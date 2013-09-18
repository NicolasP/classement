Outil de r�cup�ration du classement de ses adversaires.

Le syst�me classement de tennis mis en place par la F�d�ration fran�aise de tennis calcule votre nouveau classement en fonction du classement de vos adversaires non pas au moment o� vous les avez battus, mais de leur calssement futur. Un 30 qui monte 15/3 comptera comme un 15/3 dans votre bilan. 

Pour faire ce calcul, la FFT effectue un gros calcul sur l'ensemble des comp�titeurs en deux passes :
- la premi�re passe a lieu en prenant en compte le classement actuel
- la deuxi�me passe a lieu en prenant en compte le classement calcul� par la premi�re passe
Cela n�cessite de calculer ces deux passes sur l'ensemble des comp�titeurs, ce qui repr�sente un volume de calcul consid�rable.

L'outil propos� ici permet d'aller r�cup�rer r�cursivement les palmar�s de vos adversaires, jusqu'� une certaine profondeur. Ainsi, l'outil effectue une approximation du futur classement de vos adversaires, gr�ce � une approximation du futur classement de leurs adversaires, etc. La r�cursion s'arr�te � un niveau d�fini par l'utilisateur. 

Il est pour le moment :
- seulement en version alpha
- incomplet (voir TODO list)
- uniquement en ligne de commande
- verbeux et peu esth�tique

TODO list:
- prise en compte de la p�nalisation pour 5 WO et au-del� de 3 WO
- quand des num�rot�s entrent en compte, l'outil plante
- prise en compte de la bonif de championnat
- �crire une GUI