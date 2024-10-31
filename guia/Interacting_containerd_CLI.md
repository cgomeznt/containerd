## Interacting with containerd via CLI

There are several command line interface (CLI) projects for interacting with containerd:

Name      | Community             | API    | Target             | Web site                                    |
----------|-----------------------|------- | -------------------|---------------------------------------------|
`ctr`     | containerd            | Native | For debugging only | (None, see `ctr --help` to learn the usage) |
`nerdctl` | containerd (non-core) | Native | General-purpose    | https://github.com/containerd/nerdctl       |
`crictl`  | Kubernetes SIG-node   | CRI    | For debugging only | https://github.com/kubernetes-sigs/cri-tools/blob/master/docs/crictl.md |

While the `ctr` tool is bundled together with containerd, it should be noted the `ctr` tool is solely made for debugging containerd.
The [`nerdctl`](https://github.com/containerd/nerdctl) tool provides stable and human-friendly user experience.

Example (`ctr`):
```bash
ctr images pull docker.io/library/redis:alpine
ctr run docker.io/library/redis:alpine redis
```

Example (`nerdctl`):
```bash
nerdctl run --name redis redis:alpine
```


For crictl is required repo Kube and install cri-tools:
```bash
  # cat <<\EOF > /etc/yum.repos.d/kubernetes.repo
  [kubernetes]
  name=Kubernetes
  baseurl=https://pkgs.k8s.io/core:/stable:/v1.30/rpm/
  enabled=1
  gpgcheck=1
  gpgkey=https://pkgs.k8s.io/core:/stable:/v1.30/rpm/repodata/repomd.xml.key
  exclude=kubelet kubeadm kubectl cri-tools kubernetes-cni
  EOF


  # dnf install -y cri-tools  --disableexcludes=kubernetes
```
