# v2ray

bash <(curl -s -L https://raw.githubusercontent.com/dpflower/v2ray/master/install.sh)




https://github.com/v2fly/fhs-install-v2ray

https://intmainreturn0.com/v2ray-config-gen/#


yum install -y lrzsz git zip unzip curl wget qrencode libcap

ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
timedatectl set-timezone Asia/Shanghai
timedatectl set-ntp true
timedatectl status | sed -n '1p;4p'


/etc/systemd/system/v2ray.service
#User=nobody
Environment="V2RAY_VMESS_AEAD_FORCED=false"
