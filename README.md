# Devops project: Nextcloud on kubernetes using Terraform with DigitalOcean as provider

Learn by truly understanding what it is you're trying to learn. This project is a little something I set up to make myself struggle, so I can understand.


## Todo, as far as figured out

- [ ] Install etcd
- [ ] Get binaries for kube-apiserver, scheduler and controller
- [ ] Run kube-apiserver with etcd ip and port (`--etcd_servers=http://192.168.2.150`)
- [ ] Run scheduler and controller with apiserver ip and port (`--master=192.168.2.200`)
- [ ] etcd <- apiserver <- scheduler + controller is the dependency graph
- [ ] Run kubelets on other machines, specifying apiserver ip and port (`--api-servers=http://192.168.2.200`)

## Mental models

These approximations of reality make sense to me in either a direct or metaphorical sense. Through these models I can weave knowledge about kubernetes into the existing tapestry of models I have accumulated over the years.

### Kubernetes, a form of C&C for infra

Etcd and k8s master can exist on the same server, they are the C&C. The node is controlled through the kubelet daemon. Resemblances to early botnets are uncanny.
Kubernetes consists out of three separate parts. 

- etcd
- k8s master (meaning kub-apiserver, controller and scheduler)
- node (kubelet daemon)

### etcd, distributed k/v store for infra
    
    etcd is an open source distributed key-value store used to hold and manage the critical information that distributed systems need to keep running. Most notably, it manages the configuration data, state data, and metadata for Kubernetes, the popular container orchestration platform.


