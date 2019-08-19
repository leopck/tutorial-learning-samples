1. curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
  && chmod +x minikube

2. sudo mkdir -p /usr/local/bin

3. sudo install minikube /usr/local/bin

3.5. check virt-host-validate

4.  curl -LO https://storage.googleapis.com/minikube/releases/latest/docker-machine-driver-kvm2 \
  && sudo install docker-machine-driver-kvm2 /usr/local/bin/

5. sudo swupd bundle-add virt-manager kvm-host

6. sudo systemctl status libvirtd
sudo systemctl start libvirtd
sudo systemctl enable libvirtd

7. Enable 'default' network using virt-manager
Edit > Connection Details > Virtual Networks > Add new > Name: default

Proxy:
HTTP_PROXY= HTTPS_PROXY= minikube start --vm-driver=kvm2 --docker-env HTTP_PROXY= --docker-env HTTPS_PROXY=
