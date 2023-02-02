# WSL2_zsh_golang
golang install example in WSL2(ubuntu 20.04 LTS) && zsh shell

### Install go

go downloads : https://go.dev/dl/
latest version now 1.20

- if use wget
>
    $wget https://golang.org/dl/go1.20.linux-amd64.tar.gz
    $sudo tar -xvf go1.20.linux-amd64.tar.gz
    $sudo mv go /usr/local
    $cp /usr/local/go ~/

- if use apt package (not recommended)
>
    $sudo apt update
    $sudo apt install golang-go

## Set go environment variable

- if use bash shell
>
    $vi ~/.bashsrc

- if use zsh shell
>
    $vi ~/.zshrc

- add export
>
    export GOROOT=/usr/local/go
    export GOPATH=$HOME/go
    export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

- apply changes
>
    source ~/.zshrc

### Install Extension in VScode

- Remote WSL

![image](https://user-images.githubusercontent.com/41939976/216244185-8b04a3bb-5a8a-421b-978d-ad683fd22e45.png)

- Go

![image](https://user-images.githubusercontent.com/41939976/216244531-66ef5e98-911c-4414-822d-43f2e20ebd6b.png)

- Go Tools install in VScode

As shown in the picture above, if there is something that needs to be installed after accessing it, install it.

![image](https://user-images.githubusercontent.com/41939976/216246374-ab38fa92-679a-4c66-a9cb-313a2d196b2f.png)