# DevOps Team Toolchain

A set of tools that enables the DevOps culture of "Automating Everything", "Infrastructure as Code", "Pipeline as code", Workspace as code, and "Relentless Automation".

These tools includes the Kubernetes CLI (kubectl), Openshift CLI (oc), Openshift DO CLI (odo), Private Git Repository (gitea), Openshift Code Ready Containers (OCP4), VS Code, Eclipse Che, Tekton, Nexus, Sonarqube, Ansible, etc.

## Kubernetes on your Laptop

  As DevOps, whether you are a Developer or Ops/SRE specializing for cloud-native applications, it is highly recommended that you have the capability to bring up an enterprise kubernetes instance like Openshift in your laptop/desktop. Top of mind in this particular case is the CRC or Code-Ready Containers to experience openshift 4.x. 
  
  Alternatively, the Developer/Ops/SRE wearing the DevOps can also opt to get dirty or have their hands soiled with other open-source tools like Minikube or try out the older version 3 of Openshift.

### Prerequisites

  As a DevOps whether your role is a Developer and/or SRE, always make sure that you have the following language engines installed:

  1. [Java:latest](https://openjdk.java.net/install/)
  2. [Maven:latest](http://maven.apache.org/install.html)
  3. [Python:latest](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)
  4. [NodeJS: latest](https://nodejs.org/en/download/package-manager/)
  5. [Docker:latest](https://docs.docker.com/)
  6. [Quay.io:latest](https://docs.quay.io/solution/getting-started.html)
  7. [A github account and own simple repository for your personal/professional Dev/SRE profile. Optionally, setup your own domain for it](https://help.github.com/en/github/getting-started-with-github/signing-up-for-a-new-github-account)
  8. [Have a Redhat Developer Account](https://developers.redhat.com)

  To get started, open, login and click the Get Started link in [Openshift 4](https://try.openshift.com), select Clusters and then select "Run on Laptop". Fortunately, RH invested substantially to provide an installer (IPI) that made it very convenient for us mortals to quickly experience Openshift 4 and be productive with it on Day 2, even if we're offline from our respective on-prem or public DC clouds.

  It is highly recommended that before we dive too deep into installing CRC, read the [getting started guide](https://access.redhat.com/documentation/en-us/red_hat_codeready_containers) first to understand the basic nuances and idiosyncracies of provisioning CRC into your laptop and OS of choice. Select the version that suits your need or simply choose the latest.

  As a general requirement, make sure your machine sufficiently meets the following minimum specifications:

  1. 4 core or virtual CPUs
  2. 16 Gb memory
  3. At least 35 Gb storage

  Download a copy of the Pull Secret file.

### Install CRC on Windows

  On Microsoft Windows, CodeReady Containers requires the Windows 10 (Pro or Home) Fall Creators Update (version 1709). CodeReady Containers does not work on earlier versions or editions of Microsoft Windows.

  In Windows, the hypervisor is Hyper-v. [Download the binaries for Hyper-V](https://mirror.openshift.com/pub/openshift-v4/clients/crc/latest/crc-windows-amd64.zip)

### Install CRC on Mac

  On macOS, CodeReady Containers requires macOS 10.12 Sierra or newer. CodeReady Containers does not work on earlier versions of macOS.

  In a Mac, the supported hypervisors are Hyperkit and Virtualbox. [Download the binaries for Hyperkit here](https://mirror.openshift.com/pub/openshift-v4/clients/crc/latest/crc-macos-amd64.tar.xz)
  [Download the binaries for Virtualbox here](https://mirror.openshift.com/pub/openshift-v4/clients/crc/1.2.0/crc_virtualbox_4.2.8.crcbundle). Note: RH seem to have stopped developing new versions for this.

### Install CRC on Linux

  * On Linux, CodeReady Containers is only supported on Red Hat Enterprise Linux/CentOS 7.5 or newer (including 8.x versions) and on the latest two stable Fedora releases.
  * When using Red Hat Enterprise Linux, the machine running CodeReady Containers must be registered with Red Hat Customer Portal.
  * Ubuntu 18.04 LTS or newer and Debian 10 or newer are not officially supported and may require manual set up of the host machine.
  * See Section 1.4, “Required software packages” to install the required packages for your Linux distribution.

  [Download the binaries for Linux KVM here](https://mirror.openshift.com/pub/openshift-v4/clients/crc/latest/crc-linux-amd64.tar.xz)

## Operating CRC

### Available Commands:
  config      Modify crc configuration
  console     Open the OpenShift Web Console in the default browser
  delete      Delete the OpenShift cluster
  help        Help about any command
  ip          Get IP address of the running OpenShift cluster
  oc-env      Add the 'oc' binary to PATH
  setup       Set up prerequisites for the OpenShift cluster
  start       Start the OpenShift cluster
  status      Display status of the OpenShift cluster
  stop        Stop the OpenShift cluster
  version     Print version information

### Install Minikube

  [Minikube installer](https://kubernetes.io/docs/tasks/tools/install-minikube/)

### Install Minishift

  [Minishift installer](https://docs.okd.io/latest/minishift/getting-started/installing.html)

## Kubernetes Client CLI

  The Kubernetes client, kubectl, controls and manages the kubernetes cluster at the command line.

### Install kubectl

  [K8 Reference](https://kubernetes.io/docs/reference/kubectl/overview/)
  [Official Kubectl Reference](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

  Basic Commands (Beginner):
  create         Create a resource from a file or from stdin.
  expose         Take a replication controller, service, deployment or pod and expose it as a new Kubernetes Service
  run            Run a particular image on the cluster
  set            Set specific features on objects

Basic Commands (Intermediate):
  explain        Documentation of resources
  get            Display one or many resources
  edit           Edit a resource on the server
  delete         Delete resources by filenames, stdin, resources and names, or by resources and label selector

Deploy Commands:
  rollout        Manage the rollout of a resource
  scale          Set a new size for a Deployment, ReplicaSet, Replication Controller, or Job
  autoscale      Auto-scale a Deployment, ReplicaSet, or ReplicationController

Cluster Management Commands:
  certificate    Modify certificate resources.
  cluster-info   Display cluster info
  top            Display Resource (CPU/Memory/Storage) usage.
  cordon         Mark node as unschedulable
  uncordon       Mark node as schedulable
  drain          Drain node in preparation for maintenance
  taint          Update the taints on one or more nodes

## Openshift CLI

  [V3](https://mirror.openshift.com/pub/openshift-v3/clients/)
  [V4](https://mirror.openshift.com/pub/openshift-v4/clients/oc/latest/)

  OpenShift Client

  This client helps you develop, build, deploy, and run your applications on any
  OpenShift or Kubernetes cluster. It also includes the administrative
  commands for managing a cluster under the 'adm' subcommand.

  To familiarize yourself with OpenShift, login to your cluster and try creating a sample application:
  ```
    oc login mycluster.mycompany.com
    oc new-project my-example
    oc new-app django-psql-example
    oc logs -f bc/django-psql-example
  ```
  To see what has been created, run:
  ```
    oc status
  ```
  and get a command shell inside one of the created containers with:
  ```
    oc rsh dc/postgresql
  ```
  To see the list of available toolchains for building applications, run:
  ```
    oc new-app -L
  ```
## Openshift DO (ODO) CLI

  [ODO Installer](https://mirror.openshift.com/pub/openshift-v4/clients/odo/latest/)

  (OpenShift Do) odo is a CLI tool for running OpenShift applications in a fast and automated manner. Reducing the complexity of deployment, odo adds iterative development without the worry of deploying your source code.

  Find more information at https://github.com/openshift/odo

  Get started by creating a new application:

  ```
    git clone https://github.com/openshift/nodejs-ex && cd nodejs-ex
    odo create nodejs
    odo push
  ```
  Your nodejs application has now been deployed. odo has pushed the source code, built the application and deployed it on OpenShift.
  You can now edit your code in real time and watch as odo automatically deploys your application.
  ```
    odo watch
  ```
  To access your application, create a URL:
  ```
    odo url create myurl
    odo push
  ```
  More information such as logs or what components you've deployed can be accessed with these commands:
  ```
    odo describe
    odo list
    odo log
  ```
## Docker CLI
Usage:	docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default "/Users/edmcbee/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/Users/edmcbee/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/Users/edmcbee/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/Users/edmcbee/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

## Podman CLI

manage pods and images

Usage:
  podman [flags]
  podman [command]

Available Commands:
  attach      Attach to a running container
  build       Build an image using instructions from Dockerfiles
  commit      Create new image based on the changed container
  container   Manage Containers
  create      Create but do not start a container
  diff        Inspect changes on container's file systems
  events      Show podman events
  exec        Run a process in a running container
  export      Export container's filesystem contents as a tar archive
  generate    Generated structured data
  healthcheck Manage Healthcheck
  help        Help about any command
  history     Show history of a specified image
  image       Manage images
  images      List images in local storage
  import      Import a tarball to create a filesystem image
  info        Display podman system information
  init        Initialize one or more containers
  inspect     Display the configuration of a container or image
  kill        Kill one or more running containers with a specific signal
  load        Load an image from container archive
  logs        Fetch the logs of a container
  pause       Pause all the processes in one or more containers
  pod         Manage pods
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image from a registry
  push        Push an image to a specified destination
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Removes one or more images from local storage
  run         Run a command in a new container
  save        Save image to an archive
  start       Start one or more containers
  stop        Stop one or more containers
  system      Manage podman
  tag         Add an additional name to a local image
  top         Display the running processes of a container
  unpause     Unpause the processes in one or more containers
  version     Display the Podman Version Information
  volume      Manage volumes
  wait        Block on one or more containers

Flags:
      --connection string           remote connection name
  -h, --help                        help for podman
      --log-level string            Log messages above specified level: debug, info, warn, error, fatal or panic. Logged to ~/.config/containers/podman.log (default "error")
      --port int                    port on remote host (default 22)
      --remote-config-path string   alternate path for configuration file
      --remote-host string          remote host
      --syslog                      Output logging information to syslog as well as the console
      --username string             username on the remote host (default "edmcbee")
  -v, --version                     Version of podman

## Ansible

[Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

usage: ansible [-h] [--version] [-v] [-b] [--become-method BECOME_METHOD]
               [--become-user BECOME_USER] [-K] [-i INVENTORY] [--list-hosts]
               [-l SUBSET] [-P POLL_INTERVAL] [-B SECONDS] [-o] [-t TREE] [-k]
               [--private-key PRIVATE_KEY_FILE] [-u REMOTE_USER]
               [-c CONNECTION] [-T TIMEOUT]
               [--ssh-common-args SSH_COMMON_ARGS]
               [--sftp-extra-args SFTP_EXTRA_ARGS]
               [--scp-extra-args SCP_EXTRA_ARGS]
               [--ssh-extra-args SSH_EXTRA_ARGS] [-C] [--syntax-check] [-D]
               [-e EXTRA_VARS] [--vault-id VAULT_IDS]
               [--ask-vault-pass | --vault-password-file VAULT_PASSWORD_FILES]
               [-f FORKS] [-M MODULE_PATH] [--playbook-dir BASEDIR]
               [-a MODULE_ARGS] [-m MODULE_NAME]
               pattern

Define and run a single task 'playbook' against a set of hosts

positional arguments:
  pattern               host pattern

optional arguments:
  --ask-vault-pass      ask for vault password
  --list-hosts          outputs a list of matching hosts; does not execute
                        anything else
  --playbook-dir BASEDIR
                        Since this tool does not use playbooks, use this as a
                        substitute playbook directory.This sets the relative
                        path for many features including roles/ group_vars/
                        etc.
  --syntax-check        perform a syntax check on the playbook, but do not
                        execute it
  --vault-id VAULT_IDS  the vault identity to use
  --vault-password-file VAULT_PASSWORD_FILES
                        vault password file
  --version             show program's version number, config file location,
                        configured module search path, module location,
                        executable location and exit
  -B SECONDS, --background SECONDS
                        run asynchronously, failing after X seconds
                        (default=N/A)
  -C, --check           don't make any changes; instead, try to predict some
                        of the changes that may occur
  -D, --diff            when changing (small) files and templates, show the
                        differences in those files; works great with --check
  -M MODULE_PATH, --module-path MODULE_PATH
                        prepend colon-separated path(s) to module library (def
                        ault=~/.ansible/plugins/modules:/usr/share/ansible/plu
                        gins/modules)
  -P POLL_INTERVAL, --poll POLL_INTERVAL
                        set the poll interval if using -B (default=15)
  -a MODULE_ARGS, --args MODULE_ARGS
                        module arguments
  -e EXTRA_VARS, --extra-vars EXTRA_VARS
                        set additional variables as key=value or YAML/JSON, if
                        filename prepend with @
  -f FORKS, --forks FORKS
                        specify number of parallel processes to use
                        (default=5)
  -h, --help            show this help message and exit
  -i INVENTORY, --inventory INVENTORY, --inventory-file INVENTORY
                        specify inventory host path or comma separated host
                        list. --inventory-file is deprecated
  -l SUBSET, --limit SUBSET
                        further limit selected hosts to an additional pattern
  -m MODULE_NAME, --module-name MODULE_NAME
                        module name to execute (default=command)
  -o, --one-line        condense output
  -t TREE, --tree TREE  log output to this directory
  -v, --verbose         verbose mode (-vvv for more, -vvvv to enable
                        connection debugging)

Privilege Escalation Options:
  control how and which user you become as on target hosts

  --become-method BECOME_METHOD
                        privilege escalation method to use (default=sudo), use
                        `ansible-doc -t become -l` to list valid choices.
  --become-user BECOME_USER
                        run operations as this user (default=root)
  -K, --ask-become-pass
                        ask for privilege escalation password
  -b, --become          run operations with become (does not imply password
                        prompting)

Connection Options:
  control as whom and how to connect to hosts

  --private-key PRIVATE_KEY_FILE, --key-file PRIVATE_KEY_FILE
                        use this file to authenticate the connection
  --scp-extra-args SCP_EXTRA_ARGS
                        specify extra arguments to pass to scp only (e.g. -l)
  --sftp-extra-args SFTP_EXTRA_ARGS
                        specify extra arguments to pass to sftp only (e.g. -f,
                        -l)
  --ssh-common-args SSH_COMMON_ARGS
                        specify common arguments to pass to sftp/scp/ssh (e.g.
                        ProxyCommand)
  --ssh-extra-args SSH_EXTRA_ARGS
                        specify extra arguments to pass to ssh only (e.g. -R)
  -T TIMEOUT, --timeout TIMEOUT
                        override the connection timeout in seconds
                        (default=10)
  -c CONNECTION, --connection CONNECTION
                        connection type to use (default=smart)
  -k, --ask-pass        ask for connection password
  -u REMOTE_USER, --user REMOTE_USER
                        connect as this user (default=None)

## Editors



## Misc SERVICES

### Private Container Registry

  [Quay as a Container](https://github.com/quay/quay/blob/master/docs/development-container.md)
  
### Private Repo Service

#### Gitea

### Jenkins

### Jenkins-X

### Tekton

### Nexus
