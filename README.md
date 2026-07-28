# OC-ASRS-Projet-4-Deployez-une-architecture-n-tiers-pour-une-PME
OpenClassrooms : Administrateur Systèmes, Réseaux et Sécurité 2024-2025
------------------------------------------------------------------------------------------------------
Qu'allez-vous apprendre dans ce projet ?
Votre mission consiste à configurer et déployer trois serveurs distincts : un pour Apache et PHP, un pour MySQL, et un pour Bind9. Vous allez commencer par déployer ces services, en créant d'abord la base de données et en configurant les connexions entre les différents services. Ensuite, vous configurerez le site web pour qu'il puisse interagir correctement avec la base de données. Vous choisirez entre plusieurs technologies, telles que des VM, Vagrant ou Docker, pour mettre en œuvre cette architecture, en fonction de ce qui sera le plus efficace pour votre environnement. Enfin, vous documenterez l'ensemble du processus et créerez un schéma détaillé de l'architecture qui sera utilisé par l'équipe d'exploitation pour maintenir le système.

 

En quoi ces compétences sont-elles importantes pour votre carrière ?
La mise en place d'une architecture 3-tiers est une compétence fondamentale pour tout administrateur système souhaitant garantir la sécurité, la performance et la maintenabilité des applications web. Vous apprendrez non seulement à configurer des serveurs dans un environnement de production, mais aussi à documenter de manière détaillée l'architecture mise en place, permettant une meilleure compréhension et gestion par l'équipe d'exploitation. Ces compétences sont essentielles pour assurer la continuité des opérations et supporter efficacement la croissance de l'entreprise.

 

Prêt à démarrer votre projet ?
Vous allez réaliser un projet réaliste, présenté sous forme de mission en entreprise. Il se rapproche d' une mission typique effectuée sur le terrain.

Le projet est découpé en trois sections :

Mission - Présentation, qui présente le contexte de votre mission,
Mission - Détails, qui présente les détails de la mission, sous forme d’échanges avec les collègues,
Livrables et Soutenance, qui décrit les livrables à fournir et le déroulement de la soutenance de validation.
Prenez soin de lire le projet en entier avant de commencer, pour comprendre ce qui est attendu de vous.
--------------------------------------------------------------------------------------------------------
Mission - Présentation
Bannière de scénario
Vous travaillez actuellement chez BeeSafe, une startup d’assurance, en tant qu’administrateur systèmes et réseaux. Vous faites partie de l’équipe qui gère l’exploitation des sites web de la startup. Vous êtes responsable de la mise à disposition de leurs moyens informatiques, ainsi que du maintien en condition opérationnelle de leur infrastructure.


 

Un nouveau site web basé sur des technologies open source va être déployé, et il a été choisi de l’installer via une architecture 3-tiers pour faciliter le déploiement. Votre rôle est de mettre en place toute l’infrastructure qui hébergera les 3 services de cette architecture.
--------------------------------------------------------------------------------------------------------
Mission - Détails
Vous recevez un mail de Marie Picard, votre contact à l’agence web, qui vous livre la première version du site.

De : Marie Picard
À : Arthur Bouhier, Vous
Objet : Livraison du site web

Bonjour,

 

Vous trouverez dans la branche master de ce repository la première version de votre nouveau site web.

Celui-ci utilise la stack LAMP traditionnelle pour fonctionner. Il faudra la répartir via une architecture 3-tiers :

une machine pour héberger le service web avec Apache et PHP ;
une machine pour héberger le service MySQL ;
et une machine pour héberger le service DNS avec Bind9 pour le référencer à l’adresse http://www.beesafe.co.
Cependant, sur cette première version, seul le site web sera fonctionnel.

 

La semaine prochaine, nous vous enverrons les scripts SQL de création de la base de données et des données.

 

Vous en souhaitant bonne réception,

 

Marie Picard

 

En attendant la livraison des scripts, vous commencez le déploiement du site sur la stack LAMP en architecture n-tiers.

 

1 semaine plus tard

 

Une semaine plus tard, vous recevez un nouveau mail de l’agence web qui vous livre les scripts SQL de création de la base de données, ainsi que les données du site web.

 

De : Marie Picard
À : Arthur Bouhier, Vous
Objet : Livraison des scripts SQL

 
Bonjour,

Vous trouverez, dans la branche “SQL” de ce repository, les scripts SQL de création des tables dans votre base de données, ainsi que les scripts SQL à jouer afin de remplir la base avec les données.

Vous en souhaitant bonne réception,

Marie Picard

 

Juste après, un nouveau message sur Slack d’Arthur, votre directeur technique :

 

Arthur : Hello, tu as vu le nouveau mail de Marie ? Du coup tu peux créer la base de données, puis un compte d’exploitation sur MySQL qui aura les accès CRUD à cette base, et enfin jouer les scripts de création de tables et d’insertion de données de l’agence. 

Il faudra ensuite configurer le site web avec les informations de connexion à MySQL pour que le site web puisse lire les informations de la base de données. 

Vous : OK, merci pour les infos, je vais m’occuper de ça. Tu me recommandes quoi comme stack technique ?

Arthur : L’architecture doit être déployée avec une stack LAMP. Tu peux la mettre en place avec des VM, mais si tu préfères tu peux aussi cloisonner les 3 services avec Vagrant ou avec des containers Docker. À toi de voir ce qui t’arrange. 

Il faudra aussi que je puisse voir la configuration que tu as choisie. Dès que c’est prêt, envoie-moi les fichiers de configuration du service DNS et du service HTTP, et les fichiers pour la création et la configuration de la base.

Vous : OK, je m’en occuperai. Ce serait peut-être bien de tout documenter, non ?

Arthur : Effectivement, j’allais t’en parler ! Une fois que tu auras fini l’installation, j’ai besoin que tu fasses un schéma de l’architecture du site avec les différents composants (Apache, PHP, MySQL, Bind9). Il faudra aussi indiquer sur le schéma les différents flux de connexion entre les composants, les ports et adresses IP utilisés et les différentes versions choisies, pour que l’équipe d’exploitation puisse mettre à jour le dossier d’exploitation. Merci  :)

Vous : Super clair, je m’occupe de ça.

 

Maintenant que votre site est déployé, vous pouvez créer la base de données et lancer les scripts SQL de création des données, ainsi que documenter votre architecture.
-------------------------------------------------------------------------------------------------------
Livrables et soutenance

Les fichiers de configuration DNS qui intègrent le nom de domaine, nommés au format txt, 
Les fichiers de configuration du service HTTPD (Apache) qui intègrent le virtual host hébergeant le site au format txt,
Le script SQL qui a permis de créer le compte d’exploitation de la base de données,
Le fichier de configuration des sources du prototype modifié pour intégrer les identifiants de connexion à la base de données,
Le schéma de l’architecture 3-tiers au format pdf. 
Pour faciliter votre passage devant le jury, déposez sur la plateforme, dans un dossier zip nommé “Titre_du_projet_nom_prénom”, tous les livrables du projet comme suit : Nom_Prénom_n° du livrable_nom du livrable_date de démarrage du projet. Cela donnera : 

Nom_Prénom_1_configuration_DNS_mmaaaa
Nom_Prénom_2_Configuration_HTTPD_mmaaaa
Nom_Prénom_3_script_SQL_mmaaaa
Nom_Prénom_4_configuration_sources_mmaaaa
Nom_Prénom_5_schema_architecture_mmaaaa
Par exemple, le premier livrable peut être nommé comme suit : Dupont_Jean_1_X_012022.

 

Durant la présentation orale, l’évaluateur interprétera le rôle du directeur technique. La soutenance est structurée de la manière suivante :

Présentation des livrables (15 minutes, sans nécessairement se baser sur des slides de présentation) 
Présentation et explication du schéma d’architecture du site web.
Présentation des fichiers de configuration DNS qui contiennent le nom de domaine du site web.
Présentation des fichiers de configuration du serveur web.
Présentation des scripts SQL servant à créer le compte d’exploitation de la base de données.
Présentation des fichiers de configuration complétés intégrant les identifiants de connexion à la base de données.
Discussion (10 minutes) 
L’évaluateur jouera le rôle du directeur technique. Il vous challengera sur les points suivants :
Configuration du serveur web.
Configuration du script PHP.
Configuration du serveur DNS.
Qualité du script SQL de création de la base de données et des droits associés.
Débriefing (5 minutes)
À la fin de la soutenance, l'évaluateur arrêtera de jouer le rôle du directeur technique pour vous permettre de débriefer ensemble.
