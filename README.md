# Controle_Position_de_MoteurDC_avec_Potentio

Ce projet Arduino contrôle un moteur DC via un pont en H (L293D) en se basant sur la lecture d'un potentiomètre. L’objectif est de maintenir le moteur à une position cible prédéfinie.

## 🛠 Matériel utilisé

- Arduino Uno 
- Moteur DC
- Driver moteur L293D
- Potentiomètre
- Câbles de connexion
- Alimentation externe (3V)

## ⚙️ Fonctionnement

- Le potentiomètre est lu via la broche analogique `A0`.
- Le moteur est contrôlé via les broches `enA` (PWM), `in1`, et `in2`.
- La position cible est fixée au milieu de la plage analogique (valeur 512).
- Si la position actuelle diffère de plus de ±10 par rapport à la cible, le moteur tourne dans la bonne direction jusqu'à s'en approcher.
- La vitesse est proportionnelle à l'erreur (plus l'écart est grand, plus le moteur tourne vite).

## 🔌 Schéma de câblage

| Composant     | Broche Arduino |
|---------------|----------------|
| Potentiomètre | A0             |
| L293D enA     | 9              |
| L293D in1     | 4              |
| L293D in2     | 5              |

## 📟 Code Arduino

Le code lit la position du potentiomètre, calcule l'écart par rapport à la position cible, puis ajuste la direction et la vitesse du moteur en conséquence.
