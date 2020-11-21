# How to install arch

### Format partitions

So basically just format a partition as ext4 (or btrfs or zfs)
There is like a million tools to do this. You can stright up grab a ubuntu install image and do it


### Mount it 

just mount the new partition on /mnt or also literally wherever u want idc


### Get the tools

get some kind of access to pacman and therefore arch-install-scripts trust me its possible idc what distro u are in
then u need to initialize pacman stuff so its usable


### install arch

`pacstrap /mnt base`


## optional things

From here on these things arent actually required but are usually nice to do


### install grub

`pacstrap /mnt grub`

then u need to chroot in and run
`grub-install /dev/sdx` and the /dev/sdx is actually the drive u are installing to


### set root password

enter chroot
`passwd`
set ur password


### fstab

if you have other partitions that u want to keep mounted then setup ur fstab


### set time

`ln -sf /usr/share/zoneinfo/Region/City /etc/localtime`


### locales

open up `/etc/locale.gen` and uncomment locales u want
run `locale-gen`
make a `/etc/locale.conf` and set ur lang


### install other shit

here is my pacstrap
`pacstrap /mnt base base-devel xorg nvidia-dkms nvidia-utils grub NetworkManager linux linux-headers openssh neovim`
