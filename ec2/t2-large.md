# Create AMI

## Create security group

Create inbound rules that allow [these ports](https://docs.lizardbyte.dev/projects/sunshine/en/latest/about/advanced_usage.html#port) for Sunshine.

## Create EC2 instance

Create t2.large EC2 instance with 100 GB of SSD. Attach the security group.

## Set up environment

SSH into the EC2 instance and run the below commands.

```sh
sudo apt update
```

Install [xrdp](https://www.xrdp.org/) to allow RDP connections:

```sh
sudo apt install ubuntu-desktop
sudo apt install xrdp
```

Set a password for the ubuntu user:

```sh
sudo passwd ubuntu
```

Source: [StackOverflow](https://stackoverflow.com/a/65634306)

## Connect to VM

Enter public IPv4 address into Microsoft Remote Desktop. Connect with `ubuntu` account.

## Install Sunshine 0.21.0

Download the [deb file](https://github.com/LizardByte/Sunshine/releases/download/v0.21.0/sunshine-ubuntu-22.04-amd64.deb).

Install Sunshine from the downloaded file:

```sh
sudo apt install -f ./sunshine-22.04-amd64.deb
```

Source: [Sunshine docs](https://docs.lizardbyte.dev/projects/sunshine/en/latest/about/installation.html#linux)

## Start sunshine

```sh
sunshine
```

## Enable UPnP in sunshine

Go to https://localhost:47990 and in the configuration, enable UPnP to stream over the internet.

## Connect with Moonlight

Enter the IPv4 address of the EC2 instance in Moonlight. It will give you a PIN. Enter the PIN into Sunshine and close the RDP connection.

Connect to the Desktop with Moonlight.

## Steam

### Disable GPU accelerated rendering in Steam

Click steam > settings > interface > uncheck "Enable GPU accelerated rendering in web views (requires restart)"
