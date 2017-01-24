# Arch Linux

# Just a my personal simple tutorial to installing 
# Arch Linux

# create the partitions as needed(usually for me just one for everything)
# remember to make it bootable and
# format it
lsblk
cfdisk /dev/sdX
# write it
mkfs.ext4 /dev/sdXX
mkdir /mnt
mount /dev/sdXX /mnt
pacstrap /mnt base base-devel
# Generate fstab
genfstab -U /mnt >> /mnt/etc/fstab
# Chroot into it
arch-root /mnt
# set time zone
ln -s /usr/share/zoneinfo/Region/City /etc/localtime

# Uncomment en_US.UTF-8 UTF-8 in /etc/locale.gen, and generate it with: 
locale-gen

# Set the LANG variable in locale.conf(5) accordingly, for example:

/etc/locale.conf
LANG=en_US.UTF-8
