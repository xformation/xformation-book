Use Case Name: AWS Container Cluster

Actors:

* System Admin\( Who creates container cluster for application deployment\)
* Developer \( Who creates container cluster for devlopment purpose\)

Triggers:

* The user indicates that she wants to purchase items that she has selected.

Preconditions:

* User Choose the create bucket option from the  xformation UI application

Post-conditions:

* The bucket \(container cluster\) will be created on the cloud
* The  bucket will be listed the in  home page 
* The bucket will be ready to deploy the application services by dragging the application from right pane.

Normal Flow:

1. The user will select the cloud AWS , from the list options \(AWS / AZURE / GCP / VMWARE/ OPENSTACK / OVH\)
2. The system will present the  AWS cloud configuration options
3. The user will configure the  AWS  Auth provider or credential profile and region from the list of options
4. The system will present the  different container cluster \(ECS/ KUBERNETES/DCOS/SWARM\) that user can select
5. The user will select the container cluster of his choice from the list of options.
6. The system will provide the cluster configuration options depending on the selection of container cluster
7. The system will enable the ADD button when all the configuration data setup is complete.
8. The user will click the add button to initiate the container cluster creation on the cloud.
9. The system will reuqest the job runner system to run the  job
10. The system will present running job details to the user
11. The system will present the created container cluster handle to the user.
12. The user will exit the system

Alternate Flows:

6A1: The user select AWS native ECS cluster option.The system will present the following configuration options:

1. The user will indicate that this order should use alternate billing or shipping information.
2. The user will enter billing and shipping information for this order.
3. The system will validate the billing and shipping information.
4. The use case continues

5A1: The user will discover an error in the billing or shipping information associated with their account, and will change it.

1. The user will indicate that the billing and shipping information is incorrect.
2. The user will edit the billing and shipping information associated with their account.
3. The system will validate the billing and shipping information.
4. The use case returns to step 2 and continues.

5A2: The user will discover an error in the billing or shipping information that is uniquely being used for this order, and will change it.

1. The user will indicate that the billing and shipping information is incorrect.
2. The user will edit the billing and shipping information for this order.
3. The use case returns to step 3A1 step 3.

10A1: The user will determine that the order is not acceptable \(perhaps due to disatisfaction with the estimated delivery date\) and will cancel the order.

1. The user will request that the order be cancelled.
2. The system will confirm that the order has been cancelled.
3. The use case ends.



