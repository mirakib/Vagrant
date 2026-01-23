![Vagrant logo.](https://tech.osteel.me/images/2015/01/25/vagrant.png)

This repo contains Vagrant related instructions and files.

[Vagrantfile generator](https://vagrantfile-generator.vercel.app/)

# Vagrant Command Cheat Sheet

## 1️⃣ VM Lifecycle Commands

| Command | Description |
|---------|-------------|
| `vagrant up` | Boot and provision the VM. Creates it if it doesn’t exist. |
| `vagrant halt` | Gracefully stop the VM. |
| `vagrant suspend` | Pause VM, saves state to disk (faster than halt). |
| `vagrant resume` | Resume a suspended VM. |
| `vagrant destroy` | Completely remove the VM and its disk. **Irreversible**. |

## 2️⃣ SSH / VM Access

| Command | Description |
|---------|-------------|
| `vagrant ssh` | SSH into the VM. |
| `vagrant ssh-config` | Show SSH connection info (useful for manual SSH or editors). |

## 3️⃣ Status & Info

| Command | Description |
|---------|-------------|
| `vagrant status` | Check if VM is running, halted, suspended, etc. |
| `vagrant global-status` | Show **all Vagrant VMs** on the system. |
| `vagrant box list` | Show downloaded Vagrant boxes. |
| `vagrant box outdated` | Check if your box has a newer version. |

## 4️⃣ Provisioning / Reconfig

| Command | Description |
|---------|-------------|
| `vagrant provision` | Run provisioning scripts again (shell, Ansible, Puppet, etc.). |
| `vagrant reload` | Restart VM and reload Vagrantfile / provisioning. |
| `vagrant reload --provision` | Restart VM **and run provisioning again**. |

## 5️⃣ Boxes Management

| Command | Description |
|---------|-------------|
| `vagrant box add <name> <url>` | Download and add a new box. |
| `vagrant box update` | Update the box to the latest version. |
| `vagrant box remove <name>` | Remove a box from the local system. |

## 6️⃣ Snapshot / Restore

| Command | Description |
|---------|-------------|
| `vagrant snapshot save <name>` | Take a snapshot of the VM state. |
| `vagrant snapshot restore <name>` | Restore the VM to a snapshot. |
| `vagrant snapshot delete <name>` | Delete a snapshot. |

## 7️⃣ Useful Cleanup / Misc

| Command | Description |
|---------|-------------|
| `vagrant destroy -f` | Force destroy VM without prompt. |
| `vagrant reload --provision` | Quick way to re-run provisioning after changing Vagrantfile. |
| `vagrant global-status --prune` | Clean up stale Vagrant entries from `global-status`. |

