## Creating a Virtual Machine Instance on Google Cloud Platform

### 1. [Generating Public Keys](https://cloud.google.com/compute/docs/connect/create-ssh-keys)
- create a .ssh/ folder in your home directory
- cd into .ssh/ in your terminal
- input the code below in your terminal with key_filename and username, any name of your choice
- then enter a passphrase, like a password anytime you want to acces the key or you can leave it empty
```
ssh-keygen -t rsa -f ~/.ssh/KEY_FILENAME -C USERNAME -b 2048
```
- two keys are created, a public and private key
### 2. Adding the SSH keys to GCP
- Navigate to Compute engine/settings/metadata/SSH keys in GCP console
- add SSH keys
- On your terminal input ``` cat key_filename.pub ``` to display the keys, copy it and add it to the gcp console and save.
### 3. Creating a VM instance
- In GCP console navigate to compute engine/vm instances
- Click on create instance
- Input the required credentials: name(any name), region
- In the Machine Configuration, General purpose series - E2, machine type e2-standard-4
- Change the boot disk to ( operating system-Ubuntu ), version - 20.04
- Click on Create
- After the Vm instance is created copy the External IP
- cd into you home directory
- ``` ssh -i ~/:.ssh/gpc name you ued@external IP of your VM instance
  ``` wget https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh```
- To install type 
  ``` bash Anaconda3-2024.02-1-Linux-x86_64.sh```
  

 
