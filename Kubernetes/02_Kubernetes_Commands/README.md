# Kubernetes Commands

Kubernetes commands are primarily executed using `kubectl`, the command-line tool for interacting with Kubernetes clusters. Below is a comprehensive list of `kubectl` commands, organized by category, with usage details and examples.

### Cluster Management Commands
| Command | Usage | Example | Where Used |
|---------|-------|---------|------------|
| `kubectl cluster-info` | Display cluster information. | `kubectl cluster-info` | To verify cluster status. |
| `kubectl get nodes` | List all nodes in the cluster. | `kubectl get nodes` | To monitor cluster resources. |
| `kubectl describe node <node_name>` | Show detailed node information. | `kubectl describe node minikube` | For troubleshooting node issues. |

### Pod and Workload Commands
| Command | Usage | Example | Where Used |
|---------|-------|---------|------------|
| `kubectl get pods` | List all pods in the current namespace. | `kubectl get pods` | To check pod status. |
| `kubectl describe pod <pod_name>` | Show detailed pod information. | `kubectl describe pod nginx-pod` | For debugging pod issues. |
| `kubectl create -f <file.yaml>` | Create a resource from a YAML file. | `kubectl create -f pod.yaml` | To deploy pods or other resources. |
| `kubectl apply -f <file.yaml>` | Apply a configuration to a resource. | `kubectl apply -f deployment.yaml` | For declarative resource management. |
| `kubectl delete pod <pod_name>` | Delete a pod. | `kubectl delete pod nginx-pod` | To remove pods. |
| `kubectl exec -it <pod_name> -- <command>` | Run a command in a pod. | `kubectl exec -it nginx-pod -- bash` | For debugging or interacting with pods. |
| `kubectl logs <pod_name>` | View pod logs. | `kubectl logs nginx-pod` | For troubleshooting. |
| `kubectl get deployments` | List all deployments. | `kubectl get deployments` | To monitor application deployments. |
| `kubectl scale deployment <deployment_name> --replicas=<n>` | Scale a deployment. | `kubectl scale deployment nginx --replicas=3` | To adjust application scale. |
| `kubectl rollout status deployment <deployment_name>` | Check deployment rollout status. | `kubectl rollout status deployment nginx` | To verify deployment updates. |
| `kubectl rollout undo deployment <deployment_name>` | Roll back a deployment. | `kubectl rollout undo deployment nginx` | To revert failed updates. |

### Service and Networking Commands
| Command | Usage | Example | Where Used |
|---------|-------|---------|------------|
| `kubectl get svc` | List all services. | `kubectl get svc` | To view service configurations. |
| `kubectl expose deployment <deployment_name> --port=<port> --type=<type>` | Expose a deployment as a service. | `kubectl expose deployment nginx --port=80 --type=NodePort` | To make applications accessible. |
| `kubectl get ingress` | List all ingresses. | `kubectl get ingress` | To manage external traffic routing. |
| `kubectl describe svc <service_name>` | Show detailed service information. | `kubectl describe svc nginx-service` | For debugging networking issues. |

### Configuration and Storage Commands
| Command | Usage | Example | Where Used |
|---------|-------|---------|------------|
| `kubectl get configmap` | List all ConfigMaps. | `kubectl get configmap` | To view configuration data. |
| `kubectl get secret` | List all Secrets. | `kubectl get secret` | To manage sensitive data. |
| `kubectl get pv` | List all Persistent Volumes. | `kubectl get pv` | To monitor storage resources. |
| `kubectl get pvc` | List all Persistent Volume Claims. | `kubectl get pvc` | To check storage bindings. |

### Other Commands
| Command | Usage | Example | Where Used |
|---------|-------|---------|------------|
| `kubectl version` | Show Kubernetes client and server versions. | `kubectl version` | To verify installation. |
| `kubectl config view` | Display current kubeconfig settings. | `kubectl config view` | To check cluster context. |
| `kubectl config use-context <context>` | Switch to a different cluster context. | `kubectl config use-context minikube` | To manage multiple clusters. |
| `kubectl label pod <pod_name> <key>=<value>` | Add a label to a pod. | `kubectl label pod nginx-pod app=web` | For organizing resources. |
| `kubectl annotate pod <pod_name> <key>=<value>` | Add an annotation to a pod. | `kubectl annotate pod nginx-pod description='web-app'` | For metadata management. |
| `kubectl port-forward <pod_name> <local_port>:<pod_port>` | Forward a local port to a pod. | `kubectl port-forward nginx-pod 8080:80` | For local testing. |

These commands, sourced from resources like [Kubernetes Cheat Sheet | Kubernetes Docs](https://kubernetes.io/docs/reference/kubectl/cheatsheet/) and [Top 50+ Kubernetes Commands | GeeksforGeeks](https://www.geeksforgeeks.org/kubernetes-commands/), cover the core functionality needed to manage Kubernetes clusters effectively.

## 4. Where Kubernetes is Used

Kubernetes is a versatile platform applicable across various domains in software development, operations, and cloud computing.

- **Production Deployments**:
  - Kubernetes manages large-scale applications in production, ensuring high availability and scalability.
  - Example: Running a web application with multiple replicas across a cluster.

- **Microservices Architecture**:
  - Kubernetes orchestrates microservices, allowing independent deployment and scaling of services.
  - Example: Managing a system with separate containers for frontend, backend, and database.

- **CI/CD Pipelines**:
  - Kubernetes integrates with CI/CD tools like Jenkins and GitLab to automate application deployment.
  - Example: Deploying code changes to a Kubernetes cluster after passing tests.

- **Cloud-Native Applications**:
  - Kubernetes is the backbone of cloud-native development, supporting workloads on AWS, Azure, and Google Cloud.
  - Example: Running a containerized application on Google Kubernetes Engine (GKE).

- **Hybrid and Multi-Cloud Environments**:
  - Kubernetes enables workloads to run across on-premises and cloud environments, ensuring portability.
  - Example: Deploying an application across AWS and Azure for redundancy.

- **AI/ML Workloads**:
  - Kubernetes manages resource-intensive AI/ML workloads, optimizing GPU usage and scaling.
  - Example: Running a machine learning model training pipeline in a Kubernetes cluster.

- **DevOps Practices**:
  - Kubernetes fosters collaboration between development and operations teams through standardized workflows.
  - Example: Using Kubernetes with Helm to manage application deployments.

- **Education and Training**:
  - Kubernetes is used in academic and professional settings to teach container orchestration and cloud-native practices.
  - Example: Setting up a Minikube cluster for learning Kubernetes.

## Key Citations
- [Kubernetes - Wikipedia](https://en.wikipedia.org/wiki/Kubernetes)
- [The History of Kubernetes & Its Impact on Modern Application Development | CNCF](https://www.cncf.io/blog/2024/06/14/the-history-of-kubernetes/)
- [What is Kubernetes? | Docker Docs](https://docs.docker.com/get-started/kube/overview/)
- [Kubernetes Deprecates Docker: What You Need to Know | InfoWorld](https://www.infoworld.com/article/3601478/kubernetes-deprecates-docker-what-you-need-to-know.html)
- [Why Kubernetes? | Kubernetes Docs](https://kubernetes.io/docs/concepts/overview/)
- [CNCF Cloud Native Interactive Landscape](https://landscape.cncf.io/)
- [Kubernetes Cheat Sheet | Kubernetes Docs](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Top 50+ Kubernetes Commands You Should Know | GeeksforGeeks](https://www.geeksforgeeks.org/kubernetes-commands/)
- [kubectl Commands Reference | Kubernetes Docs](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands/)