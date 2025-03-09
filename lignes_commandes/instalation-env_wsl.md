# Cours sur WSL pour le développement Web

## 1. Qu'est-ce que WSL ?
WSL (Windows Subsystem for Linux) est une fonctionnalité de Windows qui permet d'exécuter une distribution Linux directement sous Windows sans machine virtuelle.

Deux versions existent :
- **WSL 1** : Plus rapide pour l'accès aux fichiers Windows.
- **WSL 2** : Utilise un noyau Linux réel et offre une meilleure compatibilité.

### Comparaison entre Windows et Linux (natif ou WSL)

| Critère                        | Windows                                               | Linux (natif ou WSL)                               |
|--------------------------------|------------------------------------------------------|--------------------------------------------------|
| Outils de développement       | Simple à installer, mais peut manquer de certains outils natifs | Environnement natif pour les outils web, beaucoup de gestion par ligne de commande |
| Compatibilité avec les serveurs | Peut être limité (Apache, nginx)                     | Serveurs web natifs (Apache, nginx) et outils comme MySQL/MongoDB mieux supportés |
| Performance                    | Moins optimisé pour les environnements de développement serveur | Meilleure performance pour les applications web |
| Courbe d'apprentissage         | Plus facile pour les débutants                      | Plus de configuration et gestion via terminal  |
| Compatibilité logicielle       | Compatible avec des logiciels propriétaires Windows (Photoshop, etc.) | Moins de compatibilité avec des logiciels propriétaires Windows |
| Environnement de production    | Différent des serveurs web en production (généralement Linux) | Plus proche des environnements de production |


## 2. Installation de WSL

### Étape 1 : Activer WSL sur Windows
Ouvrir PowerShell en mode administrateur et exécuter :
```powershell
wsl --install
```
Pour mettre à jour :
```powershell
wsl --set-default-version 2
```
Redémarrer l'ordinateur si nécessaire.

### Étape 2 : Installer une distribution Linux
Ouvrir le Microsoft Store et installer **Ubuntu**.

### Étape 3 : Initialiser WSL
Lancer WSL via le terminal et configurer un utilisateur Linux.

## 3. Configuration de l'environnement de développement

### Installation d'Apache
```bash
sudo apt update && sudo apt upgrade
sudo apt install apache2
sudo service apache2 start
```
Accéder à `http://localhost` pour vérifier le fonctionnement.

### Installation de PHP
```bash
sudo apt install php libapache2-mod-php
sudo service apache2 restart
```
Créer un fichier `/var/www/html/info.php` :
```php
<?php
phpinfo();
?>
```
Accéder à `http://localhost/info.php`.

### Installation de MariaDB
```bash
sudo apt install mariadb-server
sudo service mariadb start
sudo mysql_secure_installation
```
Se connecter :
```bash
sudo mysql -u root -p
```

## 4. Installation de VSCode
1. Télécharger **Visual Studio Code** depuis [https://code.visualstudio.com/](https://code.visualstudio.com/).
2. Installer l'extension **Remote - WSL** pour éditer des fichiers directement sous WSL.

## 5. Développement Web avec WSL

### Création d'un projet Web
```bash
cd /var/www/html/
sudo mkdir mon_site
cd mon_site
```
Ouvrir le dossier avec VSCode.

### Travailler avec HTML, CSS, JS, PHP
Structure de projet :
```
/mon_site
  ├── index.html
  ├── style.css
  ├── script.js
  └── contact.php
```

### Connexion à MariaDB en PHP
```php
<?php
$servername = "localhost";
$username = "root";
$password = "ton_mot_de_passe";
$dbname = "ma_base_de_donnees";

$conn = new mysqli($servername, $username, $password, $dbname);
if ($conn->connect_error) {
    die("La connexion a échoué : " . $conn->connect_error);
}
echo "Connexion réussie!";
?>
```

## 6. Alternative : Installer WampServer sur Windows
Si tu préfères une solution Windows native :
1. Télécharger **WampServer** sur [https://www.wampserver.com/](https://www.wampserver.com/).
2. Installer et lancer WampServer.
3. Accéder à `http://localhost/` et `http://localhost/phpmyadmin/`.
4. Placer les fichiers dans `C:\wamp64\www\`.

## Conclusion
WSL est recommandé pour un environnement de développement plus proche de la production, tandis que WampServer est une alternative simple sous Windows.
