# Components

Les **components** sont des **scripts Unity** qui vont permettre d'ajouter des **fonctionnalités** et des **intéractions** aux **GameObjects** (cf. Cours sur les GameObjects).  

Le moteur de jeu Unity propose nativement un catalogue de component pour réaliser vos jeux. Cependant pour les jeux plus complexe ou demandant une fonctionnalité particulière, il est courant d'avoir à développer ses propres components.  

Durant ce cours nous allons **parcourir** en détail ce qu'est un components sur Unity et **comment** en réaliser un soit même.


## L'interface des components

Pour travailler avec les components de son GameObject, Unity fournit une **interface** de travail présente dans l'onglet "**Inspector**" sur la droite de l'éditeur qui permet de **visualiser** les components d'un GameObject sélectionné et de **modifier/ajouter/supprimer** ses components.  

Nous allons voir ici en détail comment se **structure** l'interface des components.  

### Transform

Le **Transform component** est un component à part du reste des components. Ce dernier est le component par **défaut** de chaque GameObjects et permet de **placer** ce dernier dans l'environnement de Unity, ainsi que modifier la **taille** et l'**orientation** du GameObject.  
Ce component ne peut pas être **supprimé** par défaut.  

![Create Empty](/img/00011.png)

La plupart des components offre la possibilité de **modifier** les valeurs du components afin de modifier **rapidement** le **comportement** du GameObject.  
Ici, le transform component permet de **déplacer**, **aggrandir/rétrécir** et **orienter** le GameObject facilement.
Les labels **Position**, **Rotation** et **Scale** permettent donc de modifier en temps réel le GameObject sur notre scène. Cependant, notre GameObject n'a aucun affichage graphique, la modification de ces valeurs sera invisible à notre écran (même si elles s'effectuent bien).  

Ajoutons donc un **Sprite Renderer** (un component natif du catalogue Unity) permettant d'**afficher** le component sur notre scène **2D**.  

### Ajouter un Component

Pour **ajouter** un component, cliquez sur le bouton "**Add Component**" sur l'onglet de l"**Inspector**". Une fenêtre s'ouvre et **sélectionnez** Sprite Renderer.  

![alt text](/img/00012.png)

Lorsqu'on **ajoute** un component à un GameObject, une **interface** propre au compnent s'affiche dans l'onglet "**Inspector**", cet interface contient au moins l'**entête** du component. La plupart des components permettent de **modifier** des **variables** directement depuis l'**éditeur**, c'est ici que vous pourrez **tester** différentes configuration pour correctement **paramétrer** vos components.  

Le **GameObject** possède désormais un **Sprite Renderer**. Cependant vous vous apercevez que ce dernier ne s'affiche toujours **pas** sur l'écran.  
Le Sprite Renderer a besoin d'un **Sprite** à afficher et par défaut cette valeur est à **None**.

**Remarque: Pour identifier rapidement ce qu'il faut mettre sur une variable le type attendu est souvent mis entre parenthèse -> ici (Sprite)**

![alt text](/img/00013.png)

Ainsi pour **afficher** notre **GameObject** il faut tout d'abord lui donner un **Sprite**. **Donnez** lui en un ou **créez** en un.  
Pour créer un **Sprite** allez dans l'onglet "**Project**" > Dans le dossier "**Assets**" (dossier par défaut) > **Clic droit** > **Create** > **2D** > **Sprite** > **Square**.  
Donnez lui le nom que vous souhaitez (par défaut "**Square**").  

Pour plus d'information concernant les Sprites, **référez-vous sur le cours sur les Sprites**.

![alt text](/img/00014.png)

Pour donner notre nouveau **Sprite** au Component il y a deux manières.  
1. Sélectionnez votre **GameObject** et **glissez-déposez** l'élément dans le **champs** de la valeur voulu -> Ici le **Sprite** dans le champs **Sprite** du component **Sprite Renderer**.

2. Sélectionnez votre **GameObject** et à droite du champs voulu se trouve un petit cercle. **Cliquez-dessus** et tous les **éléments** du projet capable de se **positionner** dans le champs pourrons être sélectionné.

![alt text](/img/00015.png)

**Remarque: Si vous devez naviguer entre plusieurs onglets le GameObject se déselectionne automatiquement. Pour garder à portée de main les valeurs du component vous pouvez faire : Clic droit sur l'entête du component > Properties > Une fenêtre flottante s'ouvre.**

![alt text](/img/00016.png)


## Comment créer son Component ?

Il y a deux moyens sur Unity pour créer un component :  

1. Sélectionnez un **GameObject** > Cliquez sur "**Add Component**" > **Recherchez** le component que vous voulez **créer** > Sélectionnez "**New script**"

![alt text](/img/00017.png)

2. Dans l'onglet "**Project**" initialement placé sur le bas de l'éditeur > **Clic droit** > **Create** > **C# Script** > Donnez lui le **nom** du component  

![alt text](/img/00018.png)

**Remarque: Il est conseillé de placé son script dans un répertoire prévu pour cet effet**  

Sur Unity, un **script C#** vierge (fraîchement crée) est par **défaut** considéré comme un **component**. Si vous avez crée ce component en utilisant la **seconde méthode** ou que vous voulez le **rajouter** à un autre GameObject, ce component est désormais **trouvable** dans la **fenêtre de recherche** lorsque vous voulez ajouter un nouveau component.  

![alt text](/img/00019.png)

### Comment éditer son component ?

Pour **éditer** son component, il faut simplement **double-cliquer** sur le **script C#** dans votre onglet "**Project**". Cela ouvrira votre **IDE** par défaut (Pour **modifier** son IDE par défaut : Onglet "**Edit**" > **Preferences** > **External Tools** > **External Script Editor** > **Sélectionnez** votre IDE).  

Voici comment se présente un **component vierge** sur Unity :  

![alt text](/img/00020.png)

Pour plus d'information concernant l'éditions de components, **référez-vous à la section C# du cours sur les Components**.  

**Notez** juste ici que c'est l'**héritage** de **MonoBehavior** qui permet à Unity d'identifier ce script comme étant un **Component**. Enlevez cet héritage et le script C# redevient un script **basique**.

**Remarque: MonoBehavior signifie que ce scrip peut être attaché à un GameObject.**