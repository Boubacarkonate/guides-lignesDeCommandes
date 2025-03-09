# Commandes Linux les plus courantes

### Commandes de base
```bash
pwd  # Afficher le chemin du répertoire courant
ls   # Lister les fichiers et dossiers
cd [chemin]  # Changer de répertoire
cd .. # Reculer dans le répertoire
dir # Lister les fichiers d'un dossier
mkdir [nom]  # Créer un dossier
rmdir [nom]  # Supprimer un dossier vide
rm -r [nom]  # Supprimer un dossier avec son contenu
cp [source] [destination]  # Copier un fichier ou dossier
mv [source] [destination]  # Déplacer ou renommer un fichier ou dossier
touch [nom]  # Créer un fichier vide
del [nom] # Supprimer le fichier
cat [nom]  # Afficher le contenu d'un fichier
nano [nom] # Éditer un fichier avec l’éditeur Nano
ctrl + x # Quitter éditeur de texte nano
q   # Quitter la visualition de texte less
clear # Nettoyer le terminal
history # Voir l’historique des commandes
echo ["Texte"] # Afficher du texte dans le terminal
hostname  # Afficher le nom du PC
ipconfig  # Connaître l'adresse IP locale (IPv4)
winver # Afficher la version de Windows installée
```

### Gestion des processus
```bash
ps aux  # Lister les processus en cours
top  # Afficher les processus en temps réel
kill [PID]  # Terminer un processus par son ID
killall [nom]  # Terminer tous les processus du même nom
```

### Gestion des paquets (Ubuntu/Debian)
```bash
sudo apt update  # Mettre à jour la liste des paquets
sudo apt upgrade  # Mettre à jour les paquets installés
sudo apt install [nom]  # Installer un paquet
sudo apt remove [nom]  # Supprimer un paquet
```

### Gestion des services
```bash
sudo systemctl start [service]  # Démarrer un service
sudo systemctl stop [service]  # Arrêter un service
sudo systemctl restart [service]  # Redémarrer un service
sudo systemctl status [service]  # Vérifier le statut d'un service
```

### Réseau
```bash
ip a  # Afficher les adresses IP
ping [adresse]  # Tester la connexion vers une adresse
wget [URL]  # Télécharger un fichier
curl [URL]  # Faire une requête HTTP
netstat -tulnp # Voir les ports ouverts et services actifs
```

### Gestion des services (Apache, MariaDB, etc.)
```bash
sudo systemctl start [service]  # Démarrer un service
sudo systemctl stop [service]  # Arrêter un service
sudo systemctl restart [service]  # Redémarrer un service
sudo systemctl status [service]  # Vérifier le statut d'un service
sudo systemctl enable [service] # Activer un service au démarrage
```