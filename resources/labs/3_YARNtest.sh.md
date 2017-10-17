#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 1 2 4
do
   # Reducer containers
   for j in 1 2
   do
      # Container memory
      for k in 512 1024 2048
      do
         # Set mapper JVM heap
         MAP_MB=`echo "($k*0.8)/1" | bc`

         # Set reducer JVM heap
         RED_MB=`echo "($k*0.8)/1" | bc`

        echo "##############################################################"
        echo "Settings:"
        echo -e "\t-Dmapreduce.job.maps=$i"
        echo -e "\t-Dmapreduce.map.memory.mb=$k"
        echo -e "\t-Dmapreduce.map.java.opts.max.heap=$MAP_MB"
        echo -e "\t-Dmapreduce.job.reduces=$j"
        echo -e "\t-Dmapreduce.reduce.java.opts.max.heap=$RED_MB"

        echo "Teragen time:"

        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     51200000 /user/zoltankis/results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err

       echo "Terasort time:"
        time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
                     /user/zoltankis/results/tg-10GB-${i}-${j}-${k}  \
                     /user/zoltankis/results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err

        $HADOOP/hadoop fs -rm -r -skipTrash /user/zoltankis/results/tg-10GB-${i}-${j}-${k}
        $HADOOP/hadoop fs -rm -r -skipTrash /user/zoltankis/results/ts-10GB-${i}-${j}-${k}
      done
   done
done

echo Testing loop ended on `date`
