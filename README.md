# PVEautoPostfix
Script permettant d'installer/configurer automatiquement Postfix sur des hôtes Proxmox, pour l'envoi de mail.


# Pré-requis
En premier lieu il convient d'éditer son fichier /etc/hosts avec les noms et adresses IP de vos différents noeuds Proxmox, puis il vous faudra générer une paire de clé SSH sur votre hôte via la commande ssh-keygen et enfin d'exporter votre clé publique sur vos différents noeuds via la commande ssh-copy-id root@ip_de_mon_noeud.

Si la connexion SSH ne fonctionne pas et que vous êtes sur un système Windows et que vos hôtes sont en cluster, vous pouvez effectuer cette commande qui équivaut à un ssh-copy-id : cat ~/.ssh/id_rsa.pub | ssh root@ip_de_mon_noeud "cat >> ~/.ssh/authorized_keys".

Ensuite il convient de réaliser un premier ansible ping -m all pour vérifier la connectivité, si tout est ok, vous pouvez poursuivre.

# Installation
Réalisez un simple git clone puis [. . . ]
