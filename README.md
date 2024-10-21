需要离线安装nvidia_container_toolkit的情况（需要已经安装过nvidia drive）


1. 为了能在docker中使用gpu，需要安装Nvidia-Container-Toolkit，下载以下4个包并按顺序安装：
  1.nvidia-container-toolkit-base.deb 
  2.libnvidia-container1.deb
  3.libnvidia-container-tools.deb
  4.nvidia-container-toolkit.deb
  
2. 执行以让docker可以使用 gpu runtime
sudo nvidia-ctk runtime configure — runtime=docker

3. 重启docker
sudo systemctl restart docker

(注：docker version < 19.04時，调用GPU時需要用到的工具是nvidia-docker2)
之后就可以在运行docker时使用runtime --gpu

切换gpu到持久模式：sudo nvidia-smi -pm 1 
