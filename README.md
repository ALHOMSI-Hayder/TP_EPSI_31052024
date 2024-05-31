# TP_EPSI_31052024
## TP Routage Linux & VPN
### Partie 1 : routage
#### 1.1 : Installation de la plateforme
Installez une machine sous Debian, avec 2 coeurs de processeurs et 2Go de RAM
Mettez 2 cartes réseau : une en connexion par pont sur le réseau EPSI, une dans un réseau privé
Sur la VM, installez un serveur DHCP pour distribuer des adresses IP sur le réseau privé
Démarrez une VM Kubuntu live connectée au réseau privé et vérifiez que vous recevez bien une adresse IP et que vous pouvez pinguer le serveur

#### 1.2 : Routage sous Debian
Configurez le serveur pour faire du routage : https://alexbacher.fr/unixlinux/routagedeb/ attention: n'utilisez pas IPTABLES, mais NFTABLES : https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/9/html/configuring_firewalls_and_packet_filters/configuring-nat-using-nftables_getting-started-with-nftables
Depuis le client Kubuntu, vérifiez que vous arrivez à pinguer 8.8.8.8

#### Links 01 : (Transformer Debian en routeur - Alex BACHER)
https://alexbacher.fr/unixlinux/routagedeb/

#### Links 02 : (2.4. Configuration du NAT à l'aide de nftables)
https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/9/html/configuring_firewalls_and_packet_filters/configuring-nat-using-nftables_getting-started-with-nftables

### Partie 2 : ???


#### 2.1


#### 2.2
