Instalar y configurar containerd
================================

Instalamos las utilidades de yum::

  # dnf install -y yum-utils

Refrescamos la información locar de los repositorios::

  # dnf makecache

Instalamos el containerd.io::

  # dnf config-manager --add-repo  https://download.docker.com/linux/centos/docker-ce.repo

  #  dnf install -y containerd.io

Hacemos un backup del archivo de configuración de containerd::

  # mv /etc/containerd/config.toml /etc/containerd/config.toml.orig

Creamos un nuevo archivo de configuración con el default template::

  # cd /etc/containerd/

  # containerd config default > config.toml

Editamos el nuevo archivo de configuración y buscamos SystemdCgroup y lo colocamos en true::

  # vi /etc/containerd/config.toml
  [...]
    SystemdCgroup = true
  [...]
