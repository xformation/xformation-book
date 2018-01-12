# Platform Architecture:

![](/assets/Architechture-Diagram.jpg)

Details --

This is overall system architecture . The architecture attempts to ensure scalability across every layer \( infra / app\) to ensure horizontal scalability everywhere.

# 1--

The upper half deals with the hardware aggregation on the top of cloud layer. With the available container orchestrator , we aggregate  CPU / Storage / Network  and it looks like a 1 big consolidated resource. You can deploy application services seamlessly through the continous delivery pipeline  and they run being transparent to the underneath computing resources.At application level , the scalability is achieved at individual service level as well as elastic resource pool level.

# 2--

The layer no 2 , primarily involves creating resources acrosss private / public cloud.

# 3--

The  bottom half deals with hardware and network scale out. The architecture assumes hyperscaling \( Intel RSD implementation\) to seamlessly add CPU/ Memory / Storage and create any private cloud on top of it.

# 4--

At the network layer , it assumes that , private and public cloud are hosted in same colocation enuring minimal hop between them as well as they stay in same private network space. We collborate with Equinix colocation platform  and use their IBX/ IOA based communication to guarantee the scalability / performance and security at network layer.

Synectiks xformation platform currently implements the automation and orchestration  of the  cloud , container orchestrator, devops and alm layer, primarily layer 1 & 2.

# Microservice based basic Application Architecture

![](/assets/microservices-arch.png)Notes :

This is a standard microservice based basic application architecture. We tried to carefully refactor the basic services what any enterprise  application would require and provision them separately. Each microservices uses some combination of  Cache / SQL / NOSQL / GRAPH/ BIGDATA databases to make them individually scalable.Here follows the list of basic services along with their functionality and database components:

1. **SESSION & SECURITY   SERVICE- **Primarily  serves session / security / role based access control. This uses redis cluster \( cache db\) and nosql database \(dynamo\) .
2. **CONFIGURATION  SERVICE- **Serves application configuration and config customization abilities. This use dynamo at the backend.
3. **WORKFLOW  SERVICE--**Serves business workflow services. It uses Dynamo \(NOSQL\) at the back end.
4. **CONTENT  SERVICE-- **Serves storing and accessing and searching of all documents , attatchments. It uses mongodb at the backend and distributed filesystem \(CEPH\) at the back end.
5. **Search Service --** Perform elastic and intellegent searches on any record. Uses distributed filesystem for indexing.
6. **WIKI Service -- **It store and manages the text contents. It uses Aurora RDS.
7. **SSO Service -- **It manages the Single Sign On service 
8. **Rating / Feedback Service --** It manages some basic rating / feedback services.It uses NEo4j and couchcache database.
9. **Bigdata Analytic Service  -- **It implements bigdata based analytic services. It uses DRUID on top of HDFS for olap on bigdata.
10. **Web UI** --  Application Web based UI
11. **API GATEWAY -- **API gateway for API serving

Workflow service use  JCR content service , WIKI service to cater horizontal scalability.

Apart from this , any application will have his own domain driven services depending on its functionalities.

A highly scaleout application should deploy all its basic services along with its domain drive services to a aggregated container cluster. Each individual services uses some combination of Cache / SQL / NOSQL / GRAPH/ BIGDATA databases and they also get deployed in aggregated container cluster.

# AWS Microservices Deployment Diagram



