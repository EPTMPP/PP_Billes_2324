# PP_BILLES_2324

Bienvenue dans PP_BILLES_2324, le processus informatique tournant sur le projet d'étude de la passerelle pratique vers la HES. Ce Processus antérieur a été complètement refabriquer depuis le début afin d'atteindre nos objectifs : 

- Diminution d'appareils dans le système
- Diminution du câblage
- facilité d'utilisation

## Description du processus 

Le système actuel fonctionne avec un seul châssis master (surnomé "châssis Turtle") par salle d'expostion. Antérieurement, châque châssis du système à bille avait son propre NUC, châque cellule avait son raspberry. Dans le système actuel, le châssis Master comporte l'unique NUC. et il n'y a plus qu'un seul raspberry par châssis. Ces changements ont été réalisés dans un objectif de centralisation de la partie informatique. 

Au démarrage, tout les châssis y compris le master sont alimentés. Les raspberrys s'allument et par défault lancent le programme "HermesEnLighteNed.py". Le NUC lance directement le serveur de l'interface web, en parallèle un compte à rebour de 30 secondes est lancé avant d'exécuter la suite des programmes. Le timer a été mis en place pour attendre que l'interface web est bien lancé avant d'éxécuter les programmes qui en dépendent. 

Après les 30 secondes, le programme "RaspQuickLaunch.py" kill les processus actuels sur les raspberrys et envois les programmes du raspberry vers les raspberrys, ceci sont stockés dans le NUC dans un fichier GIT garantissant que les raspberrys tournent avec le dernier process à jour. 

La fin du programme RaspQuickLaunch relance les processsus avec les derniers fichiers "HermesEnLighteNed.py" et "configHermes.json" en particulier. 

Quand RaspQuickLaunch se termine, le programme "WatchDogeSupercharged.py" est exécuté sur le NUC, celui ci est le cerveau de tout se projet il récupère les informations des APIs et les transmets entre les châssis.


## Fonctionnalités

- **CommunicationAPIS7.py** : Gère les interactions complexes avec les API avec la libraire Snap7 python.
- **HermesEnlighteNed.py** : Module avancé de traitement et d'analyse de données des APIs.
- **RaspFullSetup.py** : Automatise le processus de configuration pour les appareils Raspberry Pi.
- **RaspQuickLaunch.py** : Fournit des configurations rapides pour Raspberry Pi.
- **WatchDogeSupercharged.py** : Un système robuste de surveillance et d'alerte permettant l'interaction sans-fil entre les châssis.
- **ip_addresses.py** : Utilitaire pour gérer et suivre dynamiquement les adresses IP.
- **variablesAPI.py** :  Assignation du nom commun des variables aux adresses physique dans les automates

## Fichiers de configuration

- **configDoge.json** : Paramètres de configuration pour le module WatchDogeSupercharged.
- **configHermes.json** : Paramètres pour le module HermesEnlighteNed.

## Démarrage rapide

1. Clonez le dépôt :

   ```bash
   git clone https://github.com/EPTMPP/PP_Billes_2324
   ```

## Contribution

Les contributions permet le travail en simultané sur cette espace de travail. Par simplicité, le chef de l'équipe Net and Light possède les logins pour ce repo GIT. Les autres membres devront créer un compte, si ils n'en ont pas déjà un. Voici comment les membres de l'équipe doivent configurer leur espace de travail :

1. Forkez le projet
2. Créez votre branche de fonctionnalités (`git checkout -b feature/FeatureIncroyable`)
3. Commitez vos changements (`git commit -m 'Ajouter une FeatureIncroyable'`)
4. Poussez vers la branche (`git push origin feature/FeatureIncroyable`)
5. Ouvrez une Pull Request

Ces commandes ne devraient généralement jamais être utilisé, le logiciel Visual Studio Code permet ces communications de manière natif et facile d'utilisation. Dans le doute des fichiers Tuto ont été généré dans le OneDrive de notre année.

Le chef Net and Light vérifie les pull requests sur la page GitHub et les accepts si ils sont corrects. 

Par sécurité je vous conseil de directement créer un branche à part et de travailler sur celle-ci et d'envoyer les versions stables sur le main.


## Licence

Distribué sous la licence MIT. Voir le fichier `LICENSE` pour plus d'informations.

## Chef suprême

Sebastian Morsch - sebastian.morsch@edu.vs.ch

## Sous Sous Chef

Louis Schanen - louis.schanen@edu.vs.ch

## Dessinateur de Chat

Quelqu'un de très peu important (Nieh)

## Responsable backoffice

Keenan Prusse - keenan.prusse@edu.vs.ch

## Architecte de l'interface web

Gaëtan Veuillet - gaetan.veuillet@edu.vs.ch

## Stagiaire de la base de donnée

Benno Weber - benno.weber@edu.vs.ch

## Responsable qualité

Julien Roduit - julien.roduit@edu.vs.ch

## Lien du projet

Lien du projet : [[https://github.com/Sebastian0211-vs/GitPP2324](https://github.com/Sebastian0211-vs/GitPP2324)]
