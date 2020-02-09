# TP1Admin

## Exercice n°1
## Exercice n°2 
* __Utilisation du Manuel__

* *1. A l’aide du manuel, identifiez le rôle de la commande **which***

La commande **which** nous affiche l'emplacement d'une commande passée en argument.

* *2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de **which** ?*

Pour rechercher un terme, on utilise `/terme a rechercher` par exemple `/options` pour chercher le mot option.

*3. Comment quitte-t-on le manuel ?*

On quitte le manuel en appuyant qur la touche "Q" comme écrit en bas de la fenêtre.

*4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?*

On tape : ` man 6 intro ` pour afficher la première page, la section 6 présente des petits programmes amusants présents sur le système.

 
* __Navigation dans l’arborescence des fichiers__

*1. allez dans le dossier `/var/log`*

`cd /var/log`.

*2. remontez dans le dossier parent (`/var`) en utilisant un chemin relatif*

`cd .."`.

*3. retournez dans le dossier personnel*

`cd .."`.
`cd home/verad`.

*4. . revenez au dossier précédent (`/var`) sans utiliser de chemin*

`cd -`.

*5. essayez d’accéder au dossier `/root` ; que se passe-t-il ?*

Nous n'avons pas la permission d'y accèder.

*6. essayez la commande **sudo cd /root** ; que se passe-t-il ? Expliquez*

cd est une commande intégrée et non un programme, or `sudo` ne s'applique qu'aux programmes, le shell cherche alors un programme appelé "cd", mais il n'en trouve pas.

*7. à partir de votre dossier personnel, créez l’arborescence suivante :*
```shell

sudo mkdir Dossier1
sudo mkdir -p Dossier2/Dossier2.1
sudo mkdir -p Dossier2/Dossier2.2
sudo chown -R verad:verad /home/verad

```
puis en se plaçant dans les bons dossiers, on crée les fichiers comme ceci : `cat > FichierX.txt`.


*8. revenez dans votre dossier personnel ; à l’aide de la commande **rm**, essayez de supprimer Fichier1, puis
Dossier1 ; que se passe-t-il ?*

**rm** supprime bien les fichiers, mais ne fonctionne pas sur les repertoires. **rm** ne supprime donc pas Dossier1.

*9. quelle commande permet de supprimer un dossier ?*

`sudo rmdir NOMDUDOSSIER` permet de supprimer un dossier vide.

*10. que se passe-t-il quand on applique cette commande à Dossier2 ?*

Il ne se passe rien car **rmdir** ne supprime que des dossiers vides.

*11. comment supprimer en une seule commande Dossier2 et son contenu ?*

`sudo rm -r Dossier2` supprime de manière récursive tous les fichiers contenus dans Dossier2 ainsi que les dossier lui-même.

* __Commandes importantes__

*1. Quelle commande permet d’afficher l’heure ? A quoi sert la commande **time** ?*

`date +%R` affiche l'heure
`date` affiche la date, l'heure et le fuseau horaire
**time** : permet de chronometrer une tâche, par exemple : `time ls -aRl` qui affiche le temps réel, le temps utilisateur et le temps système.


*2. Dans votre dossier personnel, tapez successivement les commandes **ls** puis **la** ; que peut-on en déduire
sur les fichiers commençant par un point ?*

Avec **ls** on ne voit pas les fichiers dont le nom commence par un point, **la** affiche tout le repertoire.

*3. Où se situe le programme **ls** ?*

Avec `which ls` on voit que ls se situe dans  `usr/bin/ls`.

*4. Essayez la commande **ll**. Existe-t-il une entrée de manuel pour cette commande ? Utilisez les commandes **alias** pour en savoir plus sur la nature de cette commande.*

Il n'y a pas d'entrée manuel pour **ll**.
**ll** est un alias pour `ls -alF`.

*5. Quelle commande permet d’afficher les fichiers contenus dans le dossier `/bin` ?*

On utilise : `ls /bin`

*6. Que fait la commande `ls ..` ?*

`ls ..` Affiche ce qui est contenu dans le dossier parent au repertoire courant.

*7. Quelle commande donne le chemin complet du dossier courant ?*

`pwd`
 
* __Commandes relatives aux fichiers__

*8. Que fait la commande `echo 'yo' > plop` exécutée 2 fois ?*

Executée deux fois, elle crée d'abord un fichier txt vide nommé "plop", puis elle y écrit "yo\n".


*9. Que fait la commande `echo 'yo' >> plop` exécutée 2 fois ?*

executée deux fois, elle crée d'abord un fichier txt avec "yo\n" ecrit, puis elle y écrit encore "yo\n".


*10. A quoi sert la commande **file** ? Essayez la sur des fichiers de types différents.*

**file** permet de determiner le type d'un fichier et certaines informations.



*11. Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier
avec la commande **ln toto titi**. Modifiez à présent le contenu de toto et affichez le contenu de titi :
qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?*

```shell

echo 'Hello Toto !' >> toto
ln toto titi
echo 'He will not divide us' >> toto
cat titi 

```
Le contenu de titi a aussi été mofidié.
Après la suppression, titi existe encore avec le même contenu.

*12. Créez à présent un lien symbolique tutu sur titi avec la commande **ln -s titi tutu**. Modifiez le
contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle
conséquence cela a-t-il sur tutu ?*

Lorsqu'on modifie titi, tutu est modifié aussi et inversement.
Lorsqu'on supprime titi, tutu est supprimé aussi.

 
* __Affichage et manipulation de fichiers__

*13. Affichez à l’écran le fichier `/var/log/syslog`. Quels raccourcis clavier permettent d’interrompre et
reprendre le défilement à l’écran ?*
Ctrl+S arrête le défilement à l’écran.
Ctrl+Q reprend le défilement à l’écran.


*14. Affichez les 5 premières lignes du fichier `/var/log/syslog`, puis les 15 dernières, puis seulement les
lignes 10 à 20.*

`head -5 /var/log/syslog`
`tail -15 /var/log/syslog`
`head -n 10 /var/log/syslog | tail -n 10`


*15. Que fait la commande **dmesg | less** ?*

`dmesg | less` permet d'afficher "dmesg" mais d'en controler le défilement.


*16. Affichez à l’écran le fichier `/etc/passwd` ; que contient-il ? Quelle commande permet d’afficher la page
de manuel de ce fichier ?*

Il contient les informations des utilisateurs.
`man /etc/passwd` permet d'acceder la page manuel de ce fichier. 


*17. Affichez seulement la première colonne triée par ordre alphabétique inverse*
`awk -F '{ print $1| "sort -r"}' /etc/passwd`
`print $1` permet d'afficher la premiere colonne, `"sort -r"` permet de la trier dans l'ordre alphabétique inverse.

*18. Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?*

`awk -F '{ print $1}' /etc/passwd`

*19. Combien de pages de manuel comportent le mot-clé conversion dans leur description ?*

On utilise : `man -k conversion`, il y en a 4.

*20. A l’aide de la commande **find**, recherchez tous les fichiers se nommant "passwd" présents sur la machine*

On utilise : `sudo find / -name passwd`

*21. Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier
`~/list_passwd_files.txt` et que les erreurs soient redirigées vers le fichier spécial `/dev/null`*

On utilise : `sudo find 2> /dev/null >list_passwd_files.txt / -name passwd` , 
`2> /dev/null` permet de diriger le buffer d'erreurs vers le fichier spécial `/dev/null` et `>list_passwd_files.txt` permet d'ecrire la sortie de la commande dans le fichier list_passwd_files.txt.

*22. Dans votre dossier personnel, utilisez la commande **grep** pour chercher où est défini l’alias ll vu
précédemment*

`sudo grep 'll' /home/verad`

*23. Utilisez la commande **locate** pour trouver le fichier `history.log`.*

`sudo install mlocate
locate history.log`

voici le chemin vers le fichier `history.log` : `/var/log/apt/history.log`.

*24. Créer un fichier dans votre dossier personnel puis utilisez **locate** pour le trouver. Apparaît-il ? Pourquoi ?*
 
 Il n'est pas trouvé car il ne fait pas partie de la base de données des fichiers indexés.

## Exercice n°3

* __L'éditeur de texte nano__

*1. Copiez le fichier `/var/log/syslog` dans votre dossier personnel sous le nom `log.txt`, puis ouvrez-le avec
nano*

^R `/var/log/syslog.txt` et ^O `/home/verad log.txt`,
puis on se place dans notre dossier personnel,
puis `nano log.txt`.


*2. Remplacez toutes les occurrences du mot kernel par le mot noyau*

^\ on écrit "kernel" puis on appuie sur Enter puis "noyau"


*3. Déplacer les 10 premières lignes à la fin du fichier*

On sélectionne les 10 premières lignes avec shift et en déplaçant le curseur avec les flèches directionnelles puis ^K (pour couper), ^_ ^V et ^U (pour coller)


*4. Annulez cette action*

Pour annuler cette action : on fait Alt + U 2 fois de suite 

*5. Enregistrez le fichier avant de quitter nano*
 
 On fait : ^S ou ^X et "valider l'enregistrement"

 
## Exercice n°4

1. Commencez par créer une copie de ce fichier, que vous appellerez .bashrc_bak 

On utilise la commande  `cp .bashrc .bashrc_bak`

2. Editez le fichier .bashrc avec nano et décommentez la ligne force_color_prompt=yes pour activer la couleur. Enregistrez le fichier et quittez nano.

`nano .bashrc`
Puis on trouve la ligne et on la décommente (enlever le \#).

3. Le fichier .bashrc est lu au démarrage du shell; pour le recharger, il faudrait donc se déconnecter puis se reconnecter; mais il existe un autre moyen : la commande source .bashrc. Testez-la, l’invite de commande devrait immédiatement passer en couleurs.

On utilise `source .bashrc`

4. Modifiez l’invite de commande

On obtient ![](https://cdn.discordapp.com/attachments/489454553108840453/676084983915347968/unknown.png)
