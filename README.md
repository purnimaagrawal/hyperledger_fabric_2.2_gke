
As there are already a lot of materials available for setting up Hyperledger Fabric on Kubernetes Cluster, the challenge I faced was setting up HLF 2.2 on our Kubernetes cluster. I was unable to find any adequate 2.2 helm charts for setting up the blockchain network and hence open sourcing the helm charts to contribute back to the community.

Why Kubernetes?
It’s easy to achieve high availability (HA) with Kubernetes and requires less operation effort as most of the standard operating procedures are automated.
Fabric has pre-built into container images, and Kubernetes is useful in orchestration, scaling, and managing containers.
Kubernetes supports multi-tenancy, making it possible to develop and test blockchain applications.


Why Helmfile?
Helm provides fully infrastructure as code for deployment of applications on kubernetes cluster.

It allows to declare a definition of an entire Kubernetes cluster in a single YAML file, it bundles multiple Helm releases (installation of Helm charts) and allows to tune a specification of each release depending on a type of environment (develop, test, production) on which you might want to deploy your applications.

to install all charts on a cluster:

$ helmfile sync

The blockchain network I ended up setting up consists of a RAFT-backed ordererer consensus, one organization, 3 peers, 3 orderers and a CA for each organization.


Referece : https://forum.redbeatacademy.com/t/deploying-hyperledger-fabric-2-2-on-kubernetes/86
