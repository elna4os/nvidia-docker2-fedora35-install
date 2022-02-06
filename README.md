# nvidia-docker2 on Fedora 35 installation:
nvidia-docker2 is not supported in Fedora (as of 06.02.2022), but you can install it using CentOS 8 package:     
1. Install Docker as described here: https://docs.docker.com/engine/install/fedora/
2. Setup the stable repository and the GPG key: ```curl -s -L https://nvidia.github.io/nvidia-docker/centos8/nvidia-docker.repo | sudo tee /etc/yum.repos.d/nvidia-docker.repo```
3. Update packages: ```sudo dnf update```
4. Install nvidia-docker2: ```sudo dnf install -y nvidia-docker2```
5. Restart the Docker daemon: ```sudo systemctl restart docker```
6. Test: ```sudo docker run --rm --gpus all nvidia/cuda:11.0-base nvidia-smi```

Voila! :)
