# Platform Architecture:

![](/assets/Architechture-Diagram.jpg)Details --

This is overall system architecture . The architecture attempts to ensure scalability across every layer \( infra / app\) to ensure horizontal scalability everywhere.This is the master architecture to write a higly scaleout application, it talks about appliaction services , compute and network platform.

# 1--

The upper half deals with the hardware aggregation on the top of cloud layer. With the available container orchestrator , we aggregate  CPU / Storage / Network  and it looks like a 1 big consolidated resource. You can deploy application services seamlessly through the continous delivery pipeline  and they run being transparent to the underneath computing resources.At application level , the scalability is achieved at individual service level as well as elastic resource pool level.

# 2--

The layer no 2 , primarily involves creating resources acrosss private / public cloud.

# 3--

The  bottom half deals with hardware and network scale out. The architecture assumes hyperscaling \( Intel RSD implementation\) to seamlessly add CPU/ Memory / Storage and create any private cloud on top of it.

# 4--

At the network layer , it assumes that , private and public cloud are hosted in same colocation enuring minimal hop between them as well as they stay in same private network space. We collborate with Equinix colocation platform  and use their IBX/ IOA based communication to guarantee the scalability / performance and security at network layer.

Synectiks xformation platform currently implements the automation and orchestration  of the  cloud , container orchestrator, devops and alm layer, primarily layer 1 & 2.



