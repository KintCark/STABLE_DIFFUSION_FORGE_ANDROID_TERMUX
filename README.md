HOLY $#!+ I Repeat!! USERLAND DOES NOT CRASH WHEN LOADING HEAVY MODELS OR USEING HIGHRES OR REFINER!! MAYBE WE FINNALY CAN GET TEXT TO VIDEO ON OUR PHONES OFFLINE IDK U WOULD NEED LOTS OF RAM!! BUT I GOTA FIGURE OUT HOW TO DOWNLOAD SVD MODELS TO THE SVD FOLDER HOPEFULLY SOMEONE CAN MAKE AN FILE BROWSER EXTENSION FOR UBUNTU WHERE U CAN BROWSE THE ROOT USERLAN FOLDER WHERE STABLE DIFFUSION FORGE IS LOCATED!! sorry for all the caps I'm just excited 😊 




Install stable-diffusion-webui-forge on USERLAND (Android)
This will guide you on installing Forge on USERLAND (Android) Make sure that you have a high-end phone to actually make this usable. On my phone with 12GB RAM, launch the webui alone take at least ~ 2 GB RAM, thus making it impossible to load any model and process further.


1. Prerequisites
First you have to install USERLAND then pick ubuntuwait for ubuntu to install then type sudo su press enter then start installing packages.once you finish completely installing forge u dont need to type sudo su again just use bottom launch command for restarting USERLAND 


apt update && apt upgrade -y &&
apt install wget -y && apt install git -y

2. Installing Forge
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
Newer Android doesn't need this it will cause problems

export ANDROID_DATA=anything 

Install required Python packages
pip install -r requirements.txt 

Launch the webui. It will take some time to complete first-time installation then everything should be fine

python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu --no-half


Navigate to the webui in your browser
http://127.0.0.1:7860 

To start after rebooting Userland after first installation 

THEN PASTE BOTTOM COMMAND 

cd stable-diffusion-webui-forge && python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu --no-half






USE CIVBROWSER EXTENSION!!!
to download models directly to your models folder cause u can't navigate userland folder in android.
its better this way anyway also ull need your personal civitai api key
just go to your Account settings scroll all the way down to bottom and slide the words over untill u see api then tap it.
