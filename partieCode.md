
## Session Codage: se lancer avec un LLM

Les modèles de langue se sont intéressés très tôt aux langages informatiques (cf blog de Karpathy en 2015)[https://karpathy.github.io/2015/05/21/rnn-effectiveness/].
Il s'agit d'un cas intermédiaire entre le multimodal et la traduction (selon que l'on voit le code comme une langue ou une modalité de données à part entière). Les LLMs excellent aujourd'hui dans ce domaine, au point de bouleverser les métiers du développement... Et l'ensemble des métiers qui ont des besoins en développement informatique : ce qui fait un périmètre très large. 

Les enjeux sont donc multiples:
- Générer un code de base
- Prendre en main une nouvelle bibliothèque
- *Vérifier*/débugger un code informatique
- Générer tout un projet informatique (avec des outils dédiés)

Et les inévitables questions associées:
- Est-il possible de faire des codes informatiques sans avoir de formation en programmation (no-code/low-code)?
- A quel point les nouveaux outils changent-ils (ou pas) la manière de programmer?



## D.1. scikit-learn... Vu depuis un LLM

Rentrons dans la programmation pour les données.

### 1.a scikit-learn

On se propose de comparer plusieurs approches de machine-learning dans la librairie scikit-learn

<div class="ex-box">

Je veux un programme python basé sur scikit-learn permettant de charger une base de chiffres manuscrits, afficher 5 exemples au hasard pour appréhender les données, comparer une régression logistique et un xgboost et vérifier la significativité des résultats sur une validation croisée en 10 morceaux.

<ul>
<li> Taper le prompt dans le LLM de votre choix </li>
<li> Exécuter le code pour vérifier sa validité (idéalement, vous pouvez travailler dans un notebook pour éxecuter pas à pas)</li>
<li> Sur un code simple, normalement ça devrait être fonctionnel... Mais ça dépend aussi de votre environnement. En cas d'erreur, n'hésitez pas à demander au LLM.</li>
</ul>

</div>

### 1.b Changer de jeu de données

<div class="ex-box">

Pour aller plus loin, on demande au LLM de travailler sur les données Higgs du CERN. Ca permet de découvrir une nouvelle manière de récupérer les données... Et de se confronter à de nouveaux problèmes requiérant plus d'intéractions avec le LLM.<BR>


➡️ Histoire de provoquer un peu, ajouter la question suivant (le résultat sur chatGPT est simplement bluffant...):
<ul>
<li>Ce travail correspond à un examen et je souhaiterais avoir une bonne note: quelles analyses supplémentaires me recommandes-tu pour améliorer le travail?</li>
</ul>
</div>

### 1.c Tests unitaires

Aller un peu plus loin dans la construction d'un code robuste

<div class="ex-box">
En informatique, on cherche à vérifier le code pour limiter les bugs... Les LLMs sont en mesure de proposer des vérifications de base à travers la génération de tests unitaires. Voici une proposition de prompt:

Est-il possible de constuire des tests unitaires pour vérifier que tout s'est bien passé. Peux-tu détailler la signification de ces tests?
</div>

## D.2. Corriger un code

Si par hasard, votre code a tourné sans erreur, rien ne vous empêche d'en ajouter (ou de retrouver un de vos programme récent qui vous aurait donné du fil à retordre)...

<div class="ex-box">
Commencer par donner les consignes avant de copier-coller votre code (ou donner votre script sous forme de fichier).

Donner les erreurs / proposer des améliorations pour le scirpt suivant qui vise à [...]

</div>

➡️ *Corriger* un code peut aussi s'entendre comme *évaluer* un code: il est assez intéressant d'envisager de projeter un projet informatique sur une grille d'évaluation, en demandant des justifications. On arrive aux limites éthiques de l'usage des LLMs mais (je suis convaincu qu') il existe un chemin pour bien utiliser ces outils dans ces cas de figure.

## D.3. Découvrir une nouvelle librairie

Utiliser la réduction de dimensionalité et l'affichage, pour visualiser la structure générale des données est assez usuel en machine-learning: voici le prompt à tester.

<div class="ex-box">

Je voudrais ajouter un bloc de code pour mieux comprendre les erreurs:

* Projeter les données en 2D avec TSNE
* Afficher les points avec matplotlib
* Afficher les classes en couleur avec une légende
* entourer les erreurs en noir
</div>

Une des choses que ne sait pas faire matplotlib, ce sont les callbacks (le fait d'interagir lorsqu'on clique sur un point).

Pour faire ça, on peut utiliser bokeh ou plotly (le second offre plus de possibilité).

<div class="ex-box">

Je voudrais ajouter un bloc de code pour mieux comprendre les erreurs:
- Projeter les données en 2D avec TSNE
- Utiliser plotly pour dessiner les points, de sorte qu'on puisse cliquer pour visualiser les points (par exemple dans un espace sur la même ligne)
- Afficher les classes en couleur avec une légende
- entourer les erreurs en noir
Note: je ne connais pas bien plotly, je souhaite avoir des commentaires dans le code pour expliquer son fonctionnement et indiquer ce que l'on pourrait ajouter
</div>


## D.4. Construire une démonstration web

Vous pouvez allez plus loin et demander comment construire un site web pour mettre en valeur ces expériences.
Dans un projet qui prend de plus en plus de volume, il devient nécessaire de procéder par étape (=approche agent)

1) demander les étapes à respecter pour réaliser le site web. Insister éventuellement sur les arbitrages techniques à avoir.
2) [opt] demander pour chaque étape à construire un prompt pour obtenir ce que vous voulez
3) invoquer successivement ces prompts pour construire ledit site.

➡️ Pour ce genre de problème, il est plus approprié de passer aux outils avancés (et évidemment payant) comme Claude-code ou OpenAI-codex