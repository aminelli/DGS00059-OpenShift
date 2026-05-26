

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

# Installazione HELM
apt-get install curl gpg apt-transport-https --yes
curl -fsSL https://packages.buildkite.com/helm-linux/helm-debian/gpgkey | gpg --dearmor | tee /usr/share/keyrings/helm.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/helm.gpg] https://packages.buildkite.com/helm-linux/helm-debian/any/ any main" | tee /etc/apt/sources.list.d/helm-stable-debian.list
apt-get update
apt-get install helm


# Installazione K9s
echo "export TERM=xterm-256color" >> ~/.bashrc
source ~/.bashrc
mkdir $HOME/downloads
cd $HOME/downloads
wget https://github.com/derailed/k9s/releases/latest/download/k9s_linux_amd64.deb &&  apt install ./k9s_linux_amd64.deb &&  rm k9s_linux_amd64.deb




```
