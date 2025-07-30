# Basic components used on Kubernetes

## Pod
- It is the smallest unit of Kubernetes
- It's the abstraction of our container runtime on kubernetes.
- Pods are all the applications that we manage on kubernetes.

### Notes
- Pods usually only run 1 pod.
- Pods have their own private Ip address to communicate with other pots within kubernetes.
- Pods Ip Address are ephemeral.

## Node
- Physical or virtual machine that can store multiple pods.
- These are managed by the control plane components of kubernetes and only contain the necessary services to run pods.

## Service
- Is a static ip address that can be attached to Pods.
- It's mostly used to redirect requests from any source to Pods.
### Notes
- Usually every pod would have their own service.
- Services arent related to Pods, so if pods are deleted the service will persist.

## Ingress
- Forwards external requests to Pods services within the kubernetes network.

## ConfigMap
- Extends our external configuration to our application hosted on kubernetes.

## Secret
- Has the same purpose as a ConfigMap, but stores our information encoded on a base64 format.
### Notes
- Usually contains sensitive information such as passwords, certificates, etc...
- Since base64 format can be formatted by anyone we usually use a third party tool to provide security to our stored secrets.

## Volumes
- Helps persist the data of our Pods.
- Is a storage that attaches to our pods and saves the data wherever we want (Cloud storage, Local storage).

## Deployment Set
- Is what describes the behavior of our Pods, enabling us abstract Pods and have multiple Pods of the same application.
### Notes
- Services are used as a load balancer since the Pods created by the Deployment Set can connect to the same Deployment Set.

## Stateful Set
- Helps us run many Pods and keep track of each one. This is mainly used for pods that need persistent storage or a unique network identity.
- Same as Deployment sets, Stateful sets are used to run multiple pods of the same spec, helping us connect Pods to the same volume if the main fails.

### Difference between stateful set and deployment set
- Deployment set are used to replicate pods that dont need storage persistance or a unique network identity. Such as any frontend or backend app.
- Stateful set are used by pods that need storage persistence or unique network identity. such as Databases.
