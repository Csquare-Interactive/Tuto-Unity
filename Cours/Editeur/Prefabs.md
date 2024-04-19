# Prefabs

Les **prefabs** sont des **GameObject** qui ont été **préfabriqués**. Cela signifie que vous pouvez **créer** un GameObject, lui **ajouter** des **components** et **configurer** ces components, puis **sauvegarder** ce GameObject en tant que **préfab**.

L'utilité des prefabs est de pouvoir **réutiliser** un GameObject **préconfiguré** à l'infini. Cela permet de **gagner** du temps lors de la **création** de **niveaux** ou de **scènes***.
De plus, les modifications apportées à un prefab seront **répercutées** sur **tous** les GameObjects qui utilisent ce prefab, ce qui facilite la **mise à jour** de votre jeu.

## Création et configuration d'un prefab

### Création d'un prefab

Pour **créer** un prefab, il vous suffit de **sélectionner** le GameObject que vous souhaitez **préfabriquer** dans la **hiérarchie** de votre scène, puis de **glisser-déposer** ce GameObject dans le dossier de votre choix dans l'onglet **Project**.

Vous devriez voir apparaître une **icône** de **cube bleu** à côté du nom de votre GameObject, ce qui signifie que ce GameObject est maintenant un **prefab**.

![Création d'un prefab](/img/00021.png)

### Édition d'un prefab

Pour **éditer** un prefab, il vous suffit de **double-cliquer** sur le prefab dans l'onglet **Project**. Cela ouvrira le prefab dans une **nouvelle fenêtre** d'**édition**.

Vous pouvez maintenant **ajouter**, **supprimer** ou **modifier** des **components** sur votre prefab. Toutes les modifications apportées à ce prefab seront **répercutées** sur **tous** les GameObjects qui utilisent ce prefab.

Ici, j'ai ajouté un component **RigidBody2D** ainsi qu'un **GameObject enfant** au prefab.

![Édition d'un prefab](/img/00022.png)

Désormais, tous les GameObjects qui utilisent ce prefab auront un **RigidBody2D** et un **GameObject enfant**.

![Répercussion des modifications](/img/00023.png)

## Gestion des instances d'un prefab

### Création d'une instance

Pour **créer** une **instance** d'un prefab, il vous suffit de **glisser-déposer** le prefab depuis l'onglet **Project** vers la **hiérarchie** de votre scène.

Vous devriez voir apparaître une **copie** du prefab dans la **hiérarchie**. (Il est recommandé de **renommer** cette instance pour éviter toute confusion).

### Override des propriétés

Lorsque vous **modifiez** une **propriété** d'un **component** sur une **instance** d'un prefab, cette propriété est **overridée**. Cela signifie que cette propriété est **différente** de celle du prefab.

![Override d'une propriété](/img/00024.png)
![Override d'une propriété](/img/00025.png)

Pour **réinitialiser** une propriété à sa **valeur** d'origine, il vous suffit de **cliquer** sur le **bouton** **Revert** à côté de la propriété.
Vous pouvez également appliquer les **modifications** de l'instance au prefab en **cliquant** sur le **bouton** **Apply**.

![Apply ou Revert d'une propriété](/img/00026.png)

## Fonctions avancées

### Prefab Variants

Les **prefab variants** sont des **prefabs** qui **héritent** d'un **prefab** parent. Cela signifie que les **prefab variants** **répercutent** les **modifications** apportées au **prefab** parent.

Pour **créer** un **prefab variant**, il vous suffit de **glisser-déposer** le **prefab parent** dans le dossier de votre choix, puis de **modifier** ce **prefab variant** en utilisant l'**override** des propriétés vu précédemment.

Les **prefab variants** sont **très utiles** pour **créer** des **variantes** d'un **même** GameObject, comme par exemple des **ennemis** avec des **couleurs** différentes ou des **armes** avec des **dégâts** différents.

### Nesting Prefabs

Il est possible de **nester** des **prefabs** les uns dans les autres. Cela signifie que vous pouvez **ajouter** un **prefab** en tant que **GameObject enfant** d'un autre **prefab**.

Cela peut être **utile** pour **créer** des **prefabs** **composés** de **plusieurs éléments**, comme par exemple un **personnage** avec des **armes** et des **accessoires**.

![Nesting Prefabs](/img/00027.png)

## Bonnes pratiques

Il est recommandé de **créer** des **prefabs** pour **tous** les **éléments** de votre jeu qui sont **réutilisables**. Cela vous permettra de **gagner** du temps lors de la **création** de **niveaux** ou de **scènes**.

Il est également recommandé de **bien organiser** vos **prefabs** dans des **dossiers thématiques** pour **faciliter** la **navigation** et la **recherche**.