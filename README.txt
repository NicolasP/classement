# Outil de r�cup�ration du classement de ses adversaires.

(c) Camille Coti, 2013

## Syst�me de calcul

Le syst�me classement de tennis mis en place par la F�d�ration fran�aise de tennis calcule votre nouveau classement en fonction du classement de vos adversaires non pas au moment o� vous les avez battus, mais de leur calssement futur. Un 30 qui monte 15/3 comptera comme un 15/3 dans votre bilan. 

Pour faire ce calcul, la FFT effectue un gros calcul sur l'ensemble des comp�titeurs en deux passes :
* la premi�re passe a lieu en prenant en compte le classement actuel
* la deuxi�me passe a lieu en prenant en compte le classement calcul� par la premi�re passe
Cela n�cessite de calculer ces deux passes sur l'ensemble des comp�titeurs, ce qui repr�sente un volume de calcul consid�rable.

L'outil propos� ici permet d'aller r�cup�rer r�cursivement les palmar�s de vos adversaires, jusqu'� une certaine profondeur. Ainsi, l'outil effectue une approximation du futur classement de vos adversaires, gr�ce � une approximation du futur classement de leurs adversaires, etc. La r�cursion s'arr�te � un niveau d�fini par l'utilisateur. 

## Pr�requis

Il suffit de disposer d'un interpr�teur Python. Les biblioth�ques utilis�es sont incluses dans la distribution standard Python 2.6 ou fournies. On suppose ici que l'interpr�teur est situ� dans /usr/bin/python.

Les biblioth�ques fournies avec ce logiciel sont :

* gaecookie, qui permet d'utiliser plusieurs cookies � la fois (plusieurs champs Set-cookie dans l'en-t�te HTTP)
* keepalive : permet d'utiliser une connexion keep-alive avec la biblioth�ques urllib, qui normalement ne le permet pas

J'ai apport� une l�g�re modification � la biblioth�que keepalive : j'ai simplement supprim� les m�thodes relatives � HTTPS afin de supprimer la d�pendance vers la biblioth�que SSL.

## Utilisation

### Sous Unix (Mac OS, Lunix)

Dans un terminal, taper :

$ ./palmares.py

### Sous Windows

Python 2.6 peut �tre t�l�charg� ici : http://www.python.org/ftp/python/2.6/python-2.6.msi

Cliquez simplement sur palmares.py.

### Ex�cution

L'outil demande de saisie ses identifiants sur l'espace du licenci�, le num�ro de licence du joueur concern� et la profondeur de la recherche. Le dernier classement calcul� affich� correspnd au classement calcul� pour le joueur demand�. 

Il est n�cessaire d'�tre connect� � Internet pendant toute l'op�ration.

## Limitations

Il est pour le moment :
* seulement en version alpha
* incomplet (voir TODO list)
* uniquement en ligne de commande
* verbeux et peu esth�tique

## TODO list:
* prise en compte de la p�nalisation pour 5 WO et au-del� de 3 WO
* quand des num�rot�s entrent en compte, l'outil plante
* prise en compte de la bonif de championnat
* �crire une GUI
