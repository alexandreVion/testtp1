# Rendu TP 1

Etudiants | Date | Sujet
:---|:---|:---
Nathan Guilhot et Alexandre Vion | 05/02/2020 | Automatiser les tests d'une application web à l'aide de Selenium IDE.

# Introduction

Lors de ce premier TP nous devons faire des test sur différentes mini-applications faite en Javascript. Ces test sont des 
test de détection a fin de detecter d'éventuelles erreurs. Ces test sont réaliser en boite noire c'est à dire qu'on a aucune 
visualisation sur le code.

# Première partie

* Objectifs

Sur cette première partie on doit réaliser des test sur une fonction qui calcule la TVA.

* Partition TVA

| taux 0%   | 0 | décimal | entier                |                           |
|-----------|---|---------|-----------------------|---------------------------|
| taux 10%  | 0 | décimal | nombre multiple de 10 | nombre non multiple de 10 |
| taux 20 % | 0 | décimal | nombre multiple de 5  | nombre non multiple de 5  |

* Test TVA

| Entrée (taux Tva) | Entrée (Montant HT) | Attendu (Montant TVA) | Attendu (Montant TTC) | Obtenue (Montant TVA) | Obtenue (Montant TTC) |        Test        |
|:-----------------:|:-------------------:|:---------------------:|:---------------------:|:---------------------:|:---------------------:|:------------------:|
|         0%        |          4          |           0           |           4           |           0           |           4           | :white_check_mark: |
|         0%        |         3.25        |           0           |          3.25         |           0           |           3           |     :no_entry:     |
|        10%        |         1.89        |          0.19         |          2.08         |          0.19         |           2           |     :no_entry:     |
|        10%        |          10         |           1           |           11          |           1           |           11          | :white_check_mark: |
|        20%        |          5          |           1           |           6           |           1           |           6           | :white_check_mark: |
|        20%        |          4          |          0.80         |          4.80         |          0.80         |           4           |     :no_entry:     |

* Conclusion

On remarque que les résultats des calculs montant TTC ne sont pas toujours bon. On remarque aussi que les calculs faux sont
ceux qui devrait contenir des nombres décimaux. On peut en déduire que le calcul des montants TTC se fait avec un INT ( 
un nombre entier) et qui du coup arrondi la valeur et empêche d'avoir le bon résultat. 

# Seconde partie Badminton

* Objectifs

Sur cette seconde partie on doit réaliser des test sur une fonction qui calcule la catégorie d'un joueur de badminton.

* Partition

| 0 | 1-17 | 18 | 19-33 | 34 | 35 | 36-38 | 39 | 40 | 41-43 | 44 | 45 | 46-48 | 49 | 50 | 51-53 | 54 | 55 | 56-58 | 59 | 60 | 61-63 | 64 | 65 | 66-68 | 69 | 70 | 71+ |
|---|------|----|-------|----|----|-------|----|----|-------|----|----|-------|----|----|-------|----|----|-------|----|----|-------|----|----|-------|----|----|-----|

* Test

| Entrée | Attendu   | Obtenue    | test               |
|--------|-----------|------------|--------------------|
| 0      | Junior    | Junior     | :white_check_mark: |
| 4      | Junior    | Junior     | :white_check_mark: |
| 18     | Sénior    | Sénior     | :white_check_mark: |
| 25     | Sénior    | Sénior     | :white_check_mark: |
| 34     | Sénior    | Sénior     | :white_check_mark: |
| 35     | Vétéran 1 | Sénior     | :no_entry:         |
| 37     | Vétéran 1 | Vétéran 1  | :white_check_mark: |
| 39     | Vétéran 1 | Vétéran 1  | :white_check_mark: |
| 40     | Vétéran 2 | Vétéran 2  | :white_check_mark: |
| 42     | Vétéran 2 | Vétéran 2  | :white_check_mark: |
| 44     | Vétéran 2 | Vétéran 2  | :white_check_mark: |
| 45     | Vétéran 3 | Vétéran 3  | :white_check_mark: |
| 46     | Vétéran 3 | Vétéran 3  | :white_check_mark: |
| 49     | Vétéran 3 | Vétéran 3  | :white_check_mark: |
| 50     | Vétéran 4 | Vétéran 4  | :white_check_mark: |
| 53     | Vétéran 4 | Vétéran 4  | :white_check_mark: |
| 54     | Vétéran 4 | Vétéran 4  | :white_check_mark: |
| 55     | Vétéran 5 | Vétéran 5  | :white_check_mark: |
| 57     | Vétéran 5 | Vétéran 5  | :white_check_mark: |
| 59     | Vétéran 5 | Vétéran 5  | :white_check_mark: |
| 60     | Vétéran 6 | Vétéran 6  | :white_check_mark: |
| 62     | Vétéran 6 | Vétéran 6  | :white_check_mark: |
| 64     | Vétéran 6 | Vétéran 6  | :white_check_mark: |
| 65     | Vétéran 7 | Vétéran 7  | :white_check_mark: |
| 68     | Vétéran 7 | Vétéran 7  | :white_check_mark: |
| 69     | Vétéran 7 | Vétéran 7  | :white_check_mark: |
| 70     | Vétéran 8 | Vétéran 8  | :white_check_mark: |
| 144    | Vétéran 8 | Vétéran 22 | :no_entry:         |

* Conclusion

Ici on detecte deux erreurs. La première est qu'avec l'entrée 35 pour l'age, qui est une valeur limite, on a pas la bonne 
sortie. L'erreur provient certainement du fait que les bornes n'ont pas été implémentées correctement. La deuxième erreur 
provient de la partie 70+ de la partition. On se retrouve avec un vétéran 22 a la place d'un vétéran 8 pour l'entré 144. 
L'erreur pourrait venir du fait que a partir du catégorie vétéran 1, les catégories changes touts les 5 ans avec une 
incrémentations sur le vétéran. Ce qui a peut être fait par une boucle qui ne s'arrete pas lors des entrées 70+ et va
donc donner des rangs de vétérans qui n'existe pas.

# Troisème partie

* Objectifs 

Sur cette troisième partie on doit réaliser des test sur une fonction qui calcule la rubrique de paie EUNI. Pour réaliser 
cet objectifs on a fixer le smic a 1000 €.

* Partition 

| 0 | 1-1499 | 1500 | 1501-2999 | 3000 | 3000+ |
|---|--------|------|-----------|------|-------|

* Test


| Entrée | Attendu  (Tranche A / Tranche B / Total) | Obtenue (Tranche A / Tranche B / Total) |        Test        |
|:------:|:----------------------------------------:|:---------------------------------------:|:------------------:|
|    0   |                 0 / 0 / 0                |                0 / 0 / 0                | :white_check_mark: |
|   900  |                 0 / 0 / 0                |                0 / 0 / 0                | :white_check_mark: |
|  1500  |                 0 / 0 / 0                |                0 / 0 / 0                | :white_check_mark: |
|  1800  |                 3 / 0 / 3                |                3 / 0 / 3                | :white_check_mark: |
|  3000  |                15 / 0 / 15               |               15 / 0 / 15               | :white_check_mark: |
|  4000  |               15 / 20 / 35               |               18 / 20 / 35              |     :no_entry:     |
|  1501  |              0.01 / 0 / 0.01             |             0.01 / 0 / 0.01             | :white_check_mark: |
|  3001  |             15 / 0.02 / 15.02            |            18 / 0.02 / 18.02            |     :no_entry:     |

* Conclusion

L'erreur trouver dans cette fonction de calcul de la rubrique de paie EUNI sur trouve sur les résultats des calculs de la
tranche B. On remarque qu'au lieu d'avoir le résultat attendu en se retrouve avec la valeur 18. Cette valeur on la retrouve
avec le tableau de test pour un smic a 1200€. On peut en déduire que le calcul de la tranche se fait avec une valeur fixe a 
1200 eu lieu de prendre la valeur donné.

# Quatrième partie Code PIN

* Objectifs

Sur cette quatrième partie on doit réaliser des test sur une fonction qui vérifie un code PIN.

* Partition

| 0 | 0-999 | 0000 | 9999 | 00000 | 00001+ |
|---|-------|------|------|-------|--------|

* Test

| Entrée | Attendu | Obtenue |        Test        |
|:------:|:-------:|:-------:|:------------------:|
|  0000  |   true  |  false  |     :no_entry:     |
|    1   |  false  |  false  | :white_check_mark: |
|   12   |  false  |  false  | :white_check_mark: |
|   123  |  false  |  false  | :white_check_mark: |
|  1234  |   true  |   true  | :white_check_mark: |
|  5678  |   true  |   true  | :white_check_mark: |
|  9012  |   true  |  false  |     :no_entry:     |
|  9999  |   true  |   true  | :white_check_mark: |
|  12564 |  false  |  false  | :white_check_mark: |

* Conclusion

Les erreurs qu'on remarque lors de ce test proviennet quand le chiffre 0 est présent dans le code PIN. On peut en déduire que
la fonction ne prend pas en compte le chiffre 0 lors des fonctions de vérification du code PIN.


