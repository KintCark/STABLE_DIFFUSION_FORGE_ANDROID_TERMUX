# STABLE_DIFFUSION_FORGE_ANDROID_TERMUX
Hey Everyone You Can Use Stable Diffusion Forge On Android!! BUT U NEED HIGH RAM!!!



Install stable-diffusion-webui-forge on Termux (Android) + PRoot
This will guide you on installing Forge on Termux (Android) + PRoot Distro. Make sure that you have a high-end phone to actually make this usable. On my phone with 8GB RAM, launch the webui alone take at least ~ 2 GB RAM, thus making it impossible to load any model and process further.


1. Prerequisites
First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg updated && pkg upgrade -y && termux-setup-storage &&
pkg install wget -y && pkg install git -y && pkg install proot -y &&
cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh 

2. Installing stable-diffusion-webu-forge
Run below commands sequentially as root user in Ubuntu

Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y 

Install required extensions

apt-get install libgl1 libglib2.0-0 libsm6 libxrender1 libxext6 -y

Clone the repository

git clone https://github.com/lllyasviel/stable-diffusion-webui-forge



Change the current directory

cd stable-diffusion-webui-forge


'Fix' the issue with Python running in PRoot
with newer androids u might not need this command I didn't use it and it ran fine it can cause problems.

export ANDROID_DATA=anything 

Install required Python packages

pip install -r requirements.txt 

Launch the webui. It will take some time to complete first-time installation then everything should be fine

python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu --no-half


Navigate to the webui in your browser
http://127.0.0.1:7860 

To start after rebooting termux after first installation 

cd ubuntu-in-termux && ./startubuntu.sh
cd stable-diffusion-webui-forge && python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu --no-half


