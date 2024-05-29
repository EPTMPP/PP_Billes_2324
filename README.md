# PP_BILLES_2324

Bienvenue dans PP_BILLES_2324, le projet informatique de la passerelle pratique vers la HES. Ce processus a été entièrement refabriqué pour atteindre nos objectifs :

- Réduction du nombre d'appareils dans le système
- Diminution du câblage
- Amélioration de la facilité d'utilisation

## Description du processus

Le système actuel fonctionne avec un seul châssis maître (surnommé "châssis Turtle") par salle d'exposition. Auparavant, chaque châssis du système à billes avait son propre NUC, et chaque cellule avait son Raspberry Pi. Dans le système actuel, le châssis maître comporte l'unique NUC et il n'y a plus qu'un seul Raspberry Pi par châssis. Ces changements ont été réalisés dans un objectif de centralisation de la partie informatique.

Au démarrage, tous les châssis, y compris le maître, sont alimentés. Les Raspberry Pi s'allument et, par défaut, lancent le programme "HermesEnLighteNed.py". Le NUC lance directement le serveur de l'interface web, en parallèle un compte à rebours de 30 secondes est lancé avant d'exécuter la suite des programmes. Ce délai a été mis en place pour attendre que l'interface web soit bien lancée avant d'exécuter les programmes qui en dépendent.

Après les 30 secondes, le programme "RaspQuickLaunch.py" tue les processus actuels sur les Raspberry Pi et envoie les programmes du NUC vers les Raspberry Pi. Ces programmes sont stockés dans un dépôt Git sur le NUC, garantissant que les Raspberry Pi utilisent la dernière version du processus.

À la fin de "RaspQuickLaunch.py", les processus sont relancés avec les derniers fichiers "HermesEnLighteNed.py" et "configHermes.json". Une fois "RaspQuickLaunch" terminé, le programme "WatchDogeSupercharged.py" est exécuté sur le NUC. Celui-ci est le cerveau de tout le projet, récupérant les informations des API et les transmettant entre les châssis.

## Fonctionnalités

- **CommunicationAPIS7.py** : Gère les interactions complexes avec les API en utilisant la librairie Snap7 pour Python.
- **HermesEnLighteNed.py** : Module avancé de traitement et d'analyse de données des API.
- **RaspFullSetup.py** : Automatise le processus de configuration pour les appareils Raspberry Pi.
- **RaspQuickLaunch.py** : Fournit des configurations rapides pour Raspberry Pi.
- **WatchDogeSupercharged.py** : Système robuste de surveillance et d'alerte permettant l'interaction sans fil entre les châssis.
- **ip_addresses.py** : Utilitaire pour gérer et suivre dynamiquement les adresses IP.
- **variablesAPI.py** : Assignation des noms communs des variables aux adresses physiques dans les automates.

## Fichiers de configuration

- **configDoge.json** : Paramètres de configuration pour le module WatchDogeSupercharged.
- **configHermes.json** : Paramètres pour le module HermesEnLighteNed.

## Démarrage rapide

1. Clonez le dépôt :

   ```bash
   git clone https://github.com/EPTMPP/PP_Billes_2324
   ```

## Contribution

Les contributions permettent un travail collaboratif sur cet espace de travail. Par simplicité, le chef de l'équipe Net and Light possède les identifiants pour ce dépôt Git. Les autres membres doivent créer un compte s'ils n'en ont pas déjà un. Voici comment les membres de l'équipe doivent configurer leur espace de travail :

1. Forkez le projet
2. Créez votre branche de fonctionnalité (`git checkout -b feature/FeatureIncroyable`)
3. Commitez vos changements (`git commit -m 'Ajouter une FeatureIncroyable'`)
4. Poussez vers la branche (`git push origin feature/FeatureIncroyable`)
5. Ouvrez une Pull Request

Ces commandes sont généralement simplifiées grâce à Visual Studio Code, qui permet ces communications de manière native et facile d'utilisation. Des fichiers de tutoriels sont disponibles sur le OneDrive de notre année en cas de doute.

Le chef Net and Light vérifie les pull requests sur la page GitHub et les accepte si elles sont correctes.

Par sécurité, il est conseillé de créer une branche séparée pour travailler et d'envoyer les versions stables sur la branche principale.

## Licence

Distribué sous la licence MIT. Voir le fichier `LICENSE` pour plus d'informations.

## Équipe

- **Gourou Net and Light** : Sebastian Morsch - sebastian.morsch@edu.vs.ch
- **Sous-Gourou** : Louis Schanen - louis.schanen@edu.vs.ch
- **Soutien Moral** : Quelqu'un de très peu important (Nieh)
- **Responsable backoffice** : Keenan Prusse - keenan.prusse@edu.vs.ch
- **Architecte de l'interface web** : Gaëtan Veuillet - gaetan.veuillet@edu.vs.ch
- **Stagiaire base de données** : Benno Weber - benno.weber@edu.vs.ch
- **Responsable qualité / maître de la lumière** : Julien Roduit - julien.roduit@edu.vs.ch

## Lien du projet

.[https://github.com/EPTMPP/PP_Billes_2324](https://github.com/EPTMPP/PP_Billes_2324)
