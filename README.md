# PXE_sur_PI
*Ce projet configure un Raspberry Pi 3 B+ (32 bits) comme serveur PXE complet, permettant le démarrage réseau (PXE boot) de machines BIOS et UEFI pour installer Ubuntu ou charger un système Yocto via NFS.*

🎯 Objectifs

    Automatiser le déploiement de systèmes d'exploitation.
    Supporter à la fois le boot BIOS (PXELINUX) et UEFI (GRUB).
    Héberger une image Ubuntu Server et un rootfs Yocto.
    Servir de plateforme de test pour des images embarquées (Yocto → Docker).

🛠️ Stack technique

    Matériel : Raspberry Pi 3 B+
    OS : Linux (Raspberry Pi OS)
    Services :
        DHCP (isc-dhcp-server)
        TFTP (tftpd-hpa)
        HTTP (apache2)
        NFS (pour Yocto rootfs)
    Bootloaders : SYSLINUX (BIOS), GRUB UEFI (signed)
    Images : Ubuntu 22.04 Live Server, Yocto (custom)

📦 Fonctionnalités

    Configuration IP statique
    Serveur DHCP avec redirection PXE
    Serveur TFTP avec chargeurs d'amorçage
    Menu GRUB pour UEFI (Ubuntu / Yocto)
    Support PXELINUX pour BIOS
    Téléchargement et montage ISO Ubuntu
    Chargement Yocto via NFS root

🧪 Usage

    Connecte un client en réseau avec boot PXE activé (BIOS ou UEFI).
    Le client obtient une IP via DHCP.
    Il télécharge le bootloader via TFTP.
    Menu GRUB ou PXELINUX affiché → choix du système.
