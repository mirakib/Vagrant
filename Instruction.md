# Download the Vagrant

https://releases.hashicorp.com/vagrant/2.4.9/vagrant_2.4.9_windows_amd64.msi

# Microsoft Visual C++ Redistributable

https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-supported-redistributable-version

# Download Oracle Virtual Box

https://download.virtualbox.org/virtualbox/7.2.16/VirtualBox-7.2.16-174877-Win.exe

# Create directory

```
mkdir vagrant
```
```
cd vagrant
```

# Initialize vagrant

```
vagrant init ubuntu/jammy64 --box-version 20241002.0.0
```

# Edit Config file

```
Vagrant.configure("2") do |config|
  config.vm.boot_timeout = 600
  config.vm.define "Ubuntu" do |ubuntu|
    config.vm.box = "ubuntu/jammy64"
    config.vm.box_version = "20241002.0.0"
    config.vm.network "forwarded_port", guest: 22, host: 55222, auto_correct: true
    ubuntu.vm.hostname = "Ubuntu"
    ubuntu.vm.network "private_network", ip: "192.168.56.13"
    
    ubuntu.vm.provider "virtualbox" do |v|
      v.memory = "6000"
      v.cpus = 2
    end
    
    ubuntu.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update -y
      sudo apt install net-tools
      echo "Web server provisioned!"
    SHELL
  end
end
```

# Provision Vagrant

```
vagrant up
```

```
vagrant provision
```

```
vagrant status
```

# SSH into Vagrant

```
vagrant ssh Ubuntu
```
