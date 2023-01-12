# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # config.vm.box = "ubuntu/xenial64" # ubuntu 16.04 LTS
  # config.vm.box = "ubuntu/bionic64" # ubuntu 18.04 LTS
  # config.vm.box = "ubuntu/focal64"  # ubuntu 20.04 LTS
  config.vm.box = "ubuntu/jammy64"  # ubuntu 22.04 LTS

  # config.vm.disk :disk, size: "10GB", primary: true

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 3000, host: 8030, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder ".", "/app"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false

    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus = 6
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt update
    apt install -y --no-install-recommends build-essential 
    #software-properties-common ffmpeg libsm6 libxext6 tesseract-ocr libtesseract-dev libleptonica-dev pkg-config poppler-utils libxml2-dev libxslt1-dev antiword flac ffmpeg lame libmad0 libsox-fmt-mp3 sox
    add-apt-repository ppa:deadsnakes/ppa
    apt install -y --no-install-recommends python3.8 python3.8-dev python3.8-distutils python3-pip python3-enchant
  SHELL
end
