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
<summary>VS Code</summary>

#### Click the button to install:

[<img src="https://img.shields.io/badge/VS_Code-VS_Code?style=flat-square&label=Install%20Server&color=0098FF" alt="Install in VS Code">](https://insiders.vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522playwright%2522%252C%2522command%2522%253A%2522npx%2522%252C%2522args%2522%253A%255B%2522%2540playwright%252Fmcp%2540latest%2522%255D%257D) [<img alt="Install in VS Code Insiders" src="https://img.shields.io/badge/VS_Code_Insiders-VS_Code_Insiders?style=flat-square&label=Install%20Server&color=24bfa5">](https://insiders.vscode.dev/redirect?url=vscode-insiders%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522playwright%2522%252C%2522command%2522%253A%2522npx%2522%252C%2522args%2522%253A%255B%2522%2540playwright%252Fmcp%2540latest%2522%255D%257D)

#### Or install manually:

Follow the MCP install [guide](https://code.visualstudio.com/docs/copilot/chat/mcp-servers#_add-an-mcp-server), use the standard config above. You can also install the Playwright MCP server using the VS Code CLI:

```bash
# For VS Code
code --add-mcp '{"name":"playwright","command":"npx","args":["@playwright/mcp@latest"]}'
```

After installation, the Playwright MCP server will be available for use with your GitHub Copilot agent in VS Code.
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

