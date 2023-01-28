## Installer Commands

**Author: Abhishek Dey**

**Last modified: 28/01/2023**


### Install : Google Chrome

* Download google-chrome debian file from this [link](https://www.google.com/chrome/?brand=YTUH&gclid=Cj0KCQiAic6eBhCoARIsANlox85Ea9YZRw6yo23qh8jUFR8TOyNvvoWDZPsaQNeUJvB8UIEzIzn7U0YaArC2EALw_wcB&gclsrc=aw.ds)


* Go go the directory where the debian file is downloaded 

```
cd /home/user/Downloads

```

* Install google chrome

```
sudo apt install ./google-chrome-stable_current_amd64.deb

```

### Install : vim

```
sudo apt-get install vim

```


### Install : pip

```
sudo apt install python3-pip

```

### Install : pew

```
pip3 install pew

```

### Install : git


```
sudo apt-get update

sudo apt-get install git

git --version

```

* Configure your Git username and email using the following commands

```

git config --global user.name "ABC XYZ"

git config --global user.email "abc@gmail.com"

git config --list

```

### Install commmon libraries


```

pip3 install numpy pandas scipy matplotlib opencv-python

```


### Install : Jupyter notebook


```
pip3 install notebook

```

* export jupyter-notebook path in bashrc file

```

vim ~/.bashrc

export PATH=$PATH:~/.local/bin

source ~/.bashrc

```

* to open jupyter notebook in terminal

```

jupyter-notebook

```

### Install : GSUTIL


* [Gsutil installation link](https://cloud.google.com/sdk/docs/install#deb)


### Install : Docker

* [Docker installation Link](https://cnvrg.io/how-to-setup-docker-and-nvidia-docker-2-0-on-ubuntu-18-04/)


### Install : NVIDIA Driver and Cuda

* [NVIDIA Driver and Cuda Installation link](https://jackfrisht.medium.com/install-nvidia-driver-via-ppa-in-ubuntu-18-04-fc9a8c4658b9)
