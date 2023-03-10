# wsl2_zsh
install example in wsl2(ubuntu 20.04 LTS) & zsh shell

## wsl2

### Install Windows Terminal app

search for windows terminal in the Windows Store and install it.
![image](https://user-images.githubusercontent.com/41939976/216258991-f0dfc6ac-3841-433c-bb66-78068cff487a.png)

### Install Linux on Windows with WSL

docs : https://learn.microsoft.com/en-us/windows/wsl/install#step-4---download-the-linux-kernel-update-package

1. Run cmd.exe in administrator mode

2. Enabling the Windows Subsystem for Linux
>
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

3. Activate Virtual Machine
>
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

4. Reboot Windows

5. Install WSL

Run cmd.exe in administrator mode

>
    C:\Users\administartor> wsl --list --online
    C:\Users\administartor> wsl --install -d Ubuntu

6. set Ubuntu

![image](https://user-images.githubusercontent.com/41939976/216259872-c08843a7-3cca-42af-87cc-60a1f2a6621e.png)

After entering the account and password, exit the shell.

### Troubleshooting Windows Subsystem for Linux

docs: https://learn.microsoft.com/en-us/windows/wsl/troubleshooting?source=recommendations

## zsh

### Install zsh

>
    $sudo apt-get update
    $sudo apt install zsh

### Install oh my zsh

>
    $sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

1. Install powerlevel10k font

Install the MesloLGS NF font, which includes git branch status display and folder icons on zsh.
After downloading, double-click the file to install.
download: https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf

2. change font In Windows Terminal options

![image](https://user-images.githubusercontent.com/41939976/216264656-606fc736-3740-4031-9eca-16aea48b915c.png)

3. install powerlevel10k

>
    $git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
    $echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc

4. config powerlevel10k

Execute the powerlevel10k installation wizard by running it again after exiting the Windows terminal.
![image](https://user-images.githubusercontent.com/41939976/216262290-01471453-c853-476e-bccc-f7c9801b92f7.png)

5. oh my zsh extension install

install zsh-autosuggestions & zsh-syntax-highlighting

>
    $git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    $git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    $vi ~/.zshrc

then export plugins

![image](https://user-images.githubusercontent.com/41939976/216263049-e1265a7c-5c81-4c0e-93c3-9cc76ae80f24.png)

then  
>
    $source ~/.zshrc

## Install go

download list : https://go.dev/dl/  

latest version now 1.20 (2023-02-02)

### if use wget
>
    $wget https://golang.org/dl/go1.20.linux-amd64.tar.gz
    $sudo tar -xvf go1.20.linux-amd64.tar.gz
    $sudo mv go /usr/local
    $cp -r /usr/local/go ~/

### if use apt package (not recommended)
>
    $sudo apt update
    $sudo apt install golang-go

## Set go environment variable

### if use bash shell
>
    $vi ~/.bashsrc

### if use zsh shell
>
    $vi ~/.zshrc

### add export
>
    export GOROOT=/usr/local/go
    export GOPATH=$HOME/go
    export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

### apply changes
>
    $source ~/.zshrc

## Install Extension in VScode

### Remote WSL

![image](https://user-images.githubusercontent.com/41939976/216244185-8b04a3bb-5a8a-421b-978d-ad683fd22e45.png)

### Go

![image](https://user-images.githubusercontent.com/41939976/216244531-66ef5e98-911c-4414-822d-43f2e20ebd6b.png)

### Go Tools

As shown in the picture above, if there is something that needs to be installed after accessing it, install it.

![image](https://user-images.githubusercontent.com/41939976/216246374-ab38fa92-679a-4c66-a9cb-313a2d196b2f.png)

## Install Rust

download list : https://www.rust-lang.org/learn/get-started

Rust updates very frequently. If you have installed Rustup some time ago, chances are your Rust version is out of date.

### Download
>
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

## Set Rust environment variale

### if use bash shell
>
    $vi ~/.bashsrc

### if use zsh shell
>
    $vi ~/.zshrc

### add export
>
    export PATH="$HOME/.cargo/bin:$PATH"

### apply changes and add config
>
    $source ~/.zshrc
    $CARGO_NET_GIT_FETCH_WITH_CLI=true
    
### check version
>
    $rustc --version
    $cargo --version



