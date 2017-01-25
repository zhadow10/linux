# Arch Linux

# Just a my personal simple tutorial to installing 
# Arch Linux

lsblk
cfdisk /dev/sdX
# Write it
mkfs.ext4 /dev/sdXX

mkdir /mnt

mount /dev/sdXX /mnt

pacstrap /mnt base base-devel
# Configure System
genfstab -U /mnt >> /mnt/etc/fstab

arch-root /mnt

set time zone

ln -s /usr/share/zoneinfo/Region/City /etc/localtime

Uncomment en_US.UTF-8 UTF-8 in /etc/locale.gen, and generate it with: 

locale-gen

/etc/locale.conf

LANG=en_US.UTF-8

# Create the hostname
/etc/hostname -> myhostname

/etc/hosts

127.0.0.1	  localhost.localdomain	  localhost

::1		      localhost.localdomain	  localhost

127.0.1.1	  myhostname.localdomain	myhostname

# Change root password
passwd

# Install and configure bootloader
pacman -S grub (oprtionally install os-prober)

grub-install /dev/sdX

grub-mkconfig -o /boot/grub/grub.cfg

# Wrap up to reboot into OS
exit

umount /mnt

reboot
