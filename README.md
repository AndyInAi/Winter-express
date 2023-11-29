# Winter-express

```sh

echo "
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
" > /etc/apt/sources.list

export DEBIAN_FRONTEND=noninteractive

apt update -y

wget -V > /dev/null 2>&1 || apt install -y wget

git --version > /dev/null 2>&1 || apt install -y git

xz -V > /dev/null 2>&1 || apt install -y xz-utils

wget https://nodejs.org/dist/v20.10.0/node-v20.10.0-linux-x64.tar.xz -O ~/node-v20.10.0-linux-x64.tar.xz

tar -xJvf ~/node-v20.10.0-linux-x64.tar.xz -C ~/

export PATH=~/node-v20.10.0-linux-x64/bin:$PATH

echo 'PATH=~/node-v20.10.0-linux-x64/bin:$PATH' >> /etc/profile

npm config set registry http://mirrors.cloud.tencent.com/npm/

if [ ! -d ~/Winter-express ]; then cd ~/ ; git clone https://github.com/AndyInAi/Winter-express.git; fi

cd  ~/Winter-express

npm install

npm start

# starting HTTP server at http://0.0.0.0:8080

```
