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

``` 
./palmares.py
```

### Sous Windows

Python 2.6 peut �tre t�l�charg� ici : http://www.python.org/ftp/python/2.6/python-2.6.msi

* lancer l'invite de commandes
* remonter dans le dossier C: gr�ce � la ligne de commande cd ".."
* aller dans le dossier d'installation python, par exemple
 ``` 
cd "Python34" 
```
si Python est install� dans C://Python34)
* entrer la ligne de commande 
```
python.exe palmares.py
```
(apr�s avoir mis tous les fichiers .py dans ce m�me r�pertoire)

### Ex�cution

L'outil demande de saisir ses identifiants sur l'espace du licenci�, le num�ro de licence du joueur concern� et la profondeur de la recherche. Le dernier classement calcul� affich� correspnd au classement calcul� pour le joueur demand�. 

Il est n�cessaire d'�tre connect� � Internet pendant toute l'op�ration.

### Interface graphique

Ex�cuter le fichier interface.py. Remplir les champs demand�s et cliquer sur le bouton. La sortie s'affichera dans la grosse boite blanche en-dessous.

Attention, l'interface est pleine de bugs.

## Limitations

Il est pour le moment :
* seulement en version alpha
* verbeux et peu esth�tique

## TODO list:
* am�liorer la GUI
* corriger les bugs de la GUI
* prise en compte des formats courts

## Copyright

This program is free software distributed under the terms of two licenses, the CeCILL-C license that fits European law, and the GNU Lesser General Public License. You can use, modify and/ or redistribute the software under the terms of the CeCILL-C license as circulated by CEA, CNRS and INRIA at the following URL http://www.cecill.info or under the terms of the GNU LGPL as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this program. If not, see http://www.gnu.org/licenses/.

The fact that you are presently reading this means that you have had knowledge of the CeCILL-C and LGPL licenses and that you accept their terms.

