# Projet pour apprendre la commande "git cherry-pick"

## Auteurs : Kénaël ROMERO, Arthur GUILLAUME, Samuel AVRIL

# Présentation GIT cherry-pick 

- Git Cherry-pick est une commande qui permet de sélectionner des commits Git arbitraires par référence et de les ajouter au HEAD de travail actuel. 

- Le Cherry Picking consiste à sélectionner un commit dans une branche et à l'appliquer à une autre.

- Git Cherry-pick peut être utile pour annuler des modifications ; par exemple, disons qu'une validation est accidentellement effectuée sur la mauvaise branche. Vous pouvez basculer vers la bonne branche et sélectionner le commit à l'endroit où il doit appartenir.

# Quand utiliser Git Cherry-pick ?

- Git Cherry-pick est un outil utile mais pas toujours pratique. 

- Git Cherry-pick peut entraîner des validations en double. Dans de nombreux scénarios, les fusions traditionnelles sont plutôt préférées.

- Cela dit, Git Cherry-pick est un outil pratique pour quelques scénarios...

# Comment utiliser Cherry-pick 

Pour démontrer comment utiliser Git Cherry-pick, supposons que nous ayons un référentiel avec l'état de branche suivant :

    a - b - c - d   Main
         \
           e - f - g Feature

- L'utilisation de Git Cherry-pick est simple et peut être exécutée ainsi :

`git cherry-pick commitSha`

- Dans cet exemple, commitSha est une référence de commit. Vous pouvez trouver une référence de commit en utilisant la commande : `git log`

- Dans cet exemple, nous avons construit, disons que nous voulions utiliser le commit `f` dans `main`. Nous nous assurons d’abord que nous travaillons sur la branche `main`.

`git checkout main`

- Ensuite, nous exécutons Cherry-pick avec la commande suivante :

`git cherry-pick f`

- Une fois exécuté, notre historique Git ressemblera à :

    a - b - c - d - f   Main
         \
           e - f - g Feature

- Le commit `f` a été sélectionné avec succès dans la branche `main`.

# Plusieurs exemples d'utilisation de Git Cherry-pick 

- La commande `git cherry pick` peut également recevoir certaines options d'exécution.

`-edit`

- En utilisant l'option `-edit`, git demandera un message de validation avant d'appliquer l'opération de la sélection :

`--no-commit` 

- L'option `--no-commit` exécutera le Cherry pick, mais au lieu de faire un nouveau commit, elle déplacera le contenu du commit cible dans le répertoire de travail de la branche actuelle.

`--signoff`

- L'option `--signoff` ajoutera une ligne de signature « signoff » à la fin du message de validation sélectionné.

- De plus, Git Cherry pick accepte également la saisie d'options pour la résolution de conflits de fusion, cela inclut les options : `--abort --continue` et `--quit`. 
















