
docker nodejs部署

yum install git -y
mkdir /usr/projects

-t 生成  -b 大小 -c 邮箱
ssh-keygen -t rsa -b 4096 -C "1798124436@qq.com"

cat /root/.ssh/id_rsa.pub

去setting SSH 添加公钥

cd /usr/projects
git clone 项目

nvm 安装node
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
source ~/.bashrc
nvm --version

安装最新的node npm
nvm install stable
安装全局nrm 便于切换安装源
npm install nrm -g

安装docker 
sudo yum update
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-selinux \
                  docker-engine-selinux \
                  docker-engine

yum install -y yum-utils device-mapper-persistent-data lvm2
yum-config-manager\--add-repo\https://download.docker.com/linux/centos/docker-ce.repo
yum makecache fast
vi /etc/docker/daemon.json
{
    "registry-mirrors": ["http://hub-mirror.c.163.com"]
}
sudo yum -y install docker-ce
sudo service docker start

