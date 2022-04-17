# Basic Building Blocks
- **Node**: Serves as a worker machine in a K8s cluster. One important thing to note is that the node can be a physical computer or a virtual machine
		Reqirements:
			A kubelet running
			Container tooling like Docker
			A kube proxy process running
			Supervisord (restart components)
		Minikube: Lightweight Kubernetes implementation that creates a VM on your local machine and depoys a simple coluster containing a single node
- Pod: The simplest unit that you can interact with. You can create, deploy, and delete pods, and it represents one running process on your cluster
			Requirements:
			Docker application container
			Storage resources
			unique network IP
			options that govern how the container(s) should run
		Pod states:
			Pending
			Running
			Succeeded
			Failed
			CrashLoopBackOff
# Controllers
Application Reliability, Scalling, Load Balancing
- **ReplicaSet**: Ensures that a specified number of replicas for a pod are running at all times. (Manages pods. is managed by deployment)
- **Deployment**: Provides declarative updates for pods and ReplicaSets.
		Use Cases:
			Pod management: Running a ReplicaSet allows us to deploy a number of pods, and check their status as a single unit
			Scaling a ReplicaSet scales out the pods, and allows for the depoyment to handle more traffic
			Pause and Resume: used with larger changesets; Pause deployment, make changes, resume depolyment.
			Status. Easy way to check the health of pods, and identify issues
- **Daemon Sets**: Ensure that all nodes run a copy of a specific pod. As nodes are added or removed from the cluster, a DAmonSet
	 will add or remove the required pods
- **Jobs**: Supervisor process for pods carrying out batch jobs. Run individual processes that run once and complete successfully.
- **Service**: Allows the communication between one set of deployments with another. Use a service to get pods in two deployments to talk to each other
	Types
	- Internal
	- External (NodePort)
	- Load balancer

# Labels, Selectors and Namespaces
- **Labels**:
# Kubelet and kube proxy
- **Kubelet**
	- Communicates with API server to see if pods have been assigned to nodes
	- Executes pod containers via a container engine
	- Mounts and runs pod volumes and secrets
	- Executes health chcks to identify pod/node status
- **Podespec**
	- YAML file that describes a pod
	- The kubelet takes a set of Podspecs that are provided by the kube-apiserver and ensures that the containes described in those Podspecs are runninf and healthy
	- Kubelet only manages containers that were created by the API server - not any container running on the node
- **kube-proxy**
	- Process that runs on all worker nodes
	- Reflects services as defined in each node, and can do simple network stream or round-robin forwarding across a set of backends
	- Service cluster IPS and ports are currently found through Docker --link compatible environment variables specifying ports opened by the service proxy
	- Modes:
		- User space
		- Iptables
		- Ipvs




Links
https://www.linkedin.com/learning/learning-kubernetes/basic-building-blocks-nodes-and-pods