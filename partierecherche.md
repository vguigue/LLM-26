## Session B: exercices orientés recherches


[Retour à la page principale](./)

Nous allons voir les usages *recherche*, notamment bibliographique et écriture d'article puis des usages plus pédagogiques sur la rédaction de cours, la création d'exercice.

[Une autre vision des LLM pour la pédagogie, pour plus tard: [lien](https://oer.uclouvain.be/jspui/bitstream/20.500.12279/1089.3/6/CahierLLL_IAG_OKOER.pdf)]


## B.1. Bibliographie

C'est un des usages controversé: on a beaucoup cité la bibliographie comme la chose à NE PAS faire avec un LLM... Tentons quelques expériences.

### 1.a Bibliographie et hallucination

Une hallucination est un résultat faux... mais obtenu en maximisant la vraisemblance du texte. Transposé dans le domaine de la bibliographie, cela se traduit par des référénces qui n'existent pas... Mais qui sont très crédibles!

<div class="ex-box">
<ul>
<li> Je voudrais une bibliographie sur la technique CRISPR-CAS9 [remplacer par le terme technique de votre choix]</li>
</ul>

➡️ par exemple en sélectionnant le modèle  <tt>meta-llama/Llama-3.3-70B-Instruct</tt> dans l'interface Huggingface/ragarenn <BR> 
Tester les différentes références: si >90% sont bonnes, que faut-il en conclure?
<BR>
➡️ plus les références sont classiques (=beaucoup citées), plus elles sont correctes... Mais il faudra toujours les vérifier !
<BR>
➡️ Ca vaut le coup de refaire l'expérience sur un domaine plus pointu (moins général) pour avoir plus d'hallucinations... Il faut aussi différentier le mode LLM (mémoire paramétrique) et le mode RAG (sur chatGPT par exemple).
</div>

<div class="ex-box">
Générer une bibliographie sur la technique CRISPR-Cas9: distinguer les références qui précèdent cette technique, les références qui fondent CRISPR-Cas9 et les avancées récentes sur ces architectures
<ul>
<li>Remplacer le CRISPR-Cas9 par ce que vous voulez</li>

</ul>

➡️ Encore et toujours une histoire de véracité: il faut vérifier que les références existent... Et sont bien pertinentes!
</div>

### 1.b Usage en bibliographie : identifier une source primaire

Retrouver une source primaire sur [Scholar](https://scholar.google.com) n'est pas simple... Sur des techniques très connues (CRISPR-Cas9 en biologie moléculaire, les SVM, VAE ou Transformer en IA, ...)


<div class="ex-box">
<ul>
<li> Quelle est la référence biblio primaire de CRISPR-Cas9? [remplacer par une technologie très citée dans votre domaine]</li>

</ul>

</div>

### 1.c Usage en bibliographie : structurer la bibliographie

<div class="ex-box">
<ul>
<li> Je veux faire une bibliographie sur l'usage des données textuelles dans les systèmes de recommandation: peux-tu me proposer une structuration avec différents usages et quelques références</li>
<li> Je veux structurer une bibliographie sur l'alimentation animale: peux-tu me proposer une structuration avec différents axes (par exemple, valeurs nutritives, impact sur la performance animale, bien-être, ...) et quelques références </li>
</ul>

➡️ plus les références sont classiques (=beaucoup citées), plus elles sont correctes... Mais il faudra toujours les vérifier !

</div>



## B.2 Rédaction/gestion de projets

Quelques exemples:


### 2.a SWOT

<div class="ex-box">

Générer un texte d'un demi page sur les usages de l'IA dans votre métier/votre équipe de recherche en mode SWOT (Strengths, Weaknesses, Opportunities, Threats). Ajouter des informations sur votre équipe sous forme de liste de mots clés. <BR>

On peut envisager différentes options:
<ul>
<li>Ce texte a vocation a être publié sur la page web de votre équipe</li>
<li>Ce texte est une réponse à appel à projet (AAP), il doit être crédible tout en mettant en avant votre équipe pour obtenir des financements</li>
</ul>

➡️ Il faut donner une description de votre équipe, sous la forme d'un texte brut (copier-coller), sous la forme d'un lien URL (à condition d'avoir un chatbot connecté), sous la forme d'un document
</div>


### 2.b ANR

<div class="ex-box">

Je veux déposer un projet ANR sur le développement de systèmes de recommandation en nutrition [remplacer par votre sujet de prédilection!].

<ul>
<li>Quels sont les enjeux de ce type de systèmes? Générer des arguments explicant l'intérêt de ces systèmes (sur le plan de la santé, des économies, de la souveraineté alimentaire, ...) [on peut décomposer en plusieurs questions]</li>
<li>Structurer une bibliographie pour ce projet en distinguant les types d'applications et les modèles associés.</li>
<li>Quelles sont les sources de données disponibles pour apprendre ces systèmes de recommandation?</li>
</ul>
</div>

<div class="ex-box">

Je veux organiser un séminaire sur les nouvelles techniques autour des petits ARN pour les plantes de 2 jours avec des inscriptions gratuites pour les orateurs et payantes pour les participants dans le cadre d'une université francaise. Quelles sont les grandes étapes? Par ou commencer?

<ul>
<li>Ne pas hésiter à demander des outils pour certaines étapes (e.g. sélection des aarticles)</li>
<li>Auprès de qui rechercher un budget? Comment procéder? Ecrire les lettres de demande</li>
</ul>
</div>


## B.3 Ecrire un paragraphe (introduction) d'article scientifique

La démarche consiste à donner tous les éléments (ou presque) au modèle de langue sous forme de liste de mots-clés ou de bouts de phrases

- Contexte général de la recherche (à donner ou à faire générer) (e.g. l'intéret du machine-learning pour l'analyse des séquences ADN ces dernières années + exemple d'applications)
- Le défi spécifique attaqué dans l'article + les verrous scientifiques actuels / limites des solutions existantes
- Les contributions proposées dans l'article

**Note:** donner ces éléments en français puis demander une génération en anglais

<div class="ex-box">

➡️ Dans l'idéal, prenez un de vos article écrit récemment et tenter de reconstruire une introduction en donnant les bons éléments au modèle de langue
<BR>


</div>

Sinon, voici une proposition (évidemment très orientée sur le machine learning)

<div class="ex-box">

Idées à faire passer:<BR>
<tt><small> 
tendance actuelle = apport de l'appentissage de représentation non supervisé pour la classification de séries temporelles<BR>
défi = rendre ces approches plus transparentes (échec des approches supervisées); distinguer les types d'explications post-hoc et natives; ne pas perdre en performances (par rapport aux approches SAX)<BR>
contributions = (1) identification des propriétés nécessaire pour l'explicabilité de l'architecture (shift equivariance, décodeur linéaire, conservation des enchainements temporels); (2) proposition d'une architecture basée sur les VQ-VAE; (3) campagne d'expériences sur UCR pour démontrer les performances au niveau de l'état de l'art
</small></tt>
<BR>
Proposition de prompt:
<tt><small> 
Ecrire une introduction d'article scientifique en anglais d'une page détaillant les tendances actuelles du deep learning pour les séries temporelles sur différentes tâches (exemples), puis identifiant les défis actuel du domaine et mettant en avant les contributions. Enrichir les défis par rapport aux contributions
</small></tt>
<BR>
Bonus: Proposer une bibliographie pour chacun des paragraphes

Lien vers l'article original correspondant à la description: <a href="https://arxiv.org/abs/2310.16696"> lien </a>

➡️ N'hésitez pas à jouer sur un article à vous ou que vous avez lu récemment... Vous imaginez les spécifications/instructions détaillées que vous donneriez pour réaliser la tâche... Puis vous comparez.
</div>


## B.4.  Générations amusantes

<div class="ex-box">
Trouver un acronyme pour un projet de recherche sur les petits ARN: l'idée est d'optimiser la réponse des plantes aux stress environnementaux avec de l'IA

<ul>
<li>On peut spécifier la langue (le LLM part vers l'anglais ou le franglais par défaut)</li>

</ul>
</div>

<div class="ex-box">

Rédiger un poème sur les petits ARN, la réponse des plantes aux stress environnementaux, les perspectives d'utilisation de l'IA pour le futur. Les rimes seront croisées.
<ul>
<li>On peut préciser la langue ou rajouter des élements dans le prompt ou dans les questions suivantes</li>
<li>Si vous voulez ensuite générer de l'audio, différents outils existent: e.g. <a href="https://elevenlabs.io/app/speech-synthesis/text-to-speech"> lien </a> </li>
</ul>

Note: le test avec chatGPT est très concluant!
</div>

