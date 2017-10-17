# Fastest run (teragen time + terasort time)
```
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m9.399s
user    0m6.289s
sys     0m0.265s
Terasort time:

real    1m46.142s
user    0m7.744s
sys     0m0.309s
Deleted /user/zoltankis/results/tg-10GB-4-2-512
Deleted /user/zoltankis/results/ts-10GB-4-2-512
```
# Slowest run (teragen time + terasort time)
```
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m34.652s
user    0m6.164s
sys     0m0.303s
Terasort time:

real    3m7.469s
user    0m8.540s
sys     0m0.329s
Deleted /user/zoltankis/results/tg-10GB-1-1-2048
Deleted /user/zoltankis/results/ts-10GB-1-1-2048
```
# All run
```
[zoltankis@ip-172-32-11-139 ~]$ sh YARNtest.sh
Testing loop started on Tue Oct 17 16:35:28 UTC 2017

#########################
-Dmapreduce.job.maps=2
-Dmapreduce.map.memory.mb=512
-Dmapreduce.map.java.opts.max.heap=409
-Dmapreduce.job.reduces=1
-Dmapreduce.reduce.java.opts.max.heap=409

real    1m14.427s
user    0m5.972s
sys     0m0.271s

real    2m11.925s
user    0m7.825s
sys     0m0.313s
Deleted /user/zoltankis/results/tg-10GB-2-1-512
Deleted /user/zoltankis/results/ts-10GB-2-1-512

#########################
-Dmapreduce.job.maps=2
-Dmapreduce.map.memory.mb=1024
-Dmapreduce.map.java.opts.max.heap=819
-Dmapreduce.job.reduces=1
-Dmapreduce.reduce.java.opts.max.heap=819

real    1m10.484s
user    0m5.651s
sys     0m0.267s

real    2m10.116s
user    0m8.482s
sys     0m0.300s
Deleted /user/zoltankis/results/tg-10GB-2-1-1024
Deleted /user/zoltankis/results/ts-10GB-2-1-1024
Testing loop ended on Tue Oct 17 16:42:25 UTC 2017
[zoltankis@ip-172-32-11-139 ~]$ nano YARNtest.sh
[zoltankis@ip-172-32-11-139 ~]$ nano YARNtest.sh
[zoltankis@ip-172-32-11-139 ~]$ sh YARNtest.sh
Testing loop started on Tue Oct 17 16:44:51 UTC 2017
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m15.593s
user    0m6.298s
sys     0m0.276s
Terasort time:

real    2m12.575s
user    0m8.504s
sys     0m0.338s
Deleted /user/zoltankis/results/tg-10GB-2-1-512
Deleted /user/zoltankis/results/ts-10GB-2-1-512
Testing loop ended on Tue Oct 17 16:48:25 UTC 2017
[zoltankis@ip-172-32-11-139 ~]$ nano YARNtest.sh
[zoltankis@ip-172-32-11-139 ~]$ nano YARNtest.sh
[zoltankis@ip-172-32-11-139 ~]$ sh YARNtest.sh
Testing loop started on Tue Oct 17 16:50:26 UTC 2017
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m32.874s
user    0m6.504s
sys     0m0.292s
Terasort time:

real    2m16.204s
user    0m7.912s
sys     0m0.341s
Deleted /user/zoltankis/results/tg-10GB-1-1-512
Deleted /user/zoltankis/results/ts-10GB-1-1-512
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m32.644s
user    0m5.758s
sys     0m0.278s
Terasort time:

real    2m12.708s
user    0m8.423s
sys     0m0.316s
Deleted /user/zoltankis/results/tg-10GB-1-1-1024
Deleted /user/zoltankis/results/ts-10GB-1-1-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m34.652s
user    0m6.164s
sys     0m0.303s
Terasort time:

real    3m7.469s
user    0m8.540s
sys     0m0.329s
Deleted /user/zoltankis/results/tg-10GB-1-1-2048
Deleted /user/zoltankis/results/ts-10GB-1-1-2048
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m33.657s
user    0m6.193s
sys     0m0.252s
Terasort time:

real    1m42.154s
user    0m7.827s
sys     0m0.340s
Deleted /user/zoltankis/results/tg-10GB-1-2-512
Deleted /user/zoltankis/results/ts-10GB-1-2-512
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m33.620s
user    0m5.829s
sys     0m0.232s
Terasort time:

real    1m51.865s
user    0m7.991s
sys     0m0.329s
Deleted /user/zoltankis/results/tg-10GB-1-2-1024
Deleted /user/zoltankis/results/ts-10GB-1-2-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=1
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m32.507s
user    0m6.230s
sys     0m0.245s
Terasort time:

real    2m29.111s
user    0m7.533s
sys     0m0.314s
Deleted /user/zoltankis/results/tg-10GB-1-2-2048
Deleted /user/zoltankis/results/ts-10GB-1-2-2048
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m17.513s
user    0m5.976s
sys     0m0.255s
Terasort time:

real    2m10.586s
user    0m8.637s
sys     0m0.343s
Deleted /user/zoltankis/results/tg-10GB-2-1-512
Deleted /user/zoltankis/results/ts-10GB-2-1-512
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m16.456s
user    0m6.036s
sys     0m0.276s
Terasort time:

real    2m11.957s
user    0m8.123s
sys     0m0.346s
Deleted /user/zoltankis/results/tg-10GB-2-1-1024
Deleted /user/zoltankis/results/ts-10GB-2-1-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m15.437s
user    0m5.753s
sys     0m0.250s
Terasort time:

real    3m5.325s
user    0m7.929s
sys     0m0.332s
Deleted /user/zoltankis/results/tg-10GB-2-1-2048
Deleted /user/zoltankis/results/ts-10GB-2-1-2048
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m12.568s
user    0m6.460s
sys     0m0.236s
Terasort time:

real    1m45.169s
user    0m8.339s
sys     0m0.291s
Deleted /user/zoltankis/results/tg-10GB-2-2-512
Deleted /user/zoltankis/results/ts-10GB-2-2-512
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m12.528s
user    0m6.188s
sys     0m0.260s
Terasort time:

real    1m50.995s
user    0m7.823s
sys     0m0.283s
Deleted /user/zoltankis/results/tg-10GB-2-2-1024
Deleted /user/zoltankis/results/ts-10GB-2-2-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=2
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m16.415s
user    0m6.287s
sys     0m0.265s
Terasort time:

real    2m35.335s
user    0m8.020s
sys     0m0.340s
Deleted /user/zoltankis/results/tg-10GB-2-2-2048
Deleted /user/zoltankis/results/ts-10GB-2-2-2048
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m10.614s
user    0m5.712s
sys     0m0.265s
Terasort time:

real    2m17.306s
user    0m7.646s
sys     0m0.324s
Deleted /user/zoltankis/results/tg-10GB-4-1-512
Deleted /user/zoltankis/results/ts-10GB-4-1-512
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m13.197s
user    0m6.043s
sys     0m0.302s
Terasort time:

real    2m16.410s
user    0m8.038s
sys     0m0.300s
Deleted /user/zoltankis/results/tg-10GB-4-1-1024
Deleted /user/zoltankis/results/ts-10GB-4-1-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=1
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m9.775s
user    0m6.087s
sys     0m0.273s
Terasort time:

real    3m8.408s
user    0m8.220s
sys     0m0.337s
Deleted /user/zoltankis/results/tg-10GB-4-1-2048
Deleted /user/zoltankis/results/ts-10GB-4-1-2048
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=512
        -Dmapreduce.map.java.opts.max.heap=409
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=409
Teragen time:

real    1m9.399s
user    0m6.289s
sys     0m0.265s
Terasort time:

real    1m46.142s
user    0m7.744s
sys     0m0.309s
Deleted /user/zoltankis/results/tg-10GB-4-2-512
Deleted /user/zoltankis/results/ts-10GB-4-2-512
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=1024
        -Dmapreduce.map.java.opts.max.heap=819
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    1m6.216s
user    0m5.994s
sys     0m0.247s
Terasort time:

real    1m55.155s
user    0m8.077s
sys     0m0.304s
Deleted /user/zoltankis/results/tg-10GB-4-2-1024
Deleted /user/zoltankis/results/ts-10GB-4-2-1024
##############################################################
Settings:
        -Dmapreduce.job.maps=4
        -Dmapreduce.map.memory.mb=2048
        -Dmapreduce.map.java.opts.max.heap=1638
        -Dmapreduce.job.reduces=2
        -Dmapreduce.reduce.java.opts.max.heap=1638
Teragen time:

real    1m15.001s
user    0m6.293s
sys     0m0.255s
Terasort time:

real    2m42.580s
user    0m7.935s
sys     0m0.344s
Deleted /user/zoltankis/results/tg-10GB-4-2-2048
Deleted /user/zoltankis/results/ts-10GB-4-2-2048
Testing loop ended on Tue Oct 17 17:57:14 UTC 2017
```