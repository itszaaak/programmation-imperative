# Introduction à la programmation impérative

## Sommaire

1.[Les Types](#types)  
2.[Les Variables](#variables)  
3.[Conditions et operateurs](#conditions-et-opérateurs)  
4.[Les Boucles while](#boucles-while-et-do-while)    
5.[Les Boucles for](#les-boucles-for)  
6.[Les fonctions](#les-fonctions)  
7.[Les structures de données](#les-structures-de-donnes)  
8.[Projets](#projets)

## Types

Une information ou une donnée en programmation est souvent représentée par un type. Selon le paradigme et le langage de programmation utilisé, il existe différentes manières de représenter ces types. Dans cette partie du cours, nous allons nous concentrer uniquement sur les types principaux, également appelés types primitifs.

Voici le tableau des types :

| Type    | Dénomination            |
|---------|-------------------------|
| Int     | Nombres entiers         |
| Float   | Nombres à virgule       |
| Boolean | Soit Vrai soit Faux     |
| Char    | Caractère               |
| String  | Chaîne de caractères    |

**Remarque :** Un booléen est un type qui ne peut prendre que l'une des deux valeurs suivantes : Vrai ou Faux



## Variables

Les variables en programmation sont des "boîtes" qui stockent les informations que nous souhaitons manipuler. Ces variables, comme leur nom l'indique, peuvent varier suite à une opération que nous exécutons sur elles, ou elles peuvent être déclarées comme constantes, c'est-à-dire des boîtes dont la valeur ne change jamais.

Mais comment déclare-t-on une variable ?
Selon le langage de programmation, la déclaration d'une variable varie. Prenons l'exemple de Javascript, dans ce langage, toute variable est déclarée avec les mots-clés `let`, `var` ou `const`, indépendamment de son type.

**NB :** Il existe des conventions de nommage des variables, je vous invite à faire des recherches à ce sujet.

En général, pour déclarer une variable, on utilise la syntaxe suivante :

```C
char mot = "coucou"; //particularité de c : une string est considereé comme tableau de char
bool estPlein = true;
float pi = 3.14;
int monNombre; // On peut déclarer une variable sans lui attribuer une valeur initiale
```

## Conditions et opérateurs

Le premier type d'opération que nous allons voir pour traiter nos données sont les `if` statements ou conditions. Cette opération permet l'exécution d’une suite d'opérations si et seulement si une condition spécifique donnée à l’avance est vérifiée.

La déclaration de cette opération se fait souvent de la manière suivante :

```C
if (condition):
// Exécution de l'opération
else if (condition):
// Exécution de l'opération
else:
// Exécution de l'opération
```

**NB:** Le "else if" et le "else", selon les cas, sont optionnels et non obligatoires. À noter que le "else" n'implique pas une condition à vérifier.

Souvent, dans les conditions à vérifier dans le `if` statement, on utilise des opérateurs. Il existe différents types d'opérateurs selon leur utilité. Dans ce cas, nous allons nous contenter de voir les plus utilisés :

**Opérateurs mathématiques :**

| Opérateur | Dénomination           |
|-----------|------------------------|
| ==        | Égale à                |
| <         | Strictement inférieur à|
| >         | Strictement supérieur à|
| <=        | Inférieure ou égale à  |
| >=        | Supérieur ou égale à  |

**Opérateurs logiques :**

| Opérateur | Dénomination  |
|-----------|---------------|
| &&        | ET logique    |
| \|\|      | OU logique    |
| !         | NON logique   |

**NB:** `!=` signifie différent.

Divergence : il existe ce qu'on appelle un opérateur ternaire. Je vous laisse faire des recherches dessus si cela vous intéresse, mais cela reste du sucre syntaxique.


## Boucles while et do while
Le deuxième type d'opération que l'on peut faire en programmation sont les boucles while ou boucles tant que. Ce type de boucle exécute une opération ou une série d'opérations tant qu'une condition est vraie. Pour ne pas créer des boucles infinies, la boucle while nécessite une condition d'arrêt, voici un exemple :

```c
int a = 0;
while(a <= 3) {
    //exécution d’une opération
    a++; //incrémentation de a chaque itération de la boucle.
}
```
## Les boucles for 

La boucle for, quant à elle, est utilisée lorsque vous connaissez à l'avance le nombre d'itérations à effectuer. Elle se compose de trois parties : l'initialisation, la condition et l'incrémentation. Le bloc d'instructions est exécuté tant que la condition est vraie, et après chaque itération, l'incrémentation est effectuée.

A noter aussi que dans une boucle while, la condition est également vérifiée avant chaque itération du bloc d'instructions. Cependant, dans le cas d'une boucle for, la vérification de la condition se fait après l'exécution de l'incrémentation. Cela signifie que le bloc d'instructions sera exécuté au moins une fois, même si la condition est fausse dès le départ.

voici un example de boucle for en c
```c
int a = 0;
int b = 1;
for(int i = 0; i<6; i++){
    b = b*2;
}
```
**Remarque :** à l'intérieur des boucles for il ne faut jamais toucher a la variable qui a le rôle d'itérateur car peut entrainer des erreurs

## Les fonctions
Souvent lors du développement d’une application, les programmeurs se retrouvent à réécrire les mêmes bouts de code. Non seulement cela ne rend pas le code esthétique, mais cela rend également plus difficile le débogage et l’entretien du code.

Pour résoudre ce problème, les fonctions entrent en jeu. Il s'agit de bouts de code génériques avec des paramètres variables qui manipulent les données et retournent un résultat final. Dans notre code propre et organisé, ces bouts de code seront substitués par l'appel à la fonction, et éventuellement, le résultat retourné sera stocké dans une variable.

Avec les fonctions, les notions de variable globale et variable locale entrent également en jeu. La différence est que le nom des variables déclarées dans une fonction est considéré comme local à la fonction, c'est-à-dire qu'elles sont créées lors de l'appel à la fonction et détruites une fois que le résultat de la fonction est retourné. Par conséquent, il n'est pas grave de donner le même nom à une variable locale qu'à une variable globale (par convention, il est préférable de ne pas le faire).

```c
// Exemple de fonction normale
int somme(int a, int b) {
    int resultat = a + b;
    return resultat;
}

// Exemple de fonction récursive pour calculer le factoriel d'un nombre
int factoriel(int n) {
    if (n == 0) {
        return 1;
    } else {
        return n * factoriel(n - 1);
    }
}

int main() {
    // Appel de la fonction somme
    int resultatSomme = somme(3, 4);    //appel de la fonction somme
    printf("Le résultat de la somme est : %d\n", resultatSomme);

    // Appel de la fonction factoriel
    int nombre = 5;
    int resultatFactoriel = factoriel(nombre); //appel de la fonction recursive factorielle
    printf("Le factoriel de %d est : %d\n", nombre, resultatFactoriel);

    return 0;
}
```
**Remarque :** Je vous ai également donné un exemple de fonction récursive. Si vous êtes curieux/se, vous pouvez approfondir le sujet pour mieux comprendre son fonctionnement.

**Remarque :** Lors de l'appel d'une fonction, le nombre de variables passées en paramètres ainsi que leur type doivent être les mêmes que ceux définis lors de la création de la fonction. Il existe également des fonctions variadiques qui permettent de gérer un nombre variable de paramètres. Je vous invite à approfondir le sujet si vous souhaitez en savoir plus.

**NB:** vous souciez pas du `%d` et `\n` ça reste des particularites du language C

## Les structures de donnes

En programmation, les structures de données te permettent de regrouper des informations liées ensemble. Par exemple, tu pourrais créer une structure de données pour représenter une personne avec des informations comme son nom, son âge et son adresse. Cela rend plus facile la manipulation et l'accès à ces informations quand tu en as besoin dans ton programme. Les structures de données sont un concept important en programmation car elles aident à organiser et gérer les informations de manière efficace.

Les structures de données sont également utilisées pour améliorer les performances de recherche. En fonction du type de données que nous avons et des opérations que nous voulons effectuer, différentes structures de données peuvent être utilisées pour optimiser la recherche.

Par exemple, si nous avons une grande collection d'éléments et que nous voulons rechercher rapidement un élément spécifique, nous pouvons utiliser des structures de données telles que les tableaux indexés, les arbres de recherche binaires ou les tables de hachage. Ces structures de données sont conçues pour organiser les données de manière à permettre une recherche rapide et efficace.

Chaque structure de données a ses propres avantages et limitations en termes de performances et d'utilisation de la mémoire. Il est donc important de choisir la bonne structure de données en fonction des besoins spécifiques de notre programme. En optimisant la structure de données pour les opérations de recherche, nous pouvons améliorer la vitesse et l'efficacité de notre programme.

**NB:** les structures de données sont surtout abordées en Algorithmique.

## projets
- [Cryptage simple](https://github.com/itszaaak/CryptageSimple) (Python)
- [Jeu Morpion](https://github.com/itszaaak/morpion/tree/main) (Python)
- [Plus Grand Palindrome](https://github.com/itszaaak/PlusGrandPalindrome/tree/main) (Python)


