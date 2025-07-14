Before installing virtual environment
make sure u install ubuntu in termux first 


Looks like Python 3.12 actually Works!! U have to create a virtual environment so here is the guide:


To run ComfyUI in a separate environment on Termux with Python 3.10.11, follow these steps:


---

1. Install Required Packages

First, ensure your Termux is updated and install necessary packages:

apt update -y && apt upgrade -y
apt install python3-full git ffmpeg


---

2. Install & Setup a Virtual Environment

Create and activate a virtual environment:

python3 -m venv comfyui-env
source comfyui-env/bin/activate









I fixed it all u gota do is navigate to the modules folder and replace the launch_utils.py file with the modified version just tap Code

1. Prerequisites
First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg update -y && pkg install wget curl proot tar -y && wget https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/Installer/Ubuntu22/ubuntu22.sh -O ubuntu22.sh && chmod +x ubuntu22.sh && bash ubuntu22.sh 

2. Installing stable-diffusion-webui-forge
Run below commands sequentially as root user in Ubuntu

Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3 -y && pip install ffmpeg && apt dist-upgrade -y && apt install wget && apt-get install libgl1 libglib2.0 libsm6 libxrender1 libxext6 -y && apt-get install google-perftools && apt install -y libjpeg-dev zlib1g-dev && apt install libgoogle-perftools-dev && pip install moviepy==1.0.3 && pip install accelerate && pip install setuptools

Clone the repository

git clone https://github.com/lllyasviel/stable-diffusion-webui-forge

 cd stable-diffusion-webui-forge


'Fix' the issue with Python running in PRoot

export ANDROID_DATA=anything 

Install required Python packages

pip install -r requirements_versions.txt

Launch the webui. It will take some time to complete first-time installation then everything should be fine

Navigate to the webui in your browser
http://127.0.0.1:7860 

To start after rebooting termux after first installation 

cd ubuntu-in-termux && ./startubuntu.sh

THEN PASTE BOTTOM COMMAND 
cd ubuntu-in-termux && ./startubuntu.sh
cd stable-diffusion-webui-forge && python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --opt-split-attention-v1 --all-in-fp16 --vae-in-cpu --disable-model-loading-ram-optimization --unet-in-fp8-e4m3fn --precision full --skip-load-model-at-start

Use new termux 1.9.1 beta it's the latest we st released version and stable


