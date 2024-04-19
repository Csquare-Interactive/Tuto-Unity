# GameObject

Sur unity, tout est **GameObject**. Un GameObject peut représenter un joueur, un arbre, une montagne, une maison, une arme, une balle, etc...  
Votre jeu va dépendre de comment vous allez les configurer, et comment vous allez les faire intéragir entre eux.  

Un GameObject est une instance de base dans laquelle vous allez intégrer des **components** qui permettront de "donner vie" à vos GameObjects.

## Comment créer un GameObject ?

Pour créer un GameObject sur Unity il vous suffit d'inspecter la hiérarchie initialement situé sur la gauche de votre éditeur.  
Faites **cliques droi**t > "**Create Empty**"  

Ainsi un GameObject vierge (portant le nom "GameObject" par défaut) sera crée.  

![Create Empty](/img/00001.png) 

Vous voila désormais avec un GameObject vierge qui n'est en réalité pas si vierge que ça. Par défaut sur Unity, chaque GameObject dispose d'un TransformComponent.  
Ce component permet de situé le GameObject sur l'environnement 2D/3D de Unity. (Il permet également de modifier la rotation et la taille du GameObject).  

## Les components dans un GameObject

### Comment ajouter un component à notre GameObject ?

Pour pouvoir ajouter un component à votre GameObject, référez-vous à la partie "**Inspector**" initialement situé à droite de votre éditeur.  
Par défaut l'inspecteur est vide et ne comporte aucune information. Pour ajouter un component, commencez par sélectionner le GameObject concerné.  

Si vous avez sélectionnez un GameObject vierge, il aura par défaut le TransformComponent. Pour lui ajouter un nouveau component, cliquez sur "**Add Component**".  
Une fenêtre est alors ouverte affichant tous les components que Unity a trouvé. Mettons lui un **Rigidbody2D**.  
Le **Rigidbody2D** permet de simuler une *physique* propre à l'environnement 2D de Unity sur le GameObject. Cherchez **Rigidbody2D** sur la barre de rechercher et cliquez sur le component correspondant.  

![Create Empty](/img/00002.png) 

Vous voila désormais avec un GameObject comportant un component "**Rigidbody2D**". Dans l'inspecteur vous pouvez visualiser les différentes données que le component propose (Pour plus d'information référez-vous au cours sur les **Rigidbody2D**).

### Comment supprimer un component à notre GameObject ?

Pour supprimer un component, rien de plus simple.  
Effectuez un **clic droit** sur l'entête du component concerné > Cliquez sur "**Remove Component**".  
Ainsi, le component devrais être supprimé du GameObject et de l'**inspector**.  

**Remarque: Le TransformComponent ne peut, par défaut, pas être supprimé d'un GameObject.**

![Create Empty](/img/00003.png)

### Comment créer ses propres components ?

Par défaut unity propose tout un catalogue de components que l'on peut venir utiliser dans nos GameObjects.  
Mais vient rapidement le moment où ces components ne suffisent plus et où la création de nos propres components devient inévitable.  

Pour créer ses components, Unity dispose d'un langage de programmation (**C#**) à travers lequel le développement des components sera possible.  
Pour plus d'informations à ce sujet, **veuillez-vous référer au cours sur les components**.


## Gestion d'un GameObject dans l'éditeur

### La visibilité dans l'éditeur

Dans l'éditeur, il est possible de "**masquer**" un GameObject. Pour cela il vous suffit de cliquer sur l'icone "**Oeil**" à gauche du nom du GameObject dans l'onglet "**Hierarchy**". Ainsi, le GameObject sera **invisible** sur l'éditeur :

Avant :  

![Create Empty](/img/00009.png)

Après :

![Create Empty](/img/00010.png)

### Retrouver facilement un GameObject

Si vous vous **perdez** dans votre scène ou que vous ne **retrouvez plus** un GameObject. Il est possible de **double cliquer** sur le nom du GameObject concerné dans l'onglet "**Hierarchy**" pour vous emmenez directement sur l'emplacement du GameObject sur votre Scène.

## La hiérarchie des GameObjects

Sur la gauche de l'éditeur Unity se trouve l'onglet "**Hiérarchie**". C'est dans celui-ci que vous pouvez **créer et organiser** tous vos GameObjects.  
Chaque GameObjects de votre hiérarchie peut intéragir avec un autre, cependant il peut arriver que certains soit bien plus liés que d'autres (Une arme à feu et ses balles, Le tronc d'un arbre et ses feuilles, etc...).  

Pour organiser cela il est possible de créer une relation **Parent-Enfant** à vos GameObject. Un GameObject jouera ici le rôle de **parent**, et ce dernier pourra avoir un ou plusieurs GameObjects **enfants** qui à leurs tours peuvent avoir d'autres **enfants**.  
En suivant ce **schéma** dans l'organisation de vos GameObjects. Vous allez être capable non seulement d'**organiser** au mieux votre onglet "hiérarchie" mais également de **faciliter** les interactions entre ces GameObjects.  

Prenons l'exemple suivant (chaque GameObjects dans l'exemple est vierge) :  

![Create Empty](/img/00004.png)

### Relation Parent-Enfant  

En reprenant l'exemple ci-dessus. Pour correctement hiérarchiser le projet en suivant une relation **Parent-Enfant** il faut tout d'abord correctement **identifier le problème**.  
Ici, on retrouve notre étoile, le soleil, certaines planètes du système solaire et 2 lunes, celle de la Terre et une lune de Saturne.  
Pour les hiérarchiser, nous allons donc suivre le schéma suivant: Le soleil est la racine de tout et sera donc le parent de tous les GameObjects présent dans le système solaire. Ensuite les satellites (La Lune et Titan) seront chacune les enfants de leur planète respectivement (faisant d'elle les **petits enfants** du soleil).  

Ainsi, en modifiant la hiérarchisation en suivant le modèle **Parent-Enfant**, nous obtenont le schéma suivant :

![Create Empty](/img/00005.png)


### Comment hiérarchiser son projet ?

La hiérarchisation **Parent-Enfant** permet de lier des GameObject ensemble. Cependant dans un jeu vous allez parfois finir par manipuler des **milliers** de GameObjects.  

Pour correctement organiser notre onglet "**Hierarchy**", il est utile de créer des GameObjects vierge qui ne seront pas utilisés en jeu mais comme des "**dossiers**" dans lesquels ont va ranger les GameObject utilisé.  

Par exemple en reprenant notre exemple nous pouvons créer le GameObject "Voie Lactée" dans lequel nous allons ranger le système solaire. Ce GameObject "Voie Lactée" sera lui placé dans un GameObject suivant un format libre que nous aimons définir comme suit : "**### nom_du_GameObject ###**".  

Ainsi en suivant ce format, l'onglet "Hierarchy" sera organisé même si il se retrouve à contenir des milliers de GameObjects.  

![Create Empty](/img/00006.png)

**Remarque: Les petites flèches à gauche du nom des GameObjects indique que ce dernier possède des enfants**  


### Les bonnes pratiques dans la hiérarchisation des GameObjects

Bien hiérarchiser ses GameObjects est **essentiel** dans le bon développement d'un projet. Plus tôt vous avez appris les concepts de bases et qu'il était possible de créer des GameObjects **vides** pour permettre de ranger plus **facilement** ses GameObjects et permettre une organisation de l'onglet "Hierarchy" plus **fluide**.  

Cependant il est important de suivre différentes étapes pour correctement hiérarchiser son projets.  

> Est-il nécessaire de constamment créer des GameObjects vides pour ranger ses GameObjects ?  

**Non**. L'utilisation des GameObjects vides est principalement utilisé lorsque l'on est amené à créer un **grand nombre** de GameObjects du même type, **qui peuvent être rangés ensemble**. Par exemple, une forêt contient des centaines/milliers d'arbres. Dans un jeu, chaque arbre est un GameObject. Il serait donc judicieux de créer un GameObject "Foret" qui contiendrais chaque Arbre.  

> Comment se retrouver lorsque de nombreux GameObjects se ressemblent ?  

Pour se retrouver facilement, la meilleure solution est dans le **nommage** d'un GameObject. Par exemple chaque Arbre pourrait être nommé "**Arbre_XXX**" où XXX serait un nombre allant de 001 à 999.  
Ainsi, chaque GameObjects sera **facilement identifiable** avec son nom. 


## Les Tags

Un **tag** est une donnée native de Unity que **chaque** GameObject (même vierge) possèdent. Ces tags sont prévus pour **identifier** et **retrouver facilement** un GameObject en particulier. Si la hiérarchisation permet de facilement retrouver le GameObject dans l'onglet "Hierarchy", le tag permet quant à lui d'aider les **components et les scripts** du jeu à le retrouver.  

Chaque GameObject peut se voir assigner un unique **tag**.

### Comment assigner un tag à un GameObject ?

Pour assigner un **tag** à un GameObject, il faut commencer par sélectionner le GameObject concerné. Ensuite, dans l'onglet "**Inspector**" situé sur la droite de l'éditeur, vous pourrez visualiser en dessous du nom du GameObject et au dessus des components une **combo-box** portant l'intitulé "**Tag**" (Par défaut sur "**Untagged**").  

Pour assigner un tag il vous suffis de cliquer sur cette **combo-box** et de sélectionner un tag au choix. Par défaut, Unity propose une liste de tag communément utilisé.

![Create Empty](/img/00007.png)


Pour plus d'informations sur les Tags, **veuillez-vous référer sur le cours sur les Tags**.


## Les Layers

Les **Layers** sont utilisés pour organiser comment les GameObjects vont **intéragir** entre eux et le moteur du jeu.  
Ils sont utilisés principalement dans deux grandes catégories: le **rendu** et les **collisions**.  

De la même manière que les **Tags**, les Layers permettent de **catégoriser** les GameObjects mais pour leurs **interactions** avec le **moteur de jeu**.  

**Le rendu**: Vous pouvez assigner des GameObjects à un certain Layer et faire en sorte que votre caméra de jeu n'affiche **que** les GameObjects présent dans ce Layer. Ainsi tous les autres GameObjects seront **ignorés** et cela économisera des performances.  

**Les collisions**: Vous pouvez définir dans quels Layer les collisions d'un GameObject font effet (Par défaut tous les Layers). Ainsi vous pourrez faire en sorte qu'un GameObject puissent intéragir avec un **certains** **types** de GameObjects.  

### Comment assigner un layer à un GameObject ?

Pour assigner un **layer** à un GameObject, il faut sélectionner le GameObject concerné. Dans l'onglet "**Inspector**" situé dans la partie gauche de l'éditeur. Entre le nom et les components vous pourrez retrouver une **combo-box** nommé "**Layer**" (Par défaut sur "**Default**").  

Il vous suffit d'intéragir avec la **combo-box** et de sélectionner un layer. Par défaut, Unity fournit une liste de layers.

![Create Empty](/img/00008.png)

Pour plus d'informations sur les Layers, **veuillez-vous référer sur le cours sur les Layers**.