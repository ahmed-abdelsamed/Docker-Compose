# Docker-Compose

dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo

dnf install docker-ce docker-ce-cli containerd.io

systemctl enable --now docker

firewall-cmd --zone=public --add-masquerade --permanent
firewall-cmd --reload

curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

usermod -aG docker username

docker run hello-world

## ### Docker compose offline install
sudo yum install -y yum-utils

sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

sudo yum install --downloadonly --downloaddir rpms/ docker-ce docker-ce-cli containerd.io

sudo dnf install rpms/*.rpm --disablerepo '*'

sudo systemctl enable --now docker
