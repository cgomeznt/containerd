Error de ctr

Si al ejecutar algun comando de ctr nos presenta este error::

  # ctr image ls
  ctr: failed to dial "/run/containerd/containerd.sock": context deadline exceeded: connection error: desc = "transport: error while dialing: dial unix:///run/containerd/containerd.sock: timeout"

Nos descargamos el containerd::

  cd /usr/lib/systemd/system
  wget https://raw.githubusercontent.com/containerd/containerd/main/containerd.service
  sed -i 's/usr\/local\/bin/usr\/bin/' /usr/lib/systemd/system/containerd.service
  systemctl daemon-reload
  systemctl enable --now containerd

Ya podemos probar::

  # ctr image ls
  REF TYPE DIGEST SIZE PLATFORMS LABELS
