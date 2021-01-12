# bacgpu
this is doc for CentOS os install nvidia GPU

# CentOS install GPU
1. Download Centos iso
    *  https://vault.centos.org/7.8.2003/isos/x86_64/
    *  Install system with DVD installation
2. update linux package
    *  yum update
3. Download nvidia graphics card driver
    *  https://us.download.nvidia.com/XFree86/Linux-x86_64/450.80.02/NVIDIA-Linux-x86_64-450.80.02.run
    *  This url is for download 1650 GPU card . If you need other card please ask principal for driver
4.  Install the required packages
    *  install gcc  
    `yum install gcc`
    *  install kernal-devel  
    `yum install kernel-devel`  
    `yum install "kernel-devel-uname-r == $(uname -r)"`
    #### If you see this message “No package kernel-devel-uname-r == 3.10.0-1062.el7.x86_64 available.” It is mean your kernel version devel can not find in repo . So please download your kernel version devel and install then install driver.
    #### You can use command “uname -a” to find your kernel version. Like this “Linux localhost.localdomain 3.10.0-1062.el7.x86_64 #1 SMP Wed Aug 7 18:08:02 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux”
    #### If you can not find devel package, please ask principal for it.
5.  install nvidia driver
6.  check nvidia-smi
    `nvidia-smi`
    #### make sure command output show your graphics card information
    
    
# Install Docker
1.  Uninstall old versions  
`sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine`  
2.  Install using the repository  
`sudo yum install -y yum-utils`  
`sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo`  
3.  Install docker engine  
`sudo yum install docker-ce docker-ce-cli containerd.io`  
4.Start Docker  
`sudo systemctl start docker`  
5.Check that the Docker version is greater than or equal to 19.0  
`docker –version`  
