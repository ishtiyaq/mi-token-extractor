# Token extractor

This repo will help you to enable developer mode for Yeelight and extract the token.

## Run using [vagrant](https://www.vagrantup.com/)

Start the virtual box using vagrant

```bash
vagrant up
```

Login in to the virtual box

```bash
vagrant ssh
```

Go to the project folder

```bash
cd /app
```

Run `token_extractor.py` file to extract the token

```bash
python3 token_extractor.py
```

> Note: you will be asked to enter the username and password of your mi account.

Now, you can run the following command to enable the developer mode

```bash
miiocli yeelight --ip <DEVICE_IP> --token <TOKEN> set_developer_mode 1
```

## Run manually

Install `pip` and `miio-tools` tool

```bash
sudo apt update && sudo apt install python3-pip miio-tools
```

Install the project dependencies using `pip`

```bash
pip install -r requirements.txt 
```

Run `token_extractor.py` file to extract the token

```bash
python3 token_extractor.py
```

> Note: you will be asked to enter the username and password of your mi account.

Now, you can run the following command to enable the developer mode

```bash
miiocli yeelight --ip <DEVICE_IP> --token <TOKEN> set_developer_mode 1
```
