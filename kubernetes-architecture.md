Kubernetes Architecture

Kubernetes architecture is divided into two main parts: Control Plane and Data Plane (Worker Nodes). The Control Plane manages the cluster and makes decisions, while the Worker Nodes are responsible for running the actual applications in the form of Pods.

Data Plane — Worker Nodes
1. Kubelet

Kubelet is an agent that runs on every worker node. Its actual work is to make sure that the Pods assigned to that node are running according to their configuration. It continuously communicates with the API Server to get information about the Pods that should be running on its node. Kubelet then communicates with the Container Runtime to start, stop, or restart containers as required. It also monitors the health and status of Pods and sends the current node and Pod status back to the API Server.

2. Kube-proxy

Kube-proxy is responsible for handling network connectivity for Kubernetes Services on a worker node. Its actual work is to maintain the network rules required to forward traffic coming to a Service toward the correct backend Pods. It can use mechanisms such as iptables or IPVS to implement this traffic forwarding and basic load distribution. Kube-proxy does not normally assign Pod IP addresses; Pod networking and IP allocation are mainly handled by the Kubernetes CNI/network plugin.

3. Container Runtime

The Container Runtime is the component that actually runs the containers on a worker node. Kubelet tells the runtime what containers need to be running, and the runtime performs the actual container operations. Its work includes pulling container images, creating containers, starting containers, stopping containers, and managing their lifecycle. Common container runtimes used with Kubernetes include containerd and CRI-O.

Control Plane
4. API Server

The API Server is the central communication point of Kubernetes. Its actual work is to receive requests from users and Kubernetes components, authenticate and authorize those requests, validate them, and process changes to Kubernetes resources. Other Kubernetes components also communicate through the API Server. The API Server communicates with etcd to store and retrieve the cluster's state. In simple terms, the API Server acts as the gateway through which the Kubernetes cluster is managed and accessed.

5. Scheduler

The Scheduler is responsible for deciding which worker node should run a newly created Pod. When a Pod is created without a node assigned to it, the Scheduler looks at available resources and scheduling requirements such as CPU, memory, node constraints, taints and tolerations, and affinity rules. It then selects a suitable worker node and assigns the Pod to that node. The Scheduler does not actually start the Pod; it only makes the decision about where the Pod should run.

6. etcd

etcd is the key-value store used by Kubernetes to store the cluster's persistent state and configuration. Its actual work is to keep information about Kubernetes resources such as Pods, Deployments, Services, Nodes, ReplicaSets, ConfigMaps, Secrets, and other cluster objects. When the state of the cluster changes, the API Server stores that information in etcd. Kubernetes uses this stored information as the source of truth for the cluster state.

7. Controller Manager

The Controller Manager runs different Kubernetes controllers that continuously monitor the cluster. Its actual work is to compare the desired state of the cluster with the actual state and take corrective action when they are different. For example, if the desired state requires a certain number of Pods but fewer Pods are currently running, the appropriate controller works to bring the cluster back toward the desired state. Controllers are responsible for managing resources such as Deployments, ReplicaSets, Nodes, Jobs, and other Kubernetes resources.

8. Cloud Controller Manager (CCM)

The Cloud Controller Manager connects Kubernetes with the APIs of cloud providers such as AWS, Azure, or GCP. Its actual work is to handle cloud-specific infrastructure operations that Kubernetes needs, such as creating or managing cloud load balancers, handling cloud nodes and routes, and integrating with certain cloud storage functionality. It separates cloud-provider-specific logic from the core Kubernetes components.
