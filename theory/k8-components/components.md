# Kubernetes Components

Kubernetes is divided on two main types of components which serve a purpose in common, whether it is for monitoring of keep a program running.
These two types are:

- Control Plane components
- Node Components

## Control Plane Components

The componentes categorized as "Control Plane" are those that look to monitorize and maintain high availability throughout the kubernetes cluster.

The following components are part of the **Control Plane Components**:

- **kube-api server:**
    This component is the one that manages de Kubernetes API and is listening to the requests that may be asked by us, the Kubernetes Administrator.
    It also follows the instructions that we give it to keep the cluster up and running or even make it scale if the worker nodes are stressed.

- **etcd:**
    It focuses on managing a storage based on a key:value pair to keep all the cluster data secured.

- **kube-scheduler:**
    This component is the key for high availability and keeps order within our cluster, the kube-scheduler focuses on assigning a purpose to 
    newly created pods. Assigning them on which node they should work, this components tends to considerate the different constraints and specifications
    when deciding where to assign the newly created pod.

- **Kube-controller-manager:**
    This component focuses on monitoring the states of the cluster through the kube-api server, giving suggestions based on the desireable state
    of our worker nodes. 
    When managing the nodes we have different controller types, these are:

    - **Node controller:** Monitorizes that every node on the cluster is running and gives a warning when any cluster goes down.
    - **Job controller:** Monitorizes singular task jobs and is in charge for creating new pods to complete the new job.
    - **EndpointSlice controller:** Is in charge of populating the EndpointSlice object so pods and services can communicate with each other.
    - **ServiceAccount controller:** This controller assigns identities to all the pods created throughout the cluster, providing a way to identify
          and know the control access of each node.


