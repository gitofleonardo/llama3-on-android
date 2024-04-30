# llama3 On Android

[简体中文](README.md) | English

## Prerequesites

+ An android phone
+ Internet connection

## Tools required

+ Termux-app
+ Ubuntu-in-termux
+ Ollama

## Termux

Access [termux-app](https://github.com/termux/termux-app), get the latest release, then just install it to your phone.

After installation, some components needs to be installed, run the following commands below on `termux`: 

```bash
pkg install wget openssl-tool proot -y
```

```bash
wget https://raw.githubusercontent.com/MFDGaming/ubuntu-in-termux/master/ubuntu.sh
```

Change permissions

```bash
chmod 777 ubuntu.sh
```

Then execute

```bash
bash ubuntu.sh
```

Just follow the steps shown in script to install `ubuntu`.

After installation, start `ubuntu`

```bash
./startubuntu.sh
```

By this command, you will enter the `shell`, in which you can download and run `ollama`.

## Ubuntu

First of all, update your system to avoid some unexpected cases, sit down and take a rest, or have a cup or tea.

```bash
apt update && apt upgrade -y
```

Then install some frequently used packages

```bash
apt install wget screen
```

After that, download latest release of `ollama`, remember you need an `arm64` arch version to run in your phone.

```bash
# until now, the latest version of ollama is v0.1.32
wget https://github.com/ollama/ollama/releases/download/v0.1.32/ollama-linux-arm64
```

Then change permission

```bash
chmod 777 ollama-linux-arm64
```

Finally, basic environment for running `ollama` is completely setup.

## Ollama

Run `ollama` in background

```bash
screen
```

```bash
./ollama-linux-arm64 serve
```

Then press `crtl+a+d` to exit current `screen`.

After exiting the session, download the `8b` parameters version of `llama3`. But if you got enough time and space, you can also choose the `70b` version. Theoretically, you can download any models from `ollama`.

```bash
./ollama-linux-arm64 pull llama3:8b
```

If there're any errors about ca certificates, you will need to update the certificates. Google it yourself, it's not included in this readme.

Once the download finished, you can run it without any other steps

```bash
./ollama-linux-arm64 run llama3
```

## Optional

Install [maid](https://github.com/Mobile-Artificial-Intelligence/maid) to chat with llm instead of staying in a black dull console.

## Screenshots

| ![Screenshot1](Images/screenshot1.png) | ![Screenshot2](Images/screenshot2.png) |
| -- | -- |