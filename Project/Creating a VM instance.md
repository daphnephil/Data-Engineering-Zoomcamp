## Creating a Virtual Machine Instance on Google Cloud Platform

### 1. [Generating Public Keys](https://cloud.google.com/compute/docs/connect/create-ssh-keys)
- create a .ssh/ directory in your home folder
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
- On your terminal input ``` cat key_filename.pub ``` to display the keys, copy it and add it to the gcp console

 
