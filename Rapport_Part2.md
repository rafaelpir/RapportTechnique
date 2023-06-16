\

# Installation Debian automatisée par préconfiguration

## Informations Supplémentaires ![Informations supplémentaires]

Voici ci dessous quelques informations interresente sous forme d'une foire aux questions

 #. [__Qu’est-ce que le Projet Debian ? D’où vient le nom Debian ?__]{#deb}
 
    Le **"Porjet Debian"** est une Documentation facile d'accès pour les utilisateurs (Pour plus d'information sur Projet Debian : <https://www.debian.org/doc/>).Le nom Debian provient de la concatenation des noms **Debra**[^9] et **Ian Murdock**[^10] qui sont les fondateur du projet (Pour plus d'information sur l'origine du nom Debian : <https://www.debian.org/doc/manuals/debian-faq/basic-defs.fr.html#pronunciation>).

[^9]: Il s'agit du nom de la femme du créateur du projet
[^10]: Pour plus d'information sur Ian Murdock : <https://fr.wikipedia.org/wiki/Ian_Murdock>

 #. __Il existe 3 durées de prise en charge (support) de ces versions : la durée minimale, la durée en support long terme (LTS) et la durée en support long terme étendue (ELTS). Quelle sont les durées de ces prises en charge ?__
    
    Les durées de prise en charge des 3 durée sont :
    
    * la durée **minimale** pour une version Debian correspond à une prise en charge pour **3 ans minimum** pour chaque publication (Pour plus d'information sur la durée minimale d'une version Debian : <https://www.debian.org/releases/index.fr.html>)
    * la durée en **support long terme** (LTS) correspond à une durée de vie de **5 ans** (Pour plus d'information sur la durée en support long terme d'une version Debian : <https://www.debian.org/lts/index.fr.html>)
    * la durée en **support long terme étendue** (ELTS) correspond à une durée de vie de **10 ans** (Pour plus d'information sur la durée en support long terme étendue d'une version Debian : <https://wiki.debian.org/fr/LTS/Extended>)
 
 #. __Pendant combien de temps les mises à jour de sécurité seront-elles fournies ?__
 
    Les mises à jours de sécurité sont fournie **une année après que la version stable suivante a été publiée , sauf dans le cas où une autre distribution stable est publiée la même année** (Pour plus d'information sur le temps que les mises à jour de sécurité sont fournis : <https://www.debian.org/security/faq.fr.html#lifespan>).
 
 #. __Combien de version au minimum sont activement maintenues par Debian ?__
 
    Debian a au minimum **3 versions** activement maintenu , parmis elles , une **version "stable"** sous le nom de code Bullseye , une **version "testing"** sous le nom de code Bookworm , une **version "unstable"** sous le nom de code Sid (Pour plus d'information sur le maintient des version actives : <https://www.debian.org/releases/index.fr.html>).
 
 #. __D’où viennent les noms de code données aux distributions ?__

    Les nom de code données aux distribution **provient du responsable du projet Debian** qui travaillait chez Pixar et qui a choisi d'utiliser les **noms provenant de Toy Story** (Pour plus d'informations sur la provenance des noms de code Debian : <https://www.debian.org/doc/manuals/debian-faq/ftparchives.fr.html#sourceforcodenames>).
 
 #. __L’un des atouts de Debian fut le nombre d’architecture officiellement prises en charge. Combien et lesquelles sont prises en charge par la version Bullseye ?__
 
    **Debian prend en charge 9 architectures principale** et de nombreuses variantes avec Debian 11 : AMD64 & Intel 64 , Intel x86-based , ARM , ARM avec matériel FPU , ARM 64 bits , MIPS 64 bits (petit-boutien) , MIPS 32 bits (petit-boutien) , Power Systems , IBM S/390 64 bits . (Pour lus d'information sur les architectures pris en charge par Debian : <https://www.debian.org/releases/stable/arm64/ch02s01.fr.html>)
 
 #. __Première version avec un nom de code__
 
    * Quelle a était le premier nom de code utilisé ?
 
     Le premier nom de code utilisé fut **buzz** .
     
     * Quand a-t-il été annoncé ?
     
     Cette version est apparu le **26 avril 2004** .
     
     * Quelle était le numéro de version de cette distribution ?
     
     Il s'agit de la **version Debian 1.1** .
     
     Pour plus d'information sur le 1er nom de code et sa date d'apparution : <https://www.debian.org/doc/manuals/debian-faq/ftparchives.fr.html#sourceforcodenames>
     
     Pour plus d'information sur le numéro de la 1er version à avoir eu un nom de code : <https://www.debian.org/social_contract.1.1>
     
 #. __Dernière nom de code attribué__
 
    * Quelle a était le premier nom de code utilisé ?
 
     Le dernier nom de code annoncée à ce jour est **Forxy** .
     
     * Quand a-t-il été annoncé ?
     
     Il a été annoncé le **8/11/20** .
     
     * Quelle était le numéro de version de cette distribution ?
     
     La version de cette distribution est **Debian 14** .
     
     Pour plus d'information sur le dernier nom de code et la version correspondante : <https://wiki.debian.org/DebianReleases>
     
     Pour plus d'information sur la date d'annoncement de Debian 14 : <https://wiki.debian.org/DebianTrixie>
 
\
 
## Préconfiguration

 
Pour réaliser une installation automatiser , pour cela nous aurons besoin de récupréré et préparer les fichier nécessaires à notre automatisation . Pour commencer nous devons récuperer le fichier **autoinstall.zip** , décompressez le , et puis inserez le dans le répertoire de la machine. Avec les fichiers que l'on viens de récuperer , nous allons pouvoir avoir une préconfiguration minimal , à laquel nous allons ajouté les morceaux de configurations que l'on souhaite avoir à l'installation. Ainsi nous aurons principalent 2 fichier à modifier : **preseed.cfg** et **vboxpostinstall.sh** .

Parmis les deux fichiers cité précedement , **preseed.cfg**[^11] nous permettra de réaliser les configuration que l'on pouvait retrouver dans une installation manuelle , sous forme de liste d'ensemble d'informations et actions automatiser pour l'installation . Tandis que **vboxpostinstall.sh** est un fichier qui va plutot nous permettre de réaliser la configuration de notre bureau suite à l'installation du système d'exploitation.

[^11]: Pour plus de détails sur les divers posibilité de préconfiguration : <https://www.debian.org/releases/stable/amd64/apb.fr.html>

Ainsi pour commencer nous allons réaliser la préconfiguration du systeme d'exploitation , et ceux en allant dans le fichier **preseed.cfg** .
De la nous pourrons modifier par exemple , l'utilisateur standart et le super utilisateur . Ainsi si l'on veut par exemple **ajouter les droit de super utilisateur à l'utilisateur standart** , nous pouvons ajouté [**"sudo"**](#sudo) dans le groupe de l'utilisateur comme ci-dessous (**les groupes de l'utilisateur standart sont ici dans la dernière ligne**) :

```Bash
## Utilisateur standard
d-i passwd/user-fullname string User
d-i passwd/username string user
d-i passwd/user-password password user
d-i passwd/user-password-again password user
d-i passwd/user-default-groups string audio cdrom video sudo
```

Ensuite si nous souhaitons par exemple **avoir un environement de bureau** et non juste un terminal , nous pouvons ajouté comme dans l'exemple qui suit , [l'environement MATE](#mate) en ajouté **"mate-desktop"** comme dans la dernière ligne :

```Bash
## Installation meta-paquetages
# Tâches à installer (via des méta-paquetages)
#   Lister les possibilités : tasksel --list-task (en ligne de commande)
#   Utiliser au minimum "standard" est une bonne idée
tasksel tasksel/first multiselect standard ssh-server,mate-desktop
```

Une fois notre Système d'exploitation installer , nous pouvons passe à la suite en installant à présent tout ce dont on à besoin dans notre bureau. et pour cela on va à passer dans le fichier **vboxpostinstall.sh**[^12].

[^12]: Pour plus de détails sur ce qu'est ce fichier : <https://connect.ed-diamond.com/GNU-Linux-Magazine/glmfhs-045/une-installation-de-debian-automatique>

Ainsi si l'on souhaite par exemple **ajouter des paquets** , il vous suffit d'entrer la commande que vous auriez entrer dans un terminal depuis votre bureau mais avec écrit devant **"log_command_in_target"** , dans le fichier **vboxpostinstall.sh** comme suit :

```Bash
#
# Packages needed for GAs.
#
echo "--------------------------------------------------" >> "${MY_LOGFILE}"
echo '** Installing packages for building kernel modules...' | tee -a "${MY_LOGFILE}"
log_command_in_target apt-get -y install build-essential
log_command_in_target apt-get -y install linux-headers-$(uname -r)
log_command_in_target apt-get install --yes git-all
log_command_in_target apt-get install --yes sqlite3
log_command_in_target apt-get install --yes curl
log_command_in_target apt-get install --yes bash-completion
log_command_in_target apt-get install --yes neofetch
```

Ainsi dans l'exemple ci dessus , on installe de la **ligne 8 à 12** , les paquets suivant :

   * git
   * sqlite3
   * curl
   * bash
   * neofetch

\

## Installation automatisé

Maintenant que la préconfiguration est terminer , nous pouvons à présent passer à l'installation avec les fichiers préconfigurer au par avant. Pour commencer il va nous falloir **modifier identifiant unique universel**[^13] du fichier **S203-Debian11.viso** et ceux en se placant dans le répertoire de la machine virtuel que l'on à crée au par avant , puis d'executer la commande suivante : 

[^13]: Pour plus d'informations sur les identifiant unique universel : <https://fr.wikipedia.org/wiki/Universally_unique_identifier>

```Bash
sed -i -E "s/(--iprt-iso-maker-file-marker-bourne-sh).*$/\1=$(cat 
/proc/sys/kernel/random/uuid)/" S203-Debian11.viso
```

Ensuite, il ne vous suffit plus qu'à **inserez le fichier S203-Debian11.viso dans le lecteur** de la machine, et à lancez votre machine qui va ainsi s'installer automatiquement à son démarrage.
