# **Logique Combinatoire**

### **1. Algèbre de Bool**
L'algèbre de Bool est le fondement des circuits logiques, utilisée pour modéliser des opérations logiques binaires.

### **Table de vérité des portes logiques :**
Chaque circuit combinatoire peut être décrit à l'aide d'une table de vérité, qui liste toutes les combinaisons possibles des entrées et leur résultat correspondant.

| Entrée A | Entrée B | ET (A . B) | OU (A + B) | XOR (A ⊕ B) | NON A |
|----------|----------|------------|------------|-------------|-------|
| 0        | 0        | 0          | 0          | 0           | 1     |
| 0        | 1        | 0          | 1          | 1           | 1     |
| 1        | 0        | 0          | 1          | 1           | 0     |
| 1        | 1        | 1          | 1          | 0           | 0     |

---

### **Théorèmes Importants :**
- **De Morgan** : `¬(A · B) = ¬A + ¬B` et `¬(A + B) = ¬A · ¬B`
- **Annulation** : `A · 0 = 0`, `A + 1 = 1`
- **Complémentarité** : `A · ¬A = 0`, `A + ¬A = 1`

### **Simplification des Fonctions Booléennes :**
Utilisez les lois d’absorption, de distributivité, de De Morgan, etc., pour simplifier des expressions logiques complexes et minimiser le nombre de portes dans un circuit. Les tableaux de Karnaugh (K-map) sont souvent utilisés pour la simplification visuelle des fonctions booléennes jusqu'à 6 variables.

---

## **2. Logique Combinatoire**
Dans la logique combinatoire, la sortie dépend uniquement des entrées actuelles.

### **Circuits combinatoires courants :**

- **Additionneur Demi (Half-Adder)** :
  - Permet l'addition de deux bits.
  - Sortie : `Somme = A ⊕ B`, `Retenue = A · B`
  
![Demi-Adder](https://github.com/user-attachments/assets/37797372-ca2e-4eb8-9217-bd775b12e1f6)

- **Additionneur Complet (Full-Adder)** :
  - Ajoute trois bits (A, B, et une retenue `C_in`).
  - Sortie : `Somme = A ⊕ B ⊕ C_in`, `Retenue = (A · B) + (C_in · (A ⊕ B))`

![Full-Adder](https://github.com/user-attachments/assets/7e348512-439f-4247-8be5-19a2b45a603b)

- **Multiplexeur (MUX)** :
  - Sélectionne une entrée parmi plusieurs (2^n entrées pour n bits de sélection).
  - Formule de sortie : `S = A · ¬S + B · S`

![MUX4](https://github.com/user-attachments/assets/346347a8-ef02-4f52-b276-64de6ac8418e)

- **Démultiplexeur (DEMUX)** :
  - Prend un signal d'entrée et le distribue sur plusieurs sorties.
  - Inverse du MUX.

*(Ajouter la représentation ici)*

- **Décodeur** :
  - Convertit un code binaire en une seule sortie activée (utilisé dans la gestion de la mémoire ou la sélection de lignes).

*(Ajouter la représentation ici)*

- **Encodeur** :
  - Inverse du décodeur : il convertit plusieurs signaux d'entrée en un code binaire.

*(Ajouter la représentation ici)*

### **Simplification des Circuits Combinatoires :**
- **Table de vérité** : Outil pour vérifier toutes les combinaisons possibles des entrées et leurs résultats.
- **Map de Karnaugh** : Utile pour simplifier des fonctions à plusieurs variables en repérant les groupes de 1.
