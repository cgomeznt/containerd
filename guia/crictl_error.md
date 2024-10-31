## Error crictl

This error its commond:
```bash
# crictl ps
FATA[0000] validate service connection: validate CRI v1 runtime API for endpoint "unix:///run/containerd/containerd.sock": rpc error: code = Unimplemented desc = unknown service runtime.v1.RuntimeService
[root@srv-containerd system]# crictl info
FATA[0000] validate service connection: validate CRI v1 runtime API for endpoint "unix:///run/containerd/containerd.sock": rpc error: code = Unimplemented desc = unknown service runtime.v1.RuntimeService
```

Fix error, disabled_plugins = ["cri"]:
```bash
# vi /etc/containerd/config.toml
[...]
# disabled_plugins = ["cri"]
[...]
```

And run:
```bash
# crictl ps
CONTAINER           IMAGE               CREATED             STATE               NAME                ATTEMPT             POD ID              POD

```
