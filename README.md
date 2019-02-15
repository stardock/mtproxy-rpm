# mtproxy-rpm
The RPM package for mtproxy  

You can view https://github.com/iimarks/MTProxy to compile mtproxy if you dont trust the package
Now

## 配置需求  
1. Centos7, 尽量kvm架构  
2. 512M内存，最好1G以上  
3. CPU > 2.5Ghz，最好是独享

## 安装和启动MTproxy服务  
```  
yum -y install epel-release  
yum -y install https://extras.getpagespeed.com/release-el7-latest.rpm  
yum -y install mtproxy  
```  

## 查询和更改配置文件  
```  
cd /etc/mtproxy  
vi mtproxy.params  
head -c 16 /dev/urandom | xxd -ps
vi secret  
```  

## 添加防火墙例外  
```
firewall-cmd --zone=public --add-port=[Your port number]/tcp --permanent  
firewall-cmd --reload  
```  


## 启动和查询服务  
```  
systemctl enable mtproxy
systemctl start mtproxy
systemctl status mtproxy
```  

以上步骤如有任何疑问请参考 https://github.com/iimarks/MTProxy  

