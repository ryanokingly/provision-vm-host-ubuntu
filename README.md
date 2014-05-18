# provision-vm-host-ubuntu-12.04.3-fluxbox

Provision an instance of Ubuntu Desktop to serve as a base environment for consulting work and a host platform for running VMs. 

The assumption is that you will configure a VM for each distinct type of work you do - one per client, one per project, etc. With that in mind, the base environment is provisioned with frequently-used programs like an office suite, calculator, diagramming tools, etc. while environments for various software development projects and technical training sessions are configured in VMs. 

## Prerequisites

* Internet connection

## Steps

### Step 1. Install Ubuntu Desktop. 

Using an existing system and any suitable image creation program, create a bootable Ubuntu Desktop image on a medium the target machine can read. Here are some resources that may provide useful information about this:

* http://www.ubuntu.com/
* http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-ubuntu
* https://help.ubuntu.com/community/BurningIsoHowto
* http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-mac-osx
* http://www.ubuntu.com/download/desktop/burn-a-dvd-on-mac-osx
* http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows
* http://www.ubuntu.com/download/desktop/burn-a-dvd-on-windows
 
### Step 2. Install git.

```shell
sudo apt-get -y -f install git
```

### Step 3. Clone this repo.

```shell
cd
git clone https://github.com/neopragma/provision-vm-host-ubuntu
```

### Step 4. Run the setup script.

```shell
cd ~/provision-vm-host-ubuntu
./setup
```

The setup script runs unattended for the most part, but there are a few places where you have to respond to prompts.

* The Microsoft TrueType fonts installer will ask you to accept two EULAs.
* The VMware Player install will ask you to accept two EULAs.
* VMware Player will ask you if you want it to check for updates on startup and if you want to share runtime information to help them improve the product. Respond according to your preferences. If you own a license for VMware you can enter it when prompted; otherwise, just press Enter. The unlicensed version is for personal use only.
* Dropbox will pop up a window offering you a tour of the product. Respond as you wish. 

The last thing the setup script does is to run a script named verify that checks to see if the packages and applications were installed as expected. Check the console output at the end of the run to see if there is anything you need to deal with manually. You can run verify separately any time you wish.

After these steps are done you can remove directory provision-vm-host-ubuntu.


