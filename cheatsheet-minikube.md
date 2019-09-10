### 1.1 MINIKUBE BASIC

| Name                                         | Command                                                      |
| :------------------------------------------- | :----------------------------------------------------------- |
| minikube lifecycle                           | `minikube delete`, `minikube start`, `minikube status`, [Link: minikube](https://github.com/kubernetes/minikube) |
| Get minikube version                         | `minikube version`, [Link: all minikube releases](https://github.com/kubernetes/minikube/releases) |
| mac install minikube                         | `brew cask install minikube`, `brew cask reinstall minikube` |
| Start minikube with different machine flavor | `minikube start --memory 5120 --cpus=4`                      |
| Start minikube with a specific k8s version   | `minikube start --kubernetes-version v1.11.0`                |
| Start minikube with more customizations      | minikube start –kubernetes-version v1.11.0 –feature-gates=AdvancedAuditing=true |
| SSH to minikube vm                           | `minikube ssh`, `ssh -i ~/.minikube/machines/minikube/id_rsa docker@192.168.99.100` |
| Your local docker to use minikube dockerd    | `eval $(minikube docker-env)`, Then no need for `docker push` |
| Minikube check latest version                | `minikube update-check`                                      |
| Reference                                    | [Minikube CheatSheet](https://cheatsheet.dennyzhang.com/cheatsheet-minikube-A4), [Kubernetes kind CheatSheet](https://cheatsheet.dennyzhang.com/cheatsheet-kind-A4) |
| Reference                                    | [Kubectl CheatSheet](https://cheatsheet.dennyzhang.com/cheatsheet-kubernetes-A4), [Kubernetes Yaml](https://cheatsheet.dennyzhang.com/kubernetes-yaml-templates) |

### 1.2 CHECK STATUS

| Name                 | Command                                                      |
| :------------------- | :----------------------------------------------------------- |
| Get minikube version | `minikube version`, [Link: all minikube releases](https://github.com/kubernetes/minikube/releases) |
| Get cluster info     | `kubectl cluster-info`                                       |
| Get service info     | `minikube service <srv-name>`                                |
| Get dashboard        | `minikube dashboard`                                         |
| Get ip               | `minikube ip`                                                |
| Get minikube log     | `minikube logs`                                              |
| List addons          | `minikube addons list`                                       |

### 1.3 MINIKUBE FOLDERS

| Name                                           | Command                                          |
| :--------------------------------------------- | :----------------------------------------------- |
| Mount host OS’s folder to minikube VM          | `minikube mount /host-mount-path:/vm-mount-path` |
| Folder of k8s.io/minikube-hostpath provisioner | `/tmp/hostpath-provisioner`, `/tmp/hostpath_pv`  |
| Mount host OS’s folder to minikube VM          | `minikube mount /host-mount-path:/vm-mount-path` |
| Critical minikube folder                       | `/var/lib/localkube`, `/var/lib/docker`, `/data` |
| Check minikube config in your host OS desktop  | `~/.minikube/machines/minikube/config.json`      |
| Minikube conf in local env                     | `~/.minikube`, `~/.kube`                         |

### 1.4 MINIKUBE ADVANCED

| Name                                      | Command                                               |
| :---------------------------------------- | :---------------------------------------------------- |
| Install addon after creating minikube env | `minikube addons enable heapster`, `kubectl top node` |

### 1.5 MINIKUBE CLI ONLINE HELP

```
> minikube version
minikube version: v0.31.0

> minikube --help
Minikube is a CLI tool that provisions and manages single-node Kubernetes clusters optimized for development workflows.

Usage:
  minikube [command]

Available Commands:
  addons         Modify minikube's kubernetes addons
  cache          Add or delete an image from the local cache.
  completion     Outputs minikube shell completion for the given shell (bash or zsh)
  config         Modify minikube config
  dashboard      Access the kubernetes dashboard running within the minikube cluster
  delete         Deletes a local kubernetes cluster
  docker-env     Sets up docker env variables; similar to '$(docker-machine env)'
  help           Help about any command
  ip             Retrieves the IP address of the running cluster
  logs           Gets the logs of the running instance, used for debugging minikube, not user code
  mount          Mounts the specified directory into minikube
  profile        Profile sets the current minikube profile
  service        Gets the kubernetes URL(s) for the specified service in your local cluster
  ssh            Log into or run a command on a machine with SSH; similar to 'docker-machine ssh'
  ssh-key        Retrieve the ssh identity key path of the specified cluster
  start          Starts a local kubernetes cluster
  status         Gets the status of a local kubernetes cluster
  stop           Stops a running local kubernetes cluster
  tunnel         tunnel makes services of type LoadBalancer accessible on localhost
  update-check   Print current and latest version number
  update-context Verify the IP address of the running cluster in kubeconfig.
  version        Print the version of minikube

Flags:
      --alsologtostderr                  log to standard error as well as files
  -b, --bootstrapper string              The name of the cluster bootstrapper that will set up the kubernetes cluster. (default "kubeadm")
  -h, --help                             help for minikube
      --log_backtrace_at traceLocation   when logging hits line file:N, emit a stack trace (default :0)
      --log_dir string                   If non-empty, write log files in this directory
      --logtostderr                      log to standard error instead of files
  -p, --profile string                   The name of the minikube VM being used.
                                         	This can be modified to allow for multiple minikube instances to be run independently (default "minikube")
      --stderrthreshold severity         logs at or above this threshold go to stderr (default 2)
  -v, --v Level                          log level for V logs
      --vmodule moduleSpec               comma-separated list of pattern=N settings for file-filtered logging

Use "minikube [command] --help" for more information about a command.
```