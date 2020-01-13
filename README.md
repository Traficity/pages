Contrôle de Trafic Urbain
=========================

>   Traficity est un contrôle de trafic urbain nouvelle génération.

Mise en situation :
-------------------

Notre situation se passe en ville, a un carrefour, Traficity doit gérer
plusieurs carrefours avec différents matérielle, le tout avec : une Base de
données, un superviseur qui peut changer le mode de fonctionnement (mais pas en
crée) et un Technicien de maintenance qui crée les cycles de feu.

**Le projet est séparé en 3 Tache :**

Création des commandes de contrôle de la Maquette Electrome – avec les
différents modes.  
Création des commandes de contrôle de la Maquette Schneider – avec les
différents modes.  
Mise en place base de données – gestion carrefours et cycles – contrôle du mode
manuel.

**Les modes de fonctionnement de chaque maquette :**

Mode maintenance, les feux clignote orange ou éteints (priorité à droite).  
Mode Automatique (autonome), selon le cycle (pré-enregistré) et l’ordre de
démarrage (), peut changer via un message.  
Mode Manuel (piloté), la centrale contrôle manuellement les feux (dangereux).

Matériel :
----------

-   Raspberry Pi 3 B+

-   Arduino méga 2526

-   Arduino Ethernet Shield

-   Maquette gescar3 Electrome

-   Maquette md1ae214 Schneider

Contraintes :
-------------

UML
===

IHM
===

Test Unitaire
=============
