# Raspi Server

```bash
sudo dnf install ansible
ansible-galaxy collection install -r requirements.yml
ansible-playbook raspi_server.yml -i inventory.yml --ask-become-pass --ask-vault-pass --ask-pass
```

## SD Card Setup

```bash
unxz <fedora.img.xz>
sudo dd if=<fedora.img> of=/dev/mmcblk0 bs=2048MB status=progress
partition resize to max
sudo lvresize -l +100%FREE fedora_fedora/root # maybe unmount before
sudo xfs_growfs /dev/fedora_fedora/root # maybe mount before
```

## On Server Setup

Remember the en keyboard layout when entering the passwords!

```bash
localectl set-keymap de
```
