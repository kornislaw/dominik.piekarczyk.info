Title: Amazon AWS Lightsail
Subtitle: How to quickly set up a server using AWS Lightsail; a short kickstart.
Category: Cloud
Tags: AWS, cloud
Date: 2017-09-30

# AWS Lightstail

Amazon is currently advertising its new service as the quickest way to set up a server in the cloud. I've decided to give it a try.

## Creating a new server

Just sign in to `https://lightsail.aws.amazon.com/` and follow instructions, it's too straight forward to explain it here.

I chose Ubuntu bare OS, the lowest config for $5/mo.

## Connecting to the server

When the server is on (takes up to a minute), you can sign in to the online console instantly (by clicking the console icon), but it's much more convenient to use a linux/mac console or PuTTy.

To connect this way you need to download the private key first. You'll see a link to the key somewhere on the screen. Save it to `~/.ssh`.

The next step is changing access permissions to the file, for me it was:

`chmod 600 ~/.ssh/LightsailDefaultPrivateKey-eu-central-1.pem`

Then you can sign in:

`ssh user@182.124.162.227 -i ~/.ssh/LightsailDefaultPrivateKey-eu-central-1.pem`

```shell
ubuntu@ip-172-26-4-72:~$ cat ~/.bash_history
python -V
python3 -V
sudo touch /var/lib/cloud/instance/locale-check.skip
sudo apt-get install language-pack-pl
sudo locale-gen pl_PL.utf-8
sudo locale-gen en_EN.utf-8
sudo apt-get install language-pack-en
sudo locale-gen en_EN.utf-8
sudo locale-gen en_GB.utf-8
sudo locale-gen en_GB.UTF-8
```


## Trouble shooting

### Set locale properly

```shell
sudo apt-get install language-pack-en
sudo apt-get update; sudo apt-get upgrade
sudo nano /etc/default/locale
```

Put there:

```shell
LANG=en_US.UTF-8
LANGUAGE=en_US
LC_CTYPE=en_US.UTF-8
LC_ALL=en_US.UTF-8
```

### Install Python 3.6

AWS Ubuntu 16.04 LTS comes with Python 3.5 and 3.6 is not available on official repositories.

To install it from a third-party repository:

```
sudo add-apt-repository ppa:jonathonf/python-3.6
sudo apt-get update
sudo apt-get install python3.6
python3.6 --version
```
