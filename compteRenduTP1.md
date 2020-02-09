OVIGNE Adrien &	KLAAS Guillaume



MANUEL
 
1 renvoie l'emplacement d'une commande

2 on utilise "/terme a rechercher" par exemple /options pour chercher le mot option

3 en appuyant sur la touche "Q" comme écrit en bas de la fenêtre

4 "man 6 intro" pour afficher la première page, la section 6 présente des petits programmes amusants présents sur le système.

navigation

1 "cd /var/log"

2 "cd .."

3 "cd .." pour revenir dans le root ensuite"cd home/verad"

4 "cd -"

5 permission denied

6 command not found

7 "sudo mkdir Dossier1"
"sudo mkdir -p Dossier2/Dossier2.1"
"sudo mkdir -p Dossier2/Dossier2.2"
"sudo chown -R verad:verad /home/verad"
ensuite en se placant dans les bons dossiers : "cat >FichierX.txt"

8 rm supprime bien les fichiers, mais ne fonctionne pas sur les repertoires. rm ne supprime donc pas Dossier1. 

9 "sudo rmdir NOMDUDOSSIER"

10 ca ne marche pas car rmdir ne supprime que des dossiers vides
11 "sudo rm -r Dossier2"

Commandes
1 	"date +%R" affiche l'heure
	"date" affiche la date, l'heure et le fuseau horaire
time : permet de chronometrer une tâche : exemple "time ls -aRl" qui affiche le temps réel, le temps utilisateur et le temps système (https://www.math-linux.com/linux-2/commande-du-jour/article/chronometrer-une-tache-time)

2 avec ls on ne voit pas les fichiers dont le nom commence par un point, la affiche tout le repertoire.

3 "which ls" -> usr/bin/ls 

4 Pas d'entrée manuel pour "ll" 
"ll" est un alias pour "ls -alF"
5 
6 la commande "ls" affiche les informations sur ce qui est dans le repertoire courant et le classe par ordre alphabetique 
7 "pwd"

8executée deux fois, elle crée d'abord un fichier txt vide nommé "plop", puis elle y écrit "yo\n"

9executée deux fois, elle crée d'abord un fichier txt avec "yo\n" ecrit, puis elle y écrit encore "yo\n"

10 file permet de determiner le type d'un fichier et certaines informations.

11 'echo 'Hello Toto !' >> toto'
	"ln toto titi"
	"echo 'He will not divide us' >> toto"
	"cat titi" le contenu de titi a aussi été mofidié
	titi existe encore avec le même contenu
	
12 lorsqu'on modifie titi tutu est modifié aussi et inversement
	lorsqu'on supprime titi, tutu est supprimé aussi

13 ctrl S arrete
	ctrl Q reprend
 
14 head -5 /var/log/syslog
	tail -15 /var/log/syslog
	head -n 10 /var/log/syslog | tail -n 10
(https://forum.ubuntu-fr.org/viewtopic.php?id=224975)

15 "dmesg | less" permet d'afficher "dmesg" mais d'en controler le défilement 

16 affiche les informations des utilisateurs
	man /etc/passwd

17 awk -F '{ print $1| "sort -r"}' /etc/passwd

18 awk -F '{ print $1}' /etc/passwd

19 man -k conversion ->4

20 sudo find / -name passwd

21 sudo find 2> /dev/null >list_passwd_files.txt / -name passwd 

22 sudo grep 'll' /home/verad

23 sudo install mlocate
	locate history.log
	->/var/log/apt/history.log

24 il n'est pas trouvé car il ne fait pas partie de la base de données des fichiers indexés

NANO

1 ^R /var/log/syslog.txt et ^O /home/verad log.txt
puis " nano log.txt" (verad en répertoire courant)
2 ^\ on écrit "kernel" puis on appuit sur Enter puis "noyau"
 
3 On sélectionne les 10 premières lignes avec shift et en déplaçant le curseur avec les flèches directionnelles puis ^K (pour couper), ^_ ^V et ^U (pour coller)

4 Alt + U 2 fois de suite  

5 ^S ou ^X et valider l'enregistrement

PERSONNALISATION DU SHELL

1 

2 

3 

4 





