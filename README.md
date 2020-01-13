Contrôle de Trafic Urbain
=========================

>   Traficity est un contrôle de trafic urbain nouvelle génération.

Mise en situation :
-------------------

Notre situation se passe en ville, a un carrefour, Traficity doit gérer
plusieurs carrefours avec différents matérielle, le tout avec : une Base de
données, un superviseur qui peut changer le mode de fonctionnement (mais pas en
crée) et un Technicien de maintenance qui crée les cycles de feu.

Bien entendu le tout doit respecter le code de la route.

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

Scenarii :
----------

### Client :

**Scenario 1: Identification**

Le superviseur démarre l'application de supervision. Il entre ses identifiants
et clique sur le bouton « connexion ». *post-condition :* Il a accès aux
fonctionnalités de l'application de supervision.

**Scenario 2: Ajout d'un cycle** *pré-condition :* Le superviseur est identifié.
Il clique sur l'onglet « cycles ».

Il clique sur le bouton « Ajout d'un cycle ».

Il sélectionne la topologie du carrefour, par exemple « en X ».

Il sélectionne un type de cycle, par exemple « en 4 phases ».

Il affecte les durées pour chaque feux.

Il valide en cliquant sur le bouton « Enregistrer ». *post-condition :* Le cycle
est créé dans la base de données.

**Scenario 3: Configurer le mode de fonctionnement** *pré-condition :* Le
superviseur est identifié. Il clique sur le bouton « mode de fonctionnement » Il
sélectionne un carrefour.

Il sélectionne le mode de maintenance.

*post-condition :* Le carrefour est bien en mode de maintenance.

**Scenario 4: Effectuer maintenance** *pré-condition :* Le carrefour a été placé
en mode maintenance par le superviseur.

L'opérateur de maintenance se rend sur le lieu du carrefour.

Il se raccorde au module contrôleur (arduino ou raspberry pi). Il peut tester
chaque entrée ou sortie du carrefour.

**Scenario 5: Programmer les cycles** *pré-condition :* Le carrefour a été placé
en mode maintenance par le superviseur.

Le superviseur a créé un nouveau cycle pour le carrefour.

L'opérateur de maintenance se rend sur le lieu du carrefour.

Il se raccorde au module contrôleur (arduino ou raspberry pi).

Il transfère le nouveau cycle sur le contrôleur.

Il lance le nouveau cycle implanté.

*post-condition :* Le cycle est visible sur les feux tricolores.

### Développeur :

Rasp
----

Ardui
-----

jesaispaencore
--------------

IHM
===

Test Unitaire
=============
