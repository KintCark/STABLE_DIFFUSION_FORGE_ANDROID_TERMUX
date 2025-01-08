python 3.12 is not supported I can't launch the
app I need someone to tell me how to create python 3.10.14 virtual environment I look all over the internet but none work. please if anyone know how tell me in issues.

1. Prerequisites
First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg updated && pkg upgrade -y && termux-setup-storage &&
pkg install wget -y && pkg install git -y && pkg install proot -y &&
cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh 

2. Installing stable-diffusion-webui-forge
Run below commands sequentially as root user in Ubuntu

Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3 -y && pip install ffmpeg --break-system-packages && apt dist-upgrade -y && apt install wget && apt-get install libgl1 libglib2.0 libsm6 libxrender1 libxext6 -y && apt-get install google-perftools && apt install -y libjpeg-dev zlib1g-dev && apt install libgoogle-perftools-dev && pip install moviepy==1.0.3 --break-system-packages && pip install accelerate --break-system-packages && pip install setuptools --break-system-packages

Clone the repository

git clone https://github.com/lllyasviel/stable-diffusion-webui-forge



Change the current directory

cd stable-diffusion-webui-forge


'Fix' the issue with Python running in PRoot

export ANDROID_DATA=anything 

Install required Python packages

pip install -r requirements_versions.txt --break-system-packages

Launch the webui. It will take some time to complete first-time installation then everything should be fine

Navigate to the webui in your browser
http://127.0.0.1:7860 

To start after rebooting termux after first installation 

cd ubuntu-in-termux && ./startubuntu.sh

THEN PASTE BOTTOM COMMAND 
cd ubuntu-in-termux && ./startubuntu.sh
cd stable-diffusion-webui-forge && python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --opt-split-attention-v1 --all-in-fp16 --vae-in-cpu --disable-model-loading-ram-optimization --unet-in-fp8-e4m3fn --precision full --skip-load-model-at-start

Use new termux 1.9.1 beta it's the latest we st released version and stable


