Ques es ctr
=================

ctr es un cliente de línea de comandos que se envía como parte del proyecto en **containerd**. Si tiene un contenedor ejecutándose en una máquina, es probable que el binario ctr también esté presente allí.

El cliente ctr es similar a la CLI homónima de Docker, pero los comandos y los indicadores a menudo difieren de sus análogos de Docker (generalmente más fáciles de usar).

Sin embargo, ctr puede servir como un excelente medio de exploración para una audiencia más general: opera justo encima de la API en contenedor y, al examinar los comandos disponibles, puede tener una buena idea de lo que puede o no hacer en contenedor.

Comandos basicos
+++++++++++++++++++


USAGE:

   ctr [global options] command [command options] [arguments...]

VERSION:

   1.7.22

DESCRIPTION:

ctr is an unsupported debug and administrative client for interacting with the containerd daemon. Because it is unsupported, the commands,
options, and operations are not guaranteed to be backward compatible or stable from release to release of the containerd project.

COMMANDS:
   plugins, plugin            Provides information about containerd plugins
   version                    Print the client and server versions
   containers, c, container   Manage containers
   content                    Manage content
   events, event              Display containerd events
   images, image, i           Manage images
   leases                     Manage leases
   namespaces, namespace, ns  Manage namespaces
   pprof                      Provide golang pprof outputs for containerd
   run                        Run a container
   snapshots, snapshot        Manage snapshots
   tasks, t, task             Manage tasks
   install                    Install a new package
   oci                        OCI tools
   sandboxes, sandbox, sb, s  Manage sandboxes
   info                       Print the server info
   deprecations
   shim                       Interact with a shim directly
   help, h                    Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --debug                      Enable debug output in logs
   --address value, -a value    Address for containerd's GRPC server (default: "/run/containerd/containerd.sock") [$CONTAINERD_ADDRESS]
   --timeout value              Total timeout for ctr commands (default: 0s)
   --connect-timeout value      Timeout for connecting to containerd (default: 0s)
   --namespace value, -n value  Namespace to use with commands (default: "default") [$CONTAINERD_NAMESPACE]
   --help, -h                   show help
   --version, -v                print the version
