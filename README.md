# testtp1

# TVA

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

# Badminton

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

# Calculer la rubrique de paie EUNI

* Partition

