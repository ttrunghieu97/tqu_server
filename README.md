Guild for using TQU server 

OS: Debian GNU/Linux 11 (bullseye) x86_64

# Connect to server:
## Windows:
1. Download and install [Tailscale](https://tailscale.com/download/windows)
2. Open PowerShell or CMD and run:
```
tailscale up --auth-key=tskey-auth-kDyPXPQtpC21CNTRL-av45nTp1uyf4efFTx5S4zfDMaAoLwWtFW
```
## Linux:
Open terminal and run:
```
curl -fsSL https://tailscale.com/install.sh | sh && sudo tailscale up --auth-key=tskey-auth-kDyPXPQtpC21CNTRL-av45nTp1uyf4efFTx5S4zfDMaAoLwWtFW
```
# Set time 
```
sudo timedatectl set-timezone Asia/Ho_Chi_Minh
```
# Conda [cheatsheet](https://docs.conda.io/projects/conda/en/stable/user-guide/cheatsheet.html#cheatsheet):
Install
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
sudo bash miniconda.sh -b -u -p /opt/miniconda3
```
Activate shell (bash, zsh, fish,...) - only first time
``` 
source /opt/miniconda3/bin/activate
conda init <shell>
```
Usage:  
Create a New Environment  
```
conda create -n myenv python=3.9
```
Activate an Environment
```
conda activate myenv
```
Deactivate the Current Environment
```
conda deactivate
```
# Dowload file from Google [gdrive](https://github.com/glotlabs/gdrive):
Copy config - only first time:
```
cd ~ 
cp -r /home/hieutt/.config/ .config/ 
```
Downloading a single file:
```
gdrive files download <file id>
```
Downloading a directory:
```
gdrive files download --recursive <file id (directory)>
```

# Download from other host:
Using [CurlWget](https://chromewebstore.google.com/detail/curlwget/dgcfkhmmpcmkikfmonjcalnjcmjcjjdn) 
# Secure Copy:
```
scp -r /local/directory user@remote_host:/remote/destination
```
# Matlab:
```
 ./install -fileInput input.txt
./install -mode silent -fileInput input.txt
./install -mode silent -fileInput ${PWD}/input.txt
```

# Cuda 
```
sudo apt-get install -y cuda-drivers
```
```
wget https://developer.download.nvidia.com/compute/cuda/12.4.0/local_installers/cuda-repo-debian11-12-4-local_12.4.0-550.54.14-1_amd64.deb
sudo dpkg -i cuda-repo-debian11-12-4-local_12.4.0-550.54.14-1_amd64.deb
sudo cp /var/cuda-repo-debian11-12-4-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo add-apt-repository contrib
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-4
sudo reboot
```
# Pytorch
Recommend torch version for cuda12.4
```
conda install pytorch==2.4.0 torchvision==0.19.0 torchaudio==2.4.0 pytorch-cuda=12.4 -c pytorch -c nvidia
```
# Ubuntu sudo apt get update 404 Not Found 
```
mkdir ~/solution
cd ~/solution/
cat << EOF > ~/solution/sources.list
deb http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse
deb http://archive.canonical.com/ubuntu focal partner
deb-src http://archive.canonical.com/ubuntu focal partner
EOF
sudo sed -i "s/focal/$(lsb_release -c -s)/" ~/solution/sources.list
sudo rm /etc/apt/sources.list
sudo cp ~/solution/sources.list /etc/apt/sources.list
sudo mv /etc/apt/sources.list.d/* ~/solution 
sudo apt update
```
# CUDA & CUDNN 
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-ubuntu2204.pin
sudo mv cuda-ubuntu2204.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.3.2/local_installers/cuda-repo-ubuntu2204-12-3-local_12.3.2-545.23.08-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2204-12-3-local_12.3.2-545.23.08-1_amd64.deb
sudo cp /var/cuda-repo-ubuntu2204-12-3-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-3
wget https://developer.download.nvidia.com/compute/cudnn/9.0.0/local_installers/cudnn-local-repo-ubuntu2204-9.0.0_1.0-1_amd64.deb
sudo dpkg -i cudnn-local-repo-ubuntu2204-9.0.0_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu2204-9.0.0/cudnn-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cudnn
sudo apt-get -y install cudnn-cuda-12
```
# Rclone 
```
ssh -L localhost:53682:localhost:53682 username@remote_server
```
