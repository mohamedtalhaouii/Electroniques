# **Index des Chapitres :**

- **[Systèmes de Numération & Codage de l’Information](#systèmes-de-numération--codage-de-linformation)**
- **[Algèbre de Bool & Portes Logiques](#algèbre-de-bool--portes-logiques)**
- **[Circuits Combinatoire](#circuits-combinatoire)**
- **[Circuits Séquentielle](#circuits-séquentielle)**


---

# **Systèmes de Numération & Codage de l’Information**
### [🔝 Retour à l'index](#index-des-chapitres-)

## 1. Conversion en décimal

- **Binaire → Décimal :**
    - $`N = \sum_{i=0}^{n-1} b_i \cdot 2^i`$

- **Octal → Décimal :**
    - $`N = \sum_{i=0}^{n-1} o_i \cdot 8^i`$

- **Hexadécimal → Décimal :**
    - $`N = \sum_{i=0}^{n-1} h_i \cdot 16^i`$


## 2. Conversion en binaire

- **Décimal → Binaire :**
  - $`\text{Diviser le nombre décimal par 2.}`$
  - $`\text{Noter le reste (0 ou 1).}`$
  - $`\text{Répéter la division avec le quotient jusqu’à ce que le quotient = 0.}`$
  - $`\text{Le code binaire est la lecture des restes de bas en haut.}`$


- **Octal → Binaire :**
$`\text{Chaque chiffre octal } o_i \rightarrow \text{ bloc binaire de 3 bits}`$

| Décimal | Octal | Binaire |
| ----- | ----- | ------- |
| 0     | 0     | 000     |
| 1     | 1     | 001     |
| 2     | 2     | 010     |
| 3     | 3     | 011     |
| 4     | 4     | 100     |
| 5     | 5     | 101     |
| 6     | 6     | 110     |
| 7     | 7     | 111     |

- **Hexadécimal → Binaire :**
$`\text{Chaque chiffre hexadécimal } h_i \rightarrow \text{ bloc binaire de 4 bits}`$

| Décimal | Hex | Binaire |
| ------- | --- | ------- |
| 0       | 0   | 0000    |
| 1       | 1   | 0001    |
| 2       | 2   | 0010    |
| 3       | 3   | 0011    |
| 4       | 4   | 0100    |
| 5       | 5   | 0101    |
| 6       | 6   | 0110    |
| 7       | 7   | 0111    |
| 8       | 8   | 1000    |
| 9       | 9   | 1001    |
| 10      | A   | 1010    |
| 11      | B   | 1011    |
| 12      | C   | 1100    |
| 13      | D   | 1101    |
| 14      | E   | 1110    |
| 15      | F   | 1111    |


## 3. Codage des entiers négatifs

- **Signe + Valeur Absolue :**
    - $`N = s|N|`$

> Avec :
> - ( s = 0 ) → nombre positif
> - ( s = 1 ) → nombre négatif

- **Complément à 1 (C1) :**
    - $`N_{C1} = \overline{N}`$

- **Complément à 2 (C2) :**
    - $`N_{C2} = N_{C1} + 1`$

> Plage sur ( n ) bits :
> - $`-2^{n-1} \leq N \leq 2^{n-1}-1`$


## 4. Codage des nombres réels

- **Virgule fixe :**
    - $`N = \text{Partie entière} + \sum_{i=1}^{m} f_i \cdot 2^{-i}`$

- **Virgule flottante (IEEE 754) :**
    - $`N = (-1)^s \times 1.m \times 2^{(E - \text{biais})}`$

> **Biais (exponent bias) :**
> - **Simple précision :** $`\text{biais} = 127`$
> - **Double précision :** $`\text{biais} = 1023`$


## 5. Codage BCD (Binary Coded Decimal)

- **Conversion Décimal → BCD :**
$`\text{1 chiffre décimal } d \rightarrow \text{mot de 4 bits } (d_3 d_2 d_1 d_0)`$

- **Tableau BCD (Binary Coded Decimal) :**

| Décimal  | BCD  |
| ----- | ------ |
| 0     | 0000 |
| 1     | 0001 |
| 2     | 0010 |
| 3     | 0011 |
| 4     | 0100 |
| 5     | 0101 |
| 6     | 0110 |
| 7     | 0111 |
| 8     | 1000 |
| 9     | 1001 |



## 6. Codage Gray (Code réfléchi)

- **Conversion Binaire → Gray  ( $`B = b_n b_{n-1} ... b_1 b_0`$ ) :**
 
  - Le bit de poids fort reste identique :
    $`g_n = b_n`$
  
  - Chaque bit suivant :
    $`g_i = b_{i+1} \oplus b_i`$

> où ( $`\oplus`$ ) = XOR.

- **Conversion Gray → Binaire  ( $`G = g_n g_{n-1} ... g_1 g_0 `$ ) :**

  - Le bit de poids fort :
    $`b_n = g_n`$
  
  - Chaque bit suivant :
    $`b_i = b_{i+1} \oplus g_i`$

| Décimal | Binaire | Gray |
| ------- | ------- | ---- |
| 0       | 0000    | 0000 |
| 1       | 0001    | 0001 |
| 2       | 0010    | 0011 |
| 3       | 0011    | 0010 |
| 4       | 0100    | 0110 |
| 5       | 0101    | 0111 |
| 6       | 0110    | 0101 |
| 7       | 0111    | 0100 |
| 8       | 1000    | 1100 |
| 9       | 1001    | 1101 |
| 10      | 1010    | 1111 |
| 11      | 1011    | 1110 |
| 12      | 1100    | 1010 |
| 13      | 1101    | 1011 |
| 14      | 1110    | 1001 |
| 15      | 1111    | 1000 |

## 7. Codage ASCII

- **Caractères [ASCII](https://www.ascii-code.com/) :**
$`\text{Code binaire} = \text{valeur décimale ASCII convertie en binaire (7 bits)}`$

- **Plages :**

  * **Chiffres :**
    $`48 \rightarrow 57`$
    
  * **Lettres majuscules :**
    $`65 \rightarrow 90`$
    
  * **Lettres minuscules :**
    $`97 \rightarrow 122`$
    
  * **Codes contrôle :**
    $`0 \rightarrow 31`$

---

# **Algèbre de Bool & Portes Logiques**
### [🔝 Retour à l'index](#index-des-chapitres-)

L'algèbre de Bool est le fondement des circuits logiques, utilisée pour modéliser des opérations logiques binaires.

### **Opérations Booléennes de Base :**
  - **ET** (·) : $` A \cdot B `$
  - **OU** (+) : $` A + B `$
  - **NON** (−) : $` \overline{A} `$
  
### **Propriétés Importantes :**

- **Idempotence :**
    - $`A + A = A`$
    - $`A \cdot A = A`$

- **Absorption :**
    - $`A + (A \cdot B) = A`$
    - $`A \cdot (A + B) = A`$

- **Domination :**
    - $`A + 1 = 1`$
    - $`A \cdot 0 = 0`$

- **Identité :**
    - $`A + 0 = A`$
    - $`A \cdot 1 = A`$

- **Complémentation :**
    - $` A + \bar{A} = 1`$
    - $`A \cdot \bar{A} = 0`$

- **Double négation :**
    - $`\bar{\bar{A}} = A`$

- **Réduction :**
  - $`A + (\bar{A} \cdot B) = A + B`$
  - $`A \cdot (\bar{A} + B) = A \cdot B`$

- **Combinaison identité-complément :**
  - $`AB + A\bar{B} = A`$
  - $`(A + B)(A + \bar{B}) = A`$

- **Distribution inverse :**
  - $`A + BC = (A + B)(A + C)`$

- **Théorèmes de De Morgan :**
  - $` \overline{A \cdot B} = \overline{A} + \overline{B} `$
  - $` \overline{A + B} = \overline{A} \cdot \overline{B} `$


### **Mintermes, Maxtermes & Formes Canoniques :**

- **Mintermes (Somme de Produits – SOP) :** Un **minterme** est un produit logique **(ET)**.
    - Représenté par :
      - bit = **1** → variable non barrée
      - bit = **0** → variable barrée

> Un minterme vaut **1 pour une seule ligne** de la table de vérité.

- **Forme canonique SDP :**
    - $`F = \sum m_i \quad\text{(sommes des mintermes où F = 1)}`$


- **Maxtermes (Produit de Sommes – POS) :** Un **maxterme** est une somme logique **(OU)**.

    - Représenté par (inverse des mintermes !) :
        - bit = **0** → variable non barrée
        - bit = **1** → variable barrée

> Un maxterme vaut **0 pour une seule ligne** de la table.

- **Forme canonique POS :**
    - $`F = \prod M_i \quad\text{(produit des maxtermes où F = 0)}`$




### **Symbole des Portes Logiques :**
![Portes-Logique](https://github.com/user-attachments/assets/0afc9b1d-eef1-434d-8a1f-523a396cc172)

### **Table de vérité des portes logiques :**
Chaque circuit combinatoire peut être décrit à l'aide d'une table de vérité, qui liste toutes les combinaisons possibles des entrées et leur résultat correspondant.

| Entrée A | Entrée B | ET (A . B) | OU (A + B) | XOR (A ⊕ B) | NON A |
|----------|----------|------------|------------|-------------|-------|
| 0        | 0        | 0          | 0          | 0           | 1     |
| 0        | 1        | 0          | 1          | 1           | 1     |
| 1        | 0        | 0          | 1          | 1           | 0     |
| 1        | 1        | 1          | 1          | 0           | 0     |

---

# **Circuits Combinatoire**
### [🔝 Retour à l'index](#index-des-chapitres-)

Dans la logique combinatoire, la sortie dépend uniquement des entrées actuelles.

## **Circuits combinatoires courants :**

### Additionneur Demi (Half-Adder) :
  - Permet l'addition de deux bits.
  - Sortie : `Somme = A ⊕ B`, `Retenue = A · B`
  - **Logigramme :**
  
![Half-Adder](https://github.com/user-attachments/assets/6565d1d7-28b6-4385-8204-bb6083dacebb)

### Additionneur Complet (Full-Adder) :
  - Ajoute trois bits (A, B, et une retenue `C_in`).
  - Sortie : `Somme = A ⊕ B ⊕ C_in`, `Retenue = (A · B) + (C_in · (A ⊕ B))`
  - Logigramme :

![Full-Adder](https://github.com/user-attachments/assets/60afee00-3e0e-4381-8bd1-2ae8769a24cb)

### Multiplexeur (MUX) :
  - Sélectionne une entrée parmi plusieurs (2^n entrées pour n bits de sélection).
  - Formule de sortie : `S = A · ¬S + B · S`
  - **Logigramme :**

![MUX4](https://github.com/user-attachments/assets/9f3a279a-1c50-43a0-a587-d940c0d50a35)

### Démultiplexeur (DEMUX) :
  - Prend un signal d'entrée et le distribue sur plusieurs sorties.
  - Inverse du MUX.
  - **Logigramme :**

![DEMUX4](https://github.com/user-attachments/assets/b77412e8-14b8-4cba-ac46-74eeff30b8bf)

### Décodeur :
  - Convertit un code binaire en une seule sortie activée (utilisé dans la gestion de la mémoire ou la sélection de lignes).
  - **Logigramme :**

![Decodeur-4bit](https://github.com/user-attachments/assets/cf268a0c-0613-49ee-8dc9-4d65ca2b764e)

### Encodeur :
  - Inverse du décodeur : il convertit plusieurs signaux d'entrée en un code binaire.
  - **Logigramme :**

![Codeur-4bit](https://github.com/user-attachments/assets/4e370849-0151-4098-b7fa-423af09cf32b)

### Décodeur - 7-Segments :
- **Formules Algébriques pour le Décodeur BCD - 7 Segments :**

  1- **Segment a :**  
     $`a = B + D + A C + \overline{A} \overline{C}`$
  
  2- **Segment b :**  
     $`b = \overline{C} + A B + \overline{A} \, \overline{B}`$
  
  3- **Segment c :**  
     $`c = A + C + \overline{B}`$
  
  4- **Segment d :**  
     $`d = D + \overline{A} \, \overline{B} + B \, \overline{C} + \overline{C} \, \overline{A} + A B C`$
  
  5- **Segment e :**  
     $`e = \overline{A} B + \overline{A} C`$
  
  6- **Segment f :**  
     $`f = D + \overline{A} \, \overline{B} + B \, \overline{C} + C \, \overline{A}`$
  
  7- **Segment g :**  
     $`g = D + \overline{A} \, \overline{C} + C \, \overline{B} + B \, \overline{C}`$

- **Logigramme :**

![7-Segment](https://github.com/user-attachments/assets/cd81b6af-1950-4c2e-8e6a-081e28c74d43)

### Comparateur :
  - Un circuit qui compare deux nombres binaires et détermine leur relation (égal, supérieur, inférieur).
  - Sorties typiques : `A = B, A > B, A < B`.
  - **Logigramme :**

![Comparateur-2bit](https://github.com/user-attachments/assets/07c13c1b-559f-4fca-b98e-41b52d6c464a)

### Unité Arithmétique et Logique (UAL) :
  - L'UAL effectue des opérations arithmétiques et logiques telles que l'addition, la soustraction, ET, OU, etc.
  - **Logigramme :**

![UAL](https://github.com/user-attachments/assets/1e562ed6-f423-456e-8f43-b50dc92a8164)

## **Simplification des Circuits Combinatoires :**
- **Table de vérité** : Outil pour vérifier toutes les combinaisons possibles des entrées et leurs résultats.
- **Tableau de Karnaugh** : Utile pour simplifier des fonctions à plusieurs variables en repérant les groupes de 1.


# **Circuits Séquentielle**
### [🔝 Retour à l'index](#index-des-chapitres-)
Un système séquentiel est un système logique dont l’état des variables de sortie dépend non seulement de
l’état des variables d’entrée mais aussi de l’état précédant des variables de sortie. 

![logique-sequentielle](https://github.com/user-attachments/assets/a2bb8ae8-8510-4579-b787-74b9a01bc90d)


### Bascule RS (Set-Reset) - **Asynchrone**

| **Définition**                                                                                                                                                                                                                     | **Symbole**                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| La bascule RS est un type de bascule qui a deux entrées (Set et Reset) et une sortie. Elle permet de mémoriser l'état logique (1 ou 0) en fonction des valeurs de ses entrées. Elle fonctionne en mode asynchrone.                | ![RS](https://github.com/user-attachments/assets/0d75ad33-9923-4913-89a8-98a6fa3c3c77) |

- **Équation Logique** :
  - $` Q_{n+1} = S + \overline{R} \cdot Q_n `$

- **Table de Vérité** :

  | S (Set) | R (Reset) | Q (Sortie)       | Q̅ (Sortie complémentaire) | **Commentaire**         |
  |---------|-----------|------------------|----------------------------|--------------------------|
  | 0       | 0         | Qn (Maintien)    | Q̅n (Maintien)             | Pas de changement d'état |
  | 0       | 1         | 0                | 1                          | Réinitialisation         |
  | 1       | 0         | 1                | 0                          | Mise à 1                 |
  | 1       | 1         | Indéterminé      | Indéterminé                | État non défini          |

- **Logigramme avec NAND** :

![RS NAND](https://github.com/user-attachments/assets/29a6fee3-ffb6-4abc-a13f-1de3476bf8e1)

- **Logigramme avec NOR** :

![RS NOR](https://github.com/user-attachments/assets/98bfc5a6-8cf3-4438-a1bf-1ac51a01d85f)

- **Chronogramme** :

![RS](https://github.com/user-attachments/assets/70ed1c2e-9b9a-4b95-ad0f-5d4a36f9d076)

---

### Bascule RSH (Reset-Set-Hold) - **Synchrone**

| **Définition**                                                                                                                                                                                                                     | **Symbole (Front Montant)**                  | **Symbole (Front Descendant)**                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|-------------------------------------------------|
| La bascule RSH (Reset-Set-Hold) synchronisée possède trois états : Reset, Set, et Hold. Elle nécessite un signal d'horloge pour changer d'état, ce qui la rend synchrone. "H" est ici l'entrée d'horloge.                           | ![RSH MONT](https://github.com/user-attachments/assets/4c394375-0cc4-4c0e-9ee2-7b806e9bfbf4)| ![RSH DESC](https://github.com/user-attachments/assets/cc1f626d-06ee-4294-b642-6d9000ed2463)|

- **Équation Logique** :
  - $` Q_{n+1} = S + \overline{R} \cdot Q_n `$ lorsque $` H `$ est sur un front montant

- **Table de Vérité** :

  | S (Set) | R (Reset) | H (Horloge) | Q (Sortie)       | Q̅ (Sortie complémentaire) | **Commentaire**                   |
  |---------|-----------|-------------|------------------|----------------------------|------------------------------------|
  | 0       | 0         | 0           | Qn (Maintien)    | Q̅n (Maintien)             | Pas de changement d'état (Hold)   |
  | 0       | 0         | 1 (↑)       | Qn (Maintien)    | Q̅n (Maintien)             | Pas de changement d'état          |
  | 0       | 1         | 1 (↑)       | 0                | 1                          | Réinitialisation                  |
  | 1       | 0         | 1 (↑)       | 1                | 0                          | Mise à 1                          |

- **Logigramme** :

![RSH](https://github.com/user-attachments/assets/dfbecc44-f077-425c-885f-7e4ad0c33386)

- **Chronogramme** :

![RSH](https://github.com/user-attachments/assets/a3e87faf-c6b2-40a3-8c96-a4f5277f99b8)

---

### Bascule JK - **Synchrone**

| **Définition**                                                                                                                                                                                                                     | **Symbole (Front Montant)**                  | **Symbole (Front Descendant)**                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|-------------------------------------------------|
| La bascule JK est une amélioration de la bascule RS qui évite l'état indéterminé. Elle a deux entrées J (Set) et K (Reset) et nécessite un signal d'horloge pour changer d'état, ce qui en fait une bascule synchrone.             | ![JK MONT](https://github.com/user-attachments/assets/ce814654-99a0-4b03-8f51-43a260d60de7)| ![JK DESC](https://github.com/user-attachments/assets/f101b152-daaf-45f1-8ba8-5a6baed80c33)|

- **Équation Logique** :
  - $` Q_{n+1} = J \cdot \overline{Q_n} + \overline{K} \cdot Q_n `$ lorsque l’horloge est sur un front montant.

- **Table de Vérité** :

  | J       | K       | H (Horloge) | Q (Sortie)       | Q̅ (Sortie complémentaire) | **Commentaire**             |
  |---------|---------|-------------|------------------|----------------------------|------------------------------|
  | 0       | 0       | 1 (↑)       | Qn (Maintien)    | Q̅n (Maintien)             | Pas de changement d'état     |
  | 0       | 1       | 1 (↑)       | 0                | 1                          | Réinitialisation             |
  | 1       | 0       | 1 (↑)       | 1                | 0                          | Mise à 1                     |
  | 1       | 1       | 1 (↑)       | Q̅n (Bascule)    | Qn (Bascule)               | Inversion de l'état (toggle) |

- **Logigramme** :

![JK](https://github.com/user-attachments/assets/9603aaf5-0547-4a03-94ef-f1773be15245)

- **Chronogramme** :

![JK](https://github.com/user-attachments/assets/b8aeb8a7-89b2-4eec-ba30-6819b3adf435)

---

### Bascule D (Delay) - **Synchrone**

| **Définition**                                                                                                                                                                                                                     | **Symbole (Front Montant)**                  | **Symbole (Front Descendant)**                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|-------------------------------------------------|
| La bascule D ou bascule à retard est utilisée pour introduire un délai dans un circuit. Elle a une seule entrée D et prend en compte cette entrée lors des transitions d'horloge, ce qui en fait une bascule synchrone.           | ![D MONT](https://github.com/user-attachments/assets/767720e8-a4d9-41a0-902d-c114ecfc932b)| ![D DESC](https://github.com/user-attachments/assets/b3093dcd-e7cd-473f-a083-759454ec98dd)|

- **Équation Logique** :
  - $` Q_{n+1} = D `$ lorsque l’horloge est sur un front montant.

- **Table de Vérité** :

  | D       | H (Horloge) | Q (Sortie)       | Q̅ (Sortie complémentaire) | **Commentaire**                 |
  |---------|-------------|------------------|----------------------------|----------------------------------|
  | 0       | 1 (↑)       | 0                | 1                          | Réinitialisation                |
  | 1       | 1 (↑)       | 1                | 0                          | Stockage de l'entrée à 1        |

- **Logigramme** :

![D](https://github.com/user-attachments/assets/3da34744-4206-4cb0-92cf-6c2212a77dbd)

- **Chronogramme** :

![D](https://github.com/user-attachments/assets/071510a9-6c8b-4117-ac65-fd27ed56d168)

---

### Bascule T (Toggle) - **Synchrone**

| **Définition**                                                                                                                                                                                                                     | **Symbole (Front Montant)**                  | **Symbole (Front Descendant)**                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|-------------------------------------------------|
| La bascule T est un type de bascule qui inverse son état à chaque impulsion d'horloge. Elle se déclenche avec un signal d'horloge, et son état bascule à chaque front actif.                   | ![T MONT](https://github.com/user-attachments/assets/995c30b0-21a9-40fb-947f-74b0d9f765ec)| ![T DESC](https://github.com/user-attachments/assets/bee63aaf-7459-4833-b481-61b6e17fac59)|

- **Équation Logique** :
  - $` Q_{n+1} = Q_n \oplus T `$ lorsque l’horloge est sur un front montant.

- **Table de Vérité** :

  | T       | H (Horloge) | Q (Sortie)       | Q̅ (Sortie complémentaire) | **Commentaire**                  |
  |---------|-------------|------------------|----------------------------|-----------------------------------|
  | 0       | 1 (↑)       | Qn (Maintien)    | Q̅n (Maintien)             | Pas de changement d'état         |
  | 1       | 1 (↑)       | Q̅n (Bascule)    | Qn (Bascule)               | Inversion de l'état (toggle)     |

- **Logigramme** :

![T](https://github.com/user-attachments/assets/f3b2e098-2db0-4d94-89bc-b251759a2c74)

- **Chronogramme** :

![T](https://github.com/user-attachments/assets/8b11b6bc-08ca-4441-a79c-d16663c8a7dd)


---

### 6. Compteur Asynchrone (Asynchronous Counter)

| **Définition**                                                                                                                                                                                                                     | **Symbole (Montée)**                           | **Symbole (Décompte)**                        |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|------------------------------------------------|
| Un compteur asynchrone, aussi appelé compteur à décalage ou "ripple counter," change d'état de manière décalée. Seul le premier bit reçoit directement l'impulsion d'horloge, et les autres bits changent en cascade. Il peut être configuré pour compter vers le haut (montée) ou vers le bas (décompte). Les transitions ne se produisent donc pas simultanément pour chaque bit. | *(Espace pour le symbole de montée)*           | *(Espace pour le symbole de décompte)*         |

- **Équations Logiques** :
  - Compteur de montée (Up Counter) : Chaque bascule change d'état lorsque le bit précédent passe de 1 à 0.
  - Compteur de décompte (Down Counter) : Chaque bascule change d'état lorsque le bit précédent passe de 0 à 1.

- **Table de Vérité** (exemple pour un compteur 3 bits) :

  | Compte | État (Montée) | État (Décompte) | **Commentaire**             |
  |--------|---------------|-----------------|-----------------------------|
  | 0      | 000           | 111             | État initial                |
  | 1      | 001           | 110             | Premier comptage            |
  | 2      | 010           | 101             | Deuxième comptage           |
  | 3      | 011           | 100             | Troisième comptage          |
  | 4      | 100           | 011             | Quatrième comptage          |
  | ...    | ...           | ...             | Continue selon la limite    |

- **Logigramme** :

  *(Espace pour le logigramme du compteur asynchrone de montée ou de décompte)*

- **Chronogramme** :

  *(Espace pour le chronogramme du compteur asynchrone)*

<hr>
<h3 align="center"> 🧑🏻‍💻 | Made By : <a href="https://github.com/mohamedtalhaouii" target="_blank">Mohamed Talhaoui</a></h3>
