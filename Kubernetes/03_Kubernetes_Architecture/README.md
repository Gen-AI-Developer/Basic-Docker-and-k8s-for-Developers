# Introduction to Kubernetes Architecture

## Overview
Kubernetes has emerged as a leading platform for orchestrating and managing containerized applications. Its distributed, client-server architecture enables efficient coordination between master and worker nodes. The master nodes serve as the control plane, managing the cluster, while worker nodes execute applications as clients. This article explores the core components of Kubernetes and various architectural topologies for deploying clusters.

## Kubernetes Components
Kubernetes components are divided into two categories: master components, which form the control plane, and node components, which run on worker nodes to execute workloads.

### Master Components
Master components manage the cluster’s operations, including scheduling, resource allocation, and maintaining cluster state. Key master components include:

- **kube-apiserver**: Acts as the primary interface for all cluster communications, exposing the Kubernetes API. It validates resource creation requests and communicates securely via a designated port. Users interact with it through tools like `kubectl` or REST API calls.
- **etcd**: A distributed key-value store that holds cluster configuration, metadata, and the desired and current state of resources. It communicates exclusively with the kube-apiserver, ensuring secure data access.
- **kube-controller-manager**: Runs controllers that maintain the cluster’s desired state by comparing the current state (stored in etcd) with the specified state. Examples include the Node Lifecycle, DaemonSet, and Deployment controllers.
- **kube-scheduler**: Assigns pods to nodes based on resource requirements, availability, affinity labels, and node taints/tolerations, optimizing workload distribution.
- **cloud-controller-manager**: Integrates with cloud providers by mapping their resources to Kubernetes objects, enabling a standardized experience across different cloud environments.

### Node Components
Node components run on worker nodes and handle the execution and management of containers. Key node components include:

- **kubelet**: An agent on each worker node that ensures containers within pods match their specifications. It interacts with the container runtime and receives pod specs via the kube-apiserver or local files.
- **kube-proxy**: A network proxy on each node that manages request forwarding using TCP, UDP, or SCTP protocols, facilitating communication with Kubernetes services.
- **Container Runtime**: Responsible for running containers within pods. Popular options include Docker, CRI-O, and containerd, with the runtime handling the actual container operations.

## Cluster Topologies
Kubernetes clusters can be configured in various topologies depending on the use case, balancing simplicity, scalability, and high availability (HA).

### Single Control-Plane Cluster
Ideal for evaluation or development, this topology runs all master components on a single node.

- **Single Node Cluster**: Combines master and worker components on one machine. Suitable for testing or CI environments, it lacks redundancy and is not recommended for production. Tools like K3s, RKE, Minikube, or Kubeadm simplify setup.
- **Single Master, Multiple Worker Nodes**: Separates master components (on one node) from worker components (on multiple nodes). This topology supports larger workloads but remains vulnerable to master node failures, making it unsuitable for production.

### High Availability (HA) Cluster
HA clusters eliminate single points of failure by scaling master components across multiple nodes, ensuring resilience and reliability.

- **Master Nodes with Co-Located Control-Plane and Etcd (Stacked Etcd Topology)**: Multiple master nodes run both control-plane components and etcd. At least three master nodes are required for HA, with etcd maintaining data redundancy. This topology is simpler but risks coupled failures if a master node goes down.
- **External Etcd Cluster**: Separates etcd nodes from control-plane nodes, reducing the impact of node failures. Each control-plane node runs kube-apiserver, kube-scheduler, and kube-controller-manager, while dedicated etcd nodes handle data storage. This setup requires more nodes but enhances fault tolerance.

### Etcd Quorum
For HA, etcd requires a quorum (majority) of nodes to agree on updates, calculated as `(n/2)+1` for `n` etcd nodes. A minimum of three etcd nodes ensures the cluster can tolerate one node failure, maintaining data consistency and availability.

## Conclusion
Kubernetes’ architecture, with its master and node components, provides a robust framework for managing containerized workloads. By understanding the roles of kube-apiserver, etcd, kube-scheduler, and other components, administrators can design clusters tailored to their needs. Topologies like single control-plane clusters suit development, while HA clusters with stacked or external etcd ensure production-grade reliability. Selecting the right topology and leveraging Kubernetes’ orchestration capabilities enables scalable, resilient application deployment.