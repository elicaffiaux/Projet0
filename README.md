Rapport du projet 0

Nous avons commencé par créer les paquets de 32 et 52 cartes

Code : ![](img\32cartes.JPG)
       ![](img\52cartes.JPG)

Ensuite, nous avons demander au joueur si “OUI” ou non, il avait besoin d’aide

Code : ![](img\aide.JPG)

}

Nous demandons quel paquet le joueur souhaite utiliser. Tant que sa réponse ne correspond pas à l’une des valeurs proposées, la question est reposée

Code : ![](img\demanderCombien.JPG)
       ![](img\redemanderCombien.JPG)
       


La partie commence, nous demandons le nom, puis la couleur que le joueur souhaite tenter

Code : ![](img\partieCommence.JPG)

S’il y a une mauvaise définition des cartes (ou valeur nulle), on l’indique et on propose de réessayer  :

![](img\mauvaiseDef.JPG)

S’il n’y a pas d’erreur de définition, on regarde si la ”carteDuJoueur” correspond à la carte à deviner

Code : ![](img\bonneCarte.JPG)
![](img\carteProposee.JPG)

Si le joueur a deviné la carte, un message s’affiche et le jeu s’arrête

Résultat :  ![](img\carteTrouvee.JPG)

S’il ne l’a pas trouvé, un message s’affiche ; et on lui indique si sa carte est inférieure ou supérieure à la carte à trouver (S’il a demandé de l’aide) 

Résultat :  ![](img\carteNonTrouvee.JPG)

La carte a deviner se change à chaque partie lancée :

Code : 

![](img\Random.JPG)

Voici le diagramme final :

![](img\diagramme.JPG)

@startuml
start


:demander si activation aide assistance;
if(aide) equals (?) then
:oui;
else (?)
:non;
endif
while (demander quel jeu de cartes)
:erreur le paquet de cartes n'existe pas;
endwhile
:32 ou 52;
repeat :intialisation du jeu;
:demander nom de carte
demander couleur de carte;
if ( ?) equals (la carte à deviné a été trouvé) then
:fin de la partie;
stop
else (la carte à deviné n'a pas été trouvé)
if(aide) equals (oui) then
:informer si la carte à deviner est plus grande ou plus petite que la carte choisis ;
else (non)
endif
if(demander si vous souhaitez connaitre la carte) equals (oui) then
:on vous donne la carte à deviné;
:fin de la partie;
stop
else (non)
:demander si vous souhaitez abandonner;
endif
if(abandon) equals (oui) then
:fin de la partie;
stop
else (non)
:recommence;
endif
@enduml