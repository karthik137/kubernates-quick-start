# kubernates-quick-start
Kubernates cluster setup and sample app deployment


### What is kubernates?

Kubernetes is a production-grade, open-source platform that orchestrates the placement (scheduling) and execution of application containers within and across computer clusters.

Kubernates is a tools which automates deployment of applications. It a container management tool.  Kubernetes helps you make sure containerized applications run where and when you want, and helps them find the resources and tools they need to work.




### Installing kubernates

```
$ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

$ cat << EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
deb https://apt.kubernetes.io/ kubernetes-xenial main
EOF

$ sudo apt-get update

$ sudo apt-get install -y kubelet kubeadm kubectl

```

#### Check kubeadm version

```
kubeadm version
kubeadm version: &version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.2", GitCommit:"66049e3b21efe110454d67df4fa62b08ea79a19b", GitTreeState:"clean", BuildDate:"2019-05-16T16:20:34Z", GoVersion:"go1.12.5", Compiler:"gc", Platform:"linux/amd64"}

```


### Deploy local development kubernates cluster using minikube

```
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64   && chmod +x minikube
```

```
$ sudo mv minikube /usr/local/bin
```

Check minikube version


```
$ minikube version
minikube version: v1.0.1

```

Start minikube

```
$ minikube start

```

Check kubectl cluster info

```
$ kubectl cluster-info
```



##### Kubernates deployments


Kubernetes Deployments

Once you have a running Kubernetes cluster, you can deploy your containerized applications on top of it. To do so, you create a Kubernetes Deployment configuration. The Deployment instructs Kubernetes how to create and update instances of your application. Once you've created a Deployment, the Kubernetes master schedules mentioned application instances onto individual Nodes in the cluster.

Once the application instances are created, a Kubernetes Deployment Controller continuously monitors those instances. If the Node hosting an instance goes down or is deleted, the Deployment controller replaces the instance with an instance on another Node in the cluster. This provides a self-healing mechanism to address machine failure or maintenance.


We can create and manage a deployment using kubernates command line interface, Kubectl.


Kubectl uses the kubernates API to interact with the cluster.



Let's deploy a sample nodejs application


```
$ kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080

```

#### View the deployments

```
$ kubectl get deployments

```


#### View our app


```
$ kubectl proxy
```



A Pod is a Kubernetes abstraction that represents a group of one or more application containers (such as Docker or rkt), and some shared resources for those containers. Those resources include:

    Shared storage, as Volumes
    Networking, as a unique cluster IP address
    Information about how to run each container, such as the container image version or specific ports to use