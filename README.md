# Configuração de Ambiente de Desenvolvimento

## Instalação WSL
* Comando de instalação WSL 
  ``` 
    wsl --install 
  ```
* Habilitar o Subsistema do Windows para Linux
  ```
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  ```
* Habilitar o recurso de Máquina Virtual
  ```
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  ```
* Baixar o pacote de atualização do kernel do Linux [Pacote de atualização do kernel do Linux do WSL2 para computadores x64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
* Definir o WSL 2 como a sua versão padrão
  ```
    wsl --set-default-version 2
  ```
* Instalar a distribuição do Linux pela Microsoft Store
* Instalar o Windows Terminal
* Atualizar o Linux
  ```
    sudo apt update
  ```

## Temas para o Windows Terminal
* [Windows Terminal Themes](https://windowsterminalthemes.dev/)

## Instalando Oh-My-ZSH
* Comando de instalação ZSH
  ```
    sudo apt install zsh
  ```
  Obs.: Do you want to continue? [Y/n] = y
* Verificar instalação do Curl
  ```
    curl --version
  ```
* Comando instalação Curl
  ```
    sudo apt install curl
  ```
* Baixar o Oh-My-ZSH
  ```
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
  ```
  Obs.: Do you want to change your default shell to zsh? [Y/n] = y
* Comando instalação Zinit
  ```
    bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"
  ```
* Configuração ZSH
  ```
    sudo nano .zshrc
  ```
  Obs.: Procurar **_End of Zinit's installer chunk_**
* Instalar plugins
  ```
    zinit light zdharma/fast-syntax-highlighting
    zinit light zsh-users/zsh-autosuggestions
    zinit light zsh-users/zsh-completions
  ```
  Obs.: salvar **_Ctrl + O -> Enter -> Ctrl + X_**, fechar o terminal e abrir novamente
* Link [themes Oh-My-ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

## Configuração GIT
* Comando instalação GIT
  ```
    sudo apt install git
  ```
* Configurar identidade
  ```
    git config --global user.name "Fulano de Tal"
    git config --global user.email "fulanodetal@exemplo.br"
  ```
* Gerar chave SSH
  ```
    ssh-keygen -t ed25519 -C "your_email@example.com"
  ```
  Obs.: Enter a file in which to save the key (/home/YOU/.ssh/ALGORITHM):[**Press enter**]
* Digitar uma frase secreta
  ```
    Enter passphrase (empty for no passphrase): "Frase secreta"
    Enter same passphrase again: "Corfirmar frase secreta"
  ```
* Adicionar a chave SSH ao ssh-agent
  ```
    eval "$(ssh-agent -s)"
  ```
  Obs.: Iniciar o ssh-agent em segundo plano
  ```
    ssh-add ~/.ssh/id_ed25519
  ```
  Obs.: Adicionando a chave SSH
* Copiar chave SSH para área de transferência
  ```
    cat ~/.ssh/id_ed25519.pub
  ```
  Ou abrir o arquivo .ssh/id_ed25519 no editor de texto

## Instalação do Node.js no WSL
* Instalação NVM
  ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
  ```
* Instalação do node.js lts
  ```
    nvm install --lts
  ```
* Listando as versões do node.js
  ```
    nvm ls
  ```

## Instalação do Yarn
* Comando de instalação yarn
  ```
    npm install --global yarn
  ```
