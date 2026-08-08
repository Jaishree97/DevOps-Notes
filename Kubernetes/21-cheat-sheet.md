# Kubernetes (K8s) Cheat Sheet

> Quick reference for `kubectl`, Kubernetes resources, configuration, networking, storage, and troubleshooting.

---

## 1. Cluster & Context

| Command | Description |
|---|---|
| `kubectl version` | Show client and server version |
| `kubectl cluster-info` | Show cluster endpoint information |
| `kubectl config get-contexts` | List all configured contexts |
| `kubectl config current-context` | Show the active context |
| `kubectl config use-context <context>` | Switch to a context |
| `kubectl config set-context --current --namespace=<ns>` | Set default namespace for current context |
| `kubectl get nodes` | List cluster nodes |
| `kubectl get nodes -o wide` | Show nodes with additional details |
| `kubectl describe node <node>` | Show detailed node information |
| `kubectl top nodes` | Show node CPU and memory usage |

> **Note:** `kubectl top` requires the Metrics Server.

---

## 2. Namespaces

| Command | Description |
|---|---|
| `kubectl get namespaces` | List namespaces |
| `kubectl create namespace <ns>` | Create a namespace |
| `kubectl delete namespace <ns>` | Delete a namespace |
| `kubectl get all -n <ns>` | Show common resources in a namespace |
| `kubectl get all -A` | Show common resources across namespaces |
| `kubectl get pods -n <ns>` | List pods in a namespace |
| `-n <ns>` / `--namespace=<ns>` | Target a specific namespace |
| `-A` / `--all-namespaces` | Target all namespaces |

---

## 3. Pods

| Command | Description |
|---|---|
| `kubectl get pods` | List pods in current namespace |
| `kubectl get pods -A` | List pods across all namespaces |
| `kubectl get pods -o wide` | Show pods with node and IP information |
| `kubectl get pods -w` | Watch pod changes |
| `kubectl describe pod <pod>` | Show pod details and events |
| `kubectl logs <pod>` | Show container logs |
| `kubectl logs <pod> -c <container>` | Show logs from a specific container |
| `kubectl logs <pod> --previous` | Show logs from the previous container instance |
| `kubectl logs -f <pod>` | Follow container logs |
| `kubectl exec -it <pod> -- /bin/sh` | Open a shell inside a container |
| `kubectl exec -it <pod> -c <container> -- /bin/sh` | Open a shell in a specific container |
| `kubectl delete pod <pod>` | Delete a pod |
| `kubectl run <pod> --image=<image>` | Create a temporary pod |
| `kubectl run -it --rm debug --image=busybox -- sh` | Start an interactive debug pod |
| `kubectl get pod <pod> -o yaml` | Display pod definition as YAML |
| `kubectl top pods` | Show pod CPU and memory usage |

> **Tip:** If a Pod is managed by a Deployment, ReplicaSet, or StatefulSet, deleting it may cause Kubernetes to create a replacement.

---

## 4. Deployments

| Command | Description |
|---|---|
| `kubectl get deployments` | List deployments |
| `kubectl describe deployment <name>` | Show deployment details |
| `kubectl create deployment <name> --image=<image>` | Create a deployment |
| `kubectl scale deployment <name> --replicas=3` | Scale deployment replicas |
| `kubectl set image deployment/<name> <container>=<image>:<tag>` | Update container image |
| `kubectl rollout status deployment/<name>` | Check rollout status |
| `kubectl rollout history deployment/<name>` | Show rollout history |
| `kubectl rollout undo deployment/<name>` | Roll back deployment |
| `kubectl rollout undo deployment/<name> --to-revision=2` | Roll back to a specific revision |
| `kubectl rollout pause deployment/<name>` | Pause rollout |
| `kubectl rollout resume deployment/<name>` | Resume rollout |
| `kubectl edit deployment <name>` | Edit deployment directly |
| `kubectl delete deployment <name>` | Delete deployment |
| `kubectl get replicasets` | List ReplicaSets |

### Rollout Examples

```bash
kubectl rollout status deployment/nginx
kubectl rollout history deployment/nginx
kubectl rollout undo deployment/nginx
