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

### Install Minikube

  [Minikube installer](https://kubernetes.io/docs/tasks/tools/install-minikube/)

#### Minikube on Windows
#### Minikube on Mac
#### Minikube on Linux

### Install Minishift

#### Minishift on Windows
#### Minikube on Mac
#### Minikube on Linux

## ODO

## Ansible

## Editors

## Misc SERVICES

### Private Repo Service

#### Gitea

### Jenkins

### Jenkins-X

### Tekton

### Nexus
