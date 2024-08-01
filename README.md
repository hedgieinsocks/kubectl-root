# kubectl-root

`kubectl-root` is a simple `kubectl` plugin that helps exec into non-root containers as `root`.

## Requirements

* you have ssh access to the k8s nodes
* the nodes have `crictl` and `runc` installed

## Installation

Place `kubectl-root` into the directory within your `PATH` (e.g. `~/.local/bin` or `~/.krew/bin`)

## Customization

You can export the following variables to tweak the plugin's behaviour.

| VARIABLE           | DEFAULT                          | DETAILS                          |
|--------------------|----------------------------------|----------------------------------|
| `KROOT_NAMESPACE`  | `default`                        | default k8s namespace            |
| `KROOT_SHELL`      | `sh`                             | default container shell          |
| `KROOT_CRICTL_BIN` | `/usr/local/bin/crictl`          | `crictl` binary path on the node |
| `KROOT_RUNC_BIN`   | `/var/lib/rancher/rke2/bin/runc` | `runc` binary path on the node   |
| `KROOT_RUNC_ROOT`  | `/run/containerd/runc/k8s.io`    | `runc` root directory            |
| `KROOT_SSH_OPT`    | ` `                              | ssh options                      |

## Usage

```
kubectl root helps exec into non-root containers as root

Usage:
  kubectl root <pod> [-c <string>] [-n <string>] [-h]

Flags:
  -c, --container string    specify container name
  -n, --namespace string    set namespace scope
  -h, --help                show this message
```
