# Projet de réingénierie
## LOG530 – Réingénierie du Logiciel
### Date de remise : 7 avril 2021 à 23h59

#### Table des matières
1. [Logiciel cible ](#logiciel)
2. [Contextualisation pour le refactoring stratégique](#contexte)
3. [Instructions](#instructions)
4. [Travail à réaliser](#travail)
	- [Partie 1 : Rétro-ingénierie](#partie1)
	- [Partie 2 : Conception](#partie2)
	- [Partie 3 : Gestion](#partie3)
	- [Partie 4 : Refactoring](#partie4)
	- [Partie 5 : Bonus (Optionnelle)](#partie5)
5. [Guide](#guide)
6. [Évaluation](#evaluation)
7. [Rapport du projet](#rapport)
8. [Conditions de réalisation](#conditions)
9. [Aide et discussions](#discussion)
10. [Remise](#remise)



<a name="logiciel"></a>
## 1. Logiciel cible 

Nous considérons le logiciel [GanttProject](https://www.ganttproject.biz/) qui est un logiciel open source gratuit pour la planification et la gestion de projets. Ce logiciel se concentre sur la création de [diagrammes de Gantt](https://fr.wikipedia.org/wiki/Diagramme_de_Gantt), qui est un diagramme à barres représentant la planification de projet.

Liens :
- Le logiciel [GanttProject](https://www.ganttproject.biz/)
- Le répertoire Github de [GanttProject](https://github.com/bardsoftware/ganttproject)
- La documentation de [GanttProject](https://docs.ganttproject.biz/)


<a name="contexte"></a>
## 2. Contextualisation pour le refactoring stratégique
Supposons que vous et votre équipe avez été embauchés par une compagnie hypothétique pour refactoriser GanttProject puisqu'ils utilisent ce logiciel open source dans leurs activités quotidiennes. Bien que GanttProject soit un bon logiciel pour la planification de projets, il manque une fonctionnalité importante pour l'entreprise hypothétique. Dans cette compagnie, les employés (ressources) peuvent être partagés entre différents projets. Chaque projet a un gestionnaire (manager) différent, et un gestionnaire ne doit pas avoir accès au calendrier d'un autre projet. Donc, chaque projet utilise un fichier différent avec un gestionnaire spécifique qui en est responsable.

La nouvelle fonctionnalité qui devrait être prise en charge dans GanttProject est d'autoriser un groupe de ressources partagé entre différents fichiers de projet. De cette manière, les gestionnaires peuvent vérifier la disponibilité des ressources sans avoir à partager l'ensemble des projets.


<a name="instructions"></a>
## 3. Instructions

Veuillez faire attention aux instructions suivantes. Vous devez envoyer un courriel au professeur (ali.ouni@etsmtl.ca) avec les détails suivants :

- **Objet du courriel** : [LOG530] Projet - GanttProject" si vous avez l'intention de travailler sur ce logiciel suggéré, ou "[LOG530] Projet Spécifique" pour une proposition de projet personnalisée. Veuillez essayer de me contacter avant la date limite (11 mars 2021) si vous souhaitez travailler sur un projet personnalisé.
- **Corps du courriel** : Le numéro de l'équipe, la liste des noms et codes permanents des membres de votre équipe (y) compris le vôtre). N'oubliez pas, un maximum de 3 personnes mais vous êtes autorisé à travailler avec moins de 3 si vous le souhaitez (par exemple, si vous voulez travailler sur un projet confidentiel).
- **Justification** : Si vous choisissez de travailler sur un projet personnalisé (différent de GanttProject), vous devez motiver ou expliquer pourquoi ce projet vous permettrait de démontrer vos compétences en réingénierie. (Veuillez vous référer à la Section [Rapport du projet](rapport) pour plus de détails)


Afin de travailler sur ce projet de réingénierie, veuillez considérez les instructions suivantes :

- Faites un Fork du répertoire de [GanttProject sur Github](https://github.com/bardsoftware/ganttproject) et faites un clone lu code source pour que votre équipe. Dans la page de [documentation](https://docs.ganttproject.biz/development/build/), vous pouvez trouver les instructions supplémentaires sur la façon de construire GanttProject (adaptez-vous en conséquence, car de nombreux projets open source sont un peu négligents pour garder leur documentation à jour).
- Tous les membres de votre équipe doivent être ajoutés au érertoire Github en tant que collaborateurs.
- Ajoutez votre enseignant en tant que collaborateur à votre repertoire (voici l'[ID GitHub de votre enseignant](https://github.com/ouniali)).
- Faites des commits de vos changements régulièrement en fournissant des informations sur l'activité réalisée. Toute activité spécifique nécessitant une modification de fichiers doit être intégrée dans un commit spécifique avec une description simple de la tache de maintenance effectuée. Par exemple, si vous changez le système pour supprimer un « God Class », votre commit serait:
`` Refactoring God Class`` ou ``correction de God Class (Extraire une classe)`` ou ``correction de God Class (suppression du code dupliqué)``
si vous introduisez de nouveaux tests:
``
Refactoring God Class + nouveau test ajouté
``
Bien sûr, pousser les tests sur un commit séparé serait également acceptable (plutôt, il serait préférable de le faire séparément).
Il n'est pas considéré comme une bonne pratique de faire des gros commits avec beaucoup de fichiers modifiés sans fournir de raison expliquant pourquoi ces fichiers ont été modifiés. Essayez de diviser vos commits en unités plus petites (ce qui peut aider à la correction aussi).

- Assurez-vous de faire un commit de la version finale de votre projet de réingénierie. Le commit final sera considéré pour l'évaluation dans le cadre de la remise de votre projet.

<a name="travail"></a>
## 4. Travail à réaliser

<a name="partie1"></a>
### Partie 1 : Rétro-ingénierie

<p align="center">
  <img src="figs/retro.png?raw=true" alt="Rétro-ingénierie"/>
</p>

Décrivez la conception actuelle de la fonctionnalité sélectionnée dans GanttProject. Indiquez clairement comment cette partie se situe dans l'architecture du projet.

<a name="partie2"></a>
### Partie 2 : Conception


<p align="center">
  <img src="figs/conception.png?raw=true" alt="Conception"/>
</p>

Introduire une conception générique qui décrit comment la nouvelle fonctionnalité doit être intégrée et comment la conception gère l'interaction avec le reste du système. Il doit être clair que les types de changements faits peuvent être facilement étendus par la suite.

Il sera important de re-penser la suite de tests de manière à ce qu'elle puisse s'adapter à la nouvelle fonctionnalité et à la nouvelle conception.

<a name="partie3"></a>
### Partie 3 : Gestion

<p align="center">
  <img src="figs/gestion.png?raw=true" alt="Gestion de projet"  width="400" height="280"/>
</p>


Organiser le travail à faire entre les membres de l’équipe et estimer l'effort et le temps requis pour :
1. Le refactoring pour faciliter/supporter les nouvelles fonctionnalités, et
2. Modifier/étendre les tests.

<a name="partie4"></a>
### Partie 4 : Refactoring

<p align="center">
  <img src="figs/refactoring.jpeg?raw=true" alt="Refactoring"/>
</p>

Refactoriser l'implémentation actuelle de GanttProject de sorte qu'il puisse gérer l'une des nouvelles fonctionnalités.

Ajustez/étendez les tests du projet pour préserver leur efficacité et leur couverture pendant et après le refactoring.

<a name="partie5"></a>
### Partie 5 : Bonus (Optionnelle)
Vous pouvez avoir un bonus allant jusqu'à 10 points si vous faites une (ou plusieurs) des tâches de réingénierie optionnelles suivantes : 
1.	Réussir à faire/contribuer à un ou plusieurs Pull Requests avec des refactorings/tests/changements sur le référentiel de [GanttProject sur Github](https://github.com/bardsoftware/ganttproject/pulls)
2.	Réussir à faire/contribuer/résoudre un ou plusieurs Issues sur le Issue Track System [GanttProject sur Github](https://github.com/bardsoftware/ganttproject/issues).
3.	Implémenter et tester la fonctionnalité sélectionnée. 
Idéalement (mais pas nécessairement), le pull request ou le issue sera révisé et fusionné par l'un des développeurs actuels du projet.


<a name="guide"></a>
## 5. Guide
Vous devrez effectuer un certain nombre de techniques que vous avez utilisé lors des séances des laboratoires et/ou expliqués dans le cours. Ceux-ci sont :
-	Analyse : Analyse de code dupliqué, mesures de qualité et visualisation, exploration des répertoires de code, etc.
•	Restructuration : Tests, refactoring, etc.

Ce projet met l'accent sur une analyse saine et systématique du problème présenté, de l'espace de solutions possibles et de la (ou des) solution(s) choisie(s). Les séances de laboratoires et du cours théorique sont conçues de manière à vous préparer à un tel projet. Vous êtes encouragé à évaluer les avantages et les inconvénients des techniques présentées dans les séances de laboratoires et à exploiter les techniques d'analyse avec un aspect critique. Vous êtes encouragé également à utiliser des techniques d'analyse alternatives avec d’autres outils existants.

En ce qui concerne la partie refactoring, il est important d’utiliser les tests. Les aspects suivants doivent être considérés :
- Déterminer dans quelle mesure les tests actuels fournissent du support pour vos étapes futures de refactorisation (p-ex, montrer l'information sur la couverture de tests).
- Composer des arguments expliquants pourquoi les tests sont (in)adéquats pour le scénario de refactoring que vous avez choisi et ajustez les tests au besoin. Soyez efficaces en ce qui concerne le temps investi dans les tests.


<a name="evaluation"></a>
## 6. Évaluation

Pour montrer que vous avez réussi le projet, vous devrez démontrer ce qui suit :
Vous avez les connaissances nécessaires pour planifier et sélectionner les patrons de réingénierie appropriés pour les différentes activités de votre projet.
- Vous avez fait une sélection de techniques d'analyse. Par exemple, l'analyse de code dupliqué, l'explorations de répertoire de code, mesure des métriques de qualité et visualisation, assistants de refactoring comme vu dans les sessions de laboratoires, mais d'autres techniques complémentaires ou alternatives sont également encouragées, et vous avez appliqué ces techniques de manière saine et systématique. Vous avez clairement expliqué (à l'aide des captures d'écran, des résultats de l'interprétation des outputs des outils) comment vous avez utilisé les résultats de ces techniques d'analyse.
- Vous avez effectué les 4 activités ci-dessus (décomposées en (1) recouvrement de la conception via la rétro-ingénierie, (2) conception, (3) gestion, et (4) refactoring) et en avez discuté dans votre rapport de projet.
- Les restructurations que vous avez appliqué préservent le comportement.
	- Vous pouvez démontrer la correspondance (mapping) entre chacune des classes de la structure d'origine avec la nouvelle structure.
	- Le processus de compilation réussit parfaitement.
	- Les tests s'exécutent sans défauts et démontrent. Augmenter la couverture des tests montre que votre solution est plus fiable.
- L'introduction du nouveau design indique clairement que le projet est prêt à être livré. Vous n'êtes pas censé effectuer complètement le processus de refactoring. Sélectionnez et exécutez un ensemble de refactorings qui illustrent suffisamment votre solution proposée.
- Le rapport est rédigé de manière claire détaillant toutes les étapes et le raisonnement du projet. N'oubliez pas que le rapport est le document qui illustre tout votre travail. C'est donc l'artefact le plus important pour le processus d'évaluation.


<a name="rapport"></a>
## 7. Rapport du projet

Les aspects que nous aimons généralement voir abordés dans le rapport sont les suivants:

- **Contexte** : discuter brièvement du contexte dans lequel vous exécutez votre projet.
- **Problème à résoudre** : clarifier le problème à la base du projet et indiquer ses difficultés intrinsèques.
- **Gestion de projet** : démontrer comment vous avez organisé le travail et comment vous le contrôlez (au lieu d’un travail qui vous contrôle !)
	-	**Portée** : quelles sont les limites de votre projet ? Qu'est-ce qui n'est pas inclus dans le projet ?
	-	**Risques** : Quels risques ont été envisagés et lesquels ont été atténués ? Quelle est la priorité des risques qui doivent encore être atténués ? Par exemple, quelles dépendances externes pourraient avoir une incidence sur votre résultat ? Quelles alternatives avez-vous préparées au cas où ce risque s’instaurerait ?
-	**Réingénierie du logiciel** :
	-	**Les tests** : Comment pouvez-vous vérifier que vous répondez aux exigences ? Quelle stratégie de test avez-vous choisie et quels sont les arguments pour cette sélection ? Dans quelle mesure êtes-vous convaincu que votre solution répond aux exigences ?
	-	**Assurance qualité** : quelles sont les exigences non fonctionnelles ? Par exemple, comment différenciez-vous une bonne et une mauvaise solution ?


**NB.** Il est possible de soumettre vos propres propositions de projets. Ces propositions seront approuvées si elles représentent un projet de réingénierie bien définit basée sur les techniques de réingénierie présentées lors des séances de laboratoires et du cours. Par exemple, vous pouvez toujours proposer de faire la réingénierie sur un autre système logiciel (un système logiciel que vous avez développé dans votre stage, projet implémenté pour un autre cours ou projet de fin d’études, etc.).


<a name="conditions"></a>
## 8. Conditions de réalisation
Le travail est à effectuer en équipes de 3 étudiants au maximum.

<a name="discussion"></a>
## 9. Aide et discussions
Vous êtes encouragés à discuter du projet et à poser vos questions en utilisant le forum créé à cette fin sur Moodle ou sur Discord. Les membres de chaque équipe sont encouragés à utiliser les channels privés (textuel et vocal) créés pour leur équipe sur Discord pour discuter et travailler en équipe sur les différentes activités du laboratoire.

<a name="remise"></a>
## 10. Remise
Le travail doit être remis électroniquement sur Moodle au plus tard le **7 avril à 23h59**. Vous devrez remettre une archive ``zip`` ou ``tar.gz`` contenant tous les fichiers, ainsi qu’un fichier texte indiquant le nom de tous les membres de l’équipe ayant contribué à la réalisation du travail. 
Une seule remise électronique est nécessaire par équipe. Remettez aussi individuellement le tableau de contribution tel vu dans le laboratoire précédent.
Pour faciliter la correction, vous devez nommer votre dossier de la remise de la façon suivante :

```
LOG530H2021-Projet-EquipeYY-CodePermanent1_CodePermanent2_CodePermanent3
```

et votre rapport ainsi :
```
EquipeYY-Rapport.pdf
```
