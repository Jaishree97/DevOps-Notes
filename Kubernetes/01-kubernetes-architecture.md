# Kubernetes Architecture

> Kubernetes is a container orchestration platform that automates deployment, scaling, networking, and self-healing of containerized applications.

---

# Why Kubernetes Exists

Docker allows you to build and run containers, but it focuses on running containers on a **single machine**. As applications grow across multiple servers, managing containers manually becomes difficult.

Kubernetes solves this by automatically:

- Scaling applications
- Scheduling containers across nodes
- Recovering from failures
- Managing networking and service discovery
- Maintaining the desired state of applications

> **Docker runs containers. Kubernetes manages containers at scale.**

---

# History

- **Created by:** Google
- **Open-sourced:** 2014
- **Maintained by:** CNCF (Cloud Native Computing Foundation)
- **Inspired by:** Google's Borg system
- **Abbreviation:** **K8s** (8 letters between K and S)

---

# Kubernetes Architecture

The Kubernetes cluster consists of two main parts:

- **Control Plane** – Makes decisions and manages the cluster.
- **Worker Nodes** – Run the application workloads (Pods).

![Kubernetes Architecture](images/kubernetes-cluster-architecture.png)

---

# Control Plane Components

| Component | Responsibility |
|-----------|----------------|
| **API Server** | Entry point for all Kubernetes requests |
| **Scheduler** | Chooses the best Worker Node for a Pod |
| **Controller Manager** | Maintains the desired state of the cluster |
| **etcd** | Stores the entire cluster configuration and state |

---

# Worker Node Components

| Component | Responsibility |
|-----------|----------------|
| **kubelet** | Ensures Pods are running on the node |
| **kube-proxy** | Handles networking and Service rules |
| **Container Runtime** | Runs containers (containerd, CRI-O, etc.) |

---

# Kubernetes Request Flow

Whenever you run:

```bash
kubectl apply -f pod.yaml
```

the request follows this path:

![Kubernetes Request Flow](images/kubernetes-request-flow.png)

| Step | What Happens |
|------|--------------|
| 1 | kubectl sends the request to the API Server |
| 2 | API Server authenticates and authorizes the request |
| 3 | API Server validates the manifest |
| 4 | Desired state is stored in etcd |
| 5 | Controller Manager notices the new Pod |
| 6 | Scheduler selects the best Worker Node |
| 7 | API Server updates the Pod assignment |
| 8 | kubelet receives the instruction |
| 9 | Container Runtime pulls the image (if required) |
| 10 | Container starts and the Pod becomes **Running** |

> **Everything in Kubernetes communicates through the API Server.**

---

# Failure Recovery

One of Kubernetes' biggest strengths is **self-healing**.

![Kubernetes Failure Recovery](images/kubernetes-failure-recovery.png)

### If the API Server goes down

- New `kubectl` commands fail
- No new deployments can be created
- Existing Pods continue running on Worker Nodes

### If a Worker Node goes down

- Kubernetes detects the failed node
- Node becomes **NotReady**
- Scheduler selects another healthy node
- Pods are recreated automatically

> Kubernetes continuously works to match the **desired state** with the **actual state**.

---

# kubeconfig

`kubeconfig` is the configuration file used by **kubectl** to connect to Kubernetes clusters.

It stores:

- Cluster information
- User credentials
- Contexts
- Certificates

**Default location**

```bash
~/.kube/config
```

Useful commands

```bash
kubectl config current-context
kubectl config get-contexts
kubectl config view
```

---

# Built-in Namespaces

| Namespace | Purpose |
|-----------|---------|
| `default` | Default namespace for user resources |
| `kube-system` | Kubernetes system components |
| `kube-public` | Publicly readable resources |
| `kube-node-lease` | Stores node heartbeat information |

---

# Common kubectl Commands

```bash
# Cluster Information
kubectl cluster-info

# List Worker Nodes
kubectl get nodes

# View all Pods
kubectl get pods -A

# View Pods in kube-system
kubectl get pods -n kube-system

# Current Context
kubectl config current-context

# All Contexts
kubectl config get-contexts

# View kubeconfig
kubectl config view
```

---

# Key Takeaways

- Kubernetes follows a **Control Plane + Worker Node** architecture.
- The **API Server** is the central communication hub.
- **etcd** stores the cluster's desired state.
- The **Scheduler** decides where Pods run.
- **kubelet** ensures containers stay healthy.
- Kubernetes automatically detects failures and recreates Pods when needed.
- The goal of Kubernetes is to continuously maintain the **desired state** of the cluster.
