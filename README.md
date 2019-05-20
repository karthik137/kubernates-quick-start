# kubernates-quick-start
Kubernates cluster setup and sample app deployment


### What is kubernates?

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
