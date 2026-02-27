# RKE2 Single Node Setup

Resources:

- https://github.com/ondrejsika/devopslive/tree/master/2022-06-08_rke2
- https://docs.rke2.io/install/quickstart/


Install RKE2 server:

```bash
curl -sfL https://get.rke2.io | sh -
```

Create RKE2 config file:

```bash
mkdir -p /etc/rancher/rke2/
cat << EOF > /etc/rancher/rke2/config.yaml
tls-san:
  - egd-rke2.sikademo.com
disable:
  - rke2-ingress-nginx
EOF
```

Start RKE2 server:

```
systemctl enable rke2-server.service --now
```

Install kubectl, helm, k9s

```bash
slu install-bin kubectl
slu install-bin helm
slu install-bin k9s
```

Create alias for kubectl:

```bash
ln -sf /usr/local/bin/kubectl /usr/local/bin/k
```

Copy kubeconfig file to default location:

```bash
mkdir -p ~/.kube
cp /etc/rancher/rke2/rke2.yaml ~/.kube/config
```
