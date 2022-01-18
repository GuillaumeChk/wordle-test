# wordle

## Project setup
```
npm install
npm run serve
```

## Présentation du projet
Récréer le jeu Wordle.

Etant donné la contrainte de ne pas passer plus d'une demi-journée soit 4~6h, je n'ai pas réussi à terminer de programmer le jeu. On ne peut pas voir si les lettres sont bonnes ou non.
On peut entrer des mots lettre par lettre (ainsi que les effacer), valider et si le mot est dans le dictionnaire on affiche la couleur des lettres. Si c'est le bon mot un message de victoire est affiché. Une fois la grille remplie sans avoir trouvé le bon mot un message de défaite est affiché.

J'ai utilisé **Vue.js** comme framework. J'ai créé des composants (dossier Components) : *GameGrid* pour la grille du jeu, *Row* pour les lignes, *Tile* pour une case, *Keyboard* pour le clavier et *KeyboardKey* pour les touches du clavier.

J'avais pensé faire appel à une API en ligne (de dictionnaire) pour récupérer un mots de 5 lettres aléatoirement et pour vérifier si le mot entré est valide, mais je n'ai pas eu suffisament de temps pour l'implémenter. Il y a une liste de 5 mots en brut pour pouvoir tester (loupe, chien, boite, aigle et flute).

J'ai utilisé la boucle v-for de Vue.js pour créer la grille et je voulais utilisé v-if/v-else-if/v-else pour afficher la couleur des lettres en fonction de leur validité.

## Comment jouer au Wordle ?
Chaque jour, un mot de 5 lettres est choisi aléatoirement. Vous devez le deviner en 6 essais.

À chaque essai, les lettres du mot que vous avez proposé changeront de couleur en fonction de à quel point vous êtes proche de le trouver :
- Vert : La lettre est dans le mot, à la bonne place.
- Jaune : La lettre est dans le mot, mais pas à la bonne place.
- Gris : La lettre R n'est pas dans le mot.
