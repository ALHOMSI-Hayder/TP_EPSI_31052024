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

### Partie 2 : VPN

#### 2.1 : VPN site-to-site
Vous devez connecter votre serveur au serveur de votre binôme (ou entre 2 VM si vous travaillez seul⋅e)

Paramétrez WireGuard pour connecter vos 2 serveurs : https://www.it-connect.fr/mise-en-place-de-wireguard-vpn-sur-debian-11/ (le tuto marche sur debian 12 aussi)
ATTENTION: sautez la partie 1.D sur ufw, vous utilisez nftables !
Depuis votre VM client, essayez de pinguer l'autre client (les réseaux privés doivent être différents évidemment). Les trames doivent passer à travers le VPN


#### 2.2 VPN client-to-site
Vous devez connecter votre client au serveur de votre binôme (ou entre une VM client et la VM serveur située de l'autre côté du VPN Wireguard)

Installez openvpn sur le serveur, et configurez-le en tant que serveur : https://openvpn.net/community-resources/how-to/
Installez openvpn sur le client, et configurez-le pour se connecter au serveur
Modifiez la table de routage du client :
si vous êtes sur le réseau 192.168.17.0/4, dites-lui de passer par le réseau OpenVPN pour accéder au réseau 192.168.54.0
inversement, si vous êtes sur le réseau 192.168.54.0, dites-lui de passer par le réseau OpenVPN pour accéder au réseau 192.168.17.0


