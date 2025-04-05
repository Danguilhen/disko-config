This repo provides a nixos-disko configuration that creates encrypted btrfs partition on 2 hhds an 1 nvme, the 2 hdds being in RAID 1 (replicas=2) and mounted as /home.

To partition and mount:

curl -o /tmp/disk-config.nix https://raw.githubusercontent.com/Danguilhen/disko-config/main/disk-config.nix
sudo nix --experimental-features "nix-command flakes" run github:nix-community/disko/latest -- --mode destroy,format,mount /tmp/disk-config.nix
