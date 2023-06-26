### Creating a Cluster with kubeadm,

`anup@ubuntu-22042-08:~$ kubeadm init`

`anup@ubuntu-22042-08:~$ sudo kubeadm init --pod-network-cidr=10.32.0.0/12 --apiserver-advertise-address=192.168.56.4 --cri-socket=unix:///var/run/cri-dockerd.sock (Weave Net)`

or,

`anup@ubuntu-22042-08:~$ sudo kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-advertise-address=192.168.56.4 --cri-socket=unix:///var/run/cri-dockerd.sock (flannel)`

or,

`anup@ubuntu-22042-08:~$ sudo kubeadm init --pod-network-cidr=192.168.0.0/16 --apiserver-advertise-address=192.168.56.4 --cri-socket=unix:///var/run/cri-dockerd.sock (calico)`

<br>

**For root user,**

`[anup@rhel-92-04 ~]$ export KUBECONFIG=/etc/kubernetes/admin.conf`

<br>

**For nonroot user,**


`[anup@rhel-92-04 ~]$ mkdir -p $HOME/.kube`

`[anup@rhel-92-04 ~]$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`

`[anup@rhel-92-04 ~]$ sudo chown $(id -u):$(id -g) $HOME/.kube/config`

<br>

**To join master,**


    kubeadm join 192.168.56.4:6443 --token 70gkub.z2blgf5fem7kxy8b \
            --discovery-token-ca-cert-hash sha256:fb0850c6gdab6j008cke574348b5bb5ddc9ba0a10746c8e9f7367d7723f243881a56

<br>

`[anup@rhel-92-04 ~]$ kubelet --version`
 
`[anup@rhel-92-04 ~]$ kubeadm version`

`[anup@rhel-92-04 ~]$ kubectl version`

<br>

`[anup@rhel-92-04 ~]$ kubectl version --client`

`[anup@rhel-92-04 ~]$ kubectl cluster-info`

`[anup@rhel-92-04 ~]$ kubectl version -o json`

`[anup@rhel-92-04 ~]$ strace -eopenat kubectl version`

`[anup@rhel-92-04 ~]$ kubectl config view --flatten`

`[anup@rhel-92-04 ~]$ kubectl get nodes`

`[anup@rhel-92-04 ~]$ kubectl get pods`

`[anup@rhel-92-04 ~]$ kubectl get replicaset`

`[anup@rhel-92-04 ~]$ kubectl get service`

<br>
