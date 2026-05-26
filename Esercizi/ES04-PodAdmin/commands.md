

```sh
# Installazione pacchetti
apt-get update
apt-get install -y wget curl nano net-tools iputils-ping iproute2 htop nano

# Installazione OC
cd ~
wget https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz

mkdir openshift
tar -zxvf openshift-client-linux.tar.gz -C openshift
echo 'export PATH=$PATH:~/openshift' >> ~/.bashrc && source ~/.bashrc
rm openshift-client-linux.tar.gz

# Apri il file
nano ~/.bashrc
# e aggiungere alla fine:
export API_SERVER=
export KUBE_VAR=

# Applica subito senza riavviare
source ~/.bashrc

# OC Login
oc login $API_SERVER --username kubeadmin --password $KUBE_VAR

```
