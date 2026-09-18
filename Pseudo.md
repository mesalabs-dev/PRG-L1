# 1. Entrée et Sortie

Le but de la suite de Wallis est de donner une approximation de $\dfrac{\pi}{2}$. C’est à l’utilisateur de dire jusqu’où peut aller la suite en entrant le nombre

Entrée → Nombre $N$ de terme jusqu’ou va aller l’approximation

Sortie → Approximation de $\dfrac{\pi}{2}$

# 2. Décomposition en sous-problème

## 1. Vérifier le terme

La suite de Wallis se compose ainsi :

$$  
\prod_{n=1}^{\infty} \frac{2n}{2n-1} \cdot \frac{2n}{2n+1}  
$$

Etant donné que l’utilisateur doit pouvoir saisir **numérateur** `n` et **dénominateur** `d` il faut vérifié que sont numérateur correspond bien à $2n-1$ par rapport au dénominateur.

Pour cela il faut :

1. Divisé le numérateur `n` et retirer 1
2. Comparer si ce résultat est égal au dénominateur `d`

Ce qui veut dire que l’on va implémenter la condition suivante : $2n- 1 = d$

1. Si la condition est fausse :
    1. Le programme indiquera que le terme saisie n’est pas correct avant se terminer
2. Si la condition est vrai :
    1. Calcule de l’approximation

## 2. Calcul de l’approximation

Pour calculer l’approximation, vu que c’est une suite. Nous allons utilisé un boucle incrémental qui commencera par 1 est se terminera par le numérateur `n` divisé par $2$ et ajouter $1$.

On stockera la suite dans une variable initalisée avant le début de la boucle

# 3. Traduction en pseudo-code

```cpp
//Verfication 
si n/2 - 1 == d
	//Calcul de l'approximation
	a = 1.0 // approximation
	//boucle avec i pour increment
	pour chaque i = 1; si i =< n/2; alors i=i+1
		a = a * ((2*i/(2*i - 1) * 2*i/(2*i + 1))
	afficher a
sinon 
	afficher "Approximation incorrect"
	fin du programme
	
```

# 4. Tester le pseudo code

## Saisie : 8 et 3

→ approximation

Calcul :  
$$
\dfrac{\pi}{2}=\frac{2}{1}\times\frac{2}{3}  
\times\frac{4}{3}\times\frac{4}{5}  
\times\frac{6}{5}\times\frac{6}{7}  
\times\frac{8}{7}\times\frac{8}{9}  
= 2,3014
$$


on s’approche bien de $\pi$

## Saisie 2 : 7 et 3

→ sortie du programme
