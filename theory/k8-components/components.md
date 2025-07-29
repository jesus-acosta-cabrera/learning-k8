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

- **kube-controller-manager:**
    This component focuses on monitoring the states of the cluster through the kube-api server, giving suggestions based on the desireable state
    of our worker nodes. 
    When managing the nodes we have different controller types, these are:

    - **Node controller:** Monitorizes that every node on the cluster is running and gives a warning when any cluster goes down.
    - **Job controller:** Monitorizes singular task jobs and is in charge for creating new pods to complete the new job.
    - **EndpointSlice controller:** Is in charge of populating the EndpointSlice object so pods and services can communicate with each other.
    - **ServiceAccount controller:** This controller assigns identities to all the pods created throughout the cluster, providing a way to identify
          and know the control access of each node.

## Node Components

These components categorized as "Node Components" are the ones that are in charge of mantaining the pods running, providing an environment for
the containerized apps to run and be managed by the "Control Plane" components.

The following components are part of the **Node Components**:

- **Kubelet:**
    This component is an agent that runs on the worker machine, making sure that the containers specified are running in a Pod. The kubelet
    is based on a set of PodSpecs that are provided that the containers are healthy and running as expected, we should also specify that this only
    manages containers created by Kubernetes.

- **container Runtime:**
    Is a core component of the worker machine that enables the Pods to run containers effectively, this is also responsible for managing the lifecycle
    of containers within the kubernetes environment. This component supports the container runtimes stated on the Kubernetes CRI (Container Runtime Interface). 

- **kube-proxy:**
    This component focuses on the mantainance of the network rules set on the nodes within our Kubernets Cluster.
    Important things to know about these rules are: 
    - These rules were implemented as part of the Kubernetes service concept.
    - These rules allow the communication to our Pods from the Network session inside of the Cluster or External requests from the internet.


## Non mandatory components (But very useful)

The following components are considered as addons, these are not mandatory for the a Kubernetes Cluster to work but provide additional useful features,

- **Domain Name Server (DNS):**
    This addon provides a cluster DNS that works as a DNS Server in addition to the other DNS Servers within our cluster, the records stored on this 
    DNS are inmediately included in the DNS searches of the containers started by Kubernetes.

- **Web UI:**
    This addon is a web based ui for Kubernetes clusters, allowing the management and troubleshoot of the kubernetes cluster.

There are many more useful addons, but these are some useful addons mentioned on the Kubernetes documentation.
