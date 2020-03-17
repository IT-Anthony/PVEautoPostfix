# PVEautoPostfix
Script permettant d'installer/configurer automatiquement Postfix sur des hôtes Proxmox, pour l'envoi de mail.

![alt text](https://i.imgur.com/qZ8jTuy.png)

# Pré-requis
En premier lieu il convient d'éditer son fichier /etc/hosts avec les noms et adresses IP de vos différents noeuds Proxmox, puis il vous faudra générer une paire de clé SSH sur votre hôte via la commande ssh-keygen et enfin d'exporter votre clé publique sur vos différents noeuds via la commande ssh-copy-id root@ip_de_mon_noeud.

Si la connexion SSH ne fonctionne pas et que vous êtes sur un système Windows et que vos hôtes sont en cluster, vous pouvez effectuer cette commande qui équivaut à un ssh-copy-id : cat ~/.ssh/id_rsa.pub | ssh root@ip_de_mon_noeud "cat >> ~/.ssh/authorized_keys".


# Installation
```
# Cloner le repo
git clone https://github.com/IT-Anthony/PVEautoPostfix.git 
# Vérifier la liaision avec les hôtes
sudo ansible -m ping all 
# Démarrer le script
ansible-playbook pve-auto-postfix.yml
# Répondre aux trois questions, puis patienter
```

# Notes supplémentaires
Ce script n'est pas à utiliser en production, les mots de passe entrés via le script Ansible ne sont malheureusement pas chiffrés, et quelques modifications générales dans le Script seraient à revoir. C'était avant tout un simple exercice personnel. Libre à vous d'adapter ce script à vos besoins. Aucun support ne sera fourni sur ce Github.

Voir l'article en rapport sur mon blog personnel : https://notamax.be/proxmox-v6-configurer-lenvoi-de-mail/

