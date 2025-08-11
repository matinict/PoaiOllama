# Ollama


## Install Ollama  Linux

    ##Vist https://ollama.com/download
    ##Install with one command
    curl -fsSL https://ollama.com/install.sh | sh
    sudo usermod -aG ollama $USER
    sudo chmod -R 775 /usr/share/ollama/.ollama

### Ollama  Linux Cli 

    sudo systemctl status ollama
    sudo systemctl start ollama
    sudo systemctl stop ollama
    ollama list 

## Install model  Linux

## VS Code

<details>
<summary>## VS Code</summary>

#### Click the button to install:

 https://code.visualstudio.com/download

#### Or install cli : 

    To install Visual Studio Code (VS Code) on Ubuntu using the command line interface (CLI), follow these steps:
    
    1. **Update the package list**:
       ```bash
       sudo apt update
       sudo apt install -y software-properties-common apt-transport-https wget
       wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
       sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
       sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'    
       sudo apt update
       sudo apt install -y code
       rm packages.microsoft.gpg     
       code
       ```    
    ### Notes:
    - These commands assume you’re using a 64-bit Ubuntu system.
    - If you encounter issues, ensure your system is fully updated (`sudo apt upgrade`) before starting.
    - You can also install VS Code by downloading the `.deb` package from the [official VS Code website](https://code.visualstudio.com/) and running:
      ```bash
      sudo dpkg -i <downloaded-file>.deb
      sudo apt install -f      ```
 
</details> 




## Uninstall / remove  Ollama

    ### Only Ollama Del, Models Untouched /usr/share/ollama/.ollama
    sudo systemctl stop ollama
    sudo systemctl disable ollama
    sudo rm /etc/systemd/system/ollama.service
    sudo rm $(which ollama)
    sudo userdel ollama
    sudo groupdel ollama



    ## Delete All
    sudo systemctl stop ollama
    sudo systemctl disable ollama
    sudo rm /etc/systemd/system/ollama.service
    sudo rm $(which ollama)
    sudo rm -r /usr/share/ollama
    sudo userdel ollama
    sudo groupdel ollama



## Ref.

##Vist https://ollama.com/download

