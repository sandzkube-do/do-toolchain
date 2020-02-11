# DevOps Team Toolchain

A set of tools that enables the DevOps culture of "Automating Everything", "Infrastructure as Code", "Pipeline as code", Workspace as code, and "Relentless Automation".

These tools includes the Kubernetes CLI (kubectl), Openshift CLI (oc), Openshift DO CLI (odo), Private Git Repository (gitea), Openshift Code Ready Containers (OCP4), VS Code, Eclipse Che, Tekton, Nexus, Sonarqube, Ansible, etc.

## Kubernetes on your Laptop

  As DevOps, whether you are a Developer or Ops/SRE specializing for cloud-native applications, it is highly recommended that you have the capability to bring up an enterprise kubernetes instance like Openshift in your laptop/desktop. Top of mind in this particular case is the CRC or Code-Ready Containers to experience openshift 4.x. 
  
  Alternatively, the Developer/Ops/SRE wearing the DevOps can also opt to get dirty or have their hands soiled with other open-source tools like Minikube or try out the older version 3 of Openshift.

### Prerequisites

  As a DevOps whether your role is a Developer and/or SRE, always make sure that you have the following language engines installed:

  1. Java:latest
  2. Python:latest
  3. NodeJS: latest
  4. Docker:latest
  5. A github account and own simple repository for your personal/professional Dev/SRE profile. Optionally, setup your own domain for it.
  6. Have a Redhat Developer Account

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


## Podman CLI



## Ansible



## Editors



## Misc SERVICES

### Private Repo Service

#### Gitea

### Jenkins

### Jenkins-X

### Tekton

### Nexus
