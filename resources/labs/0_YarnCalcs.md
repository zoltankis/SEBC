# Explain adjustments

My cluster has 5 node, 4 worker nodes and one edge node.
As all machines are AWS m3xlarge instances it has very limited resource, but enough for this test environment.

By default the YARNCalcs calculation reserve two vcore for the OS and one for the NodeManager and Datanode which results no vcore remains to YARN.
Because of this, in this small test cluster I modified the calculation to reserve only one vcore for the OS, NodeManager, Datanode and the YARN.

# What criteria affects workload factor? 
Workload factor is an indicator of the node loads. Unbalanced data, rack configuraton, network throughput, services on nodes, (... and many things) can affect the workload factor

# What does a value of 1, 2, or 4 signify?
Its connected to the number of CPUs that needed. The higher value means that the worload is more CPU intensive.