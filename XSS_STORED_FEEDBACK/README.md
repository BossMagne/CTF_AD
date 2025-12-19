##########################################

ALEXANDRE DENIS

##########################################

CTF


2nd attaque XSS : Attaque par injection XSS « FEEDBACK » :

Pour réaliser l'attaque, on essaye d'exécuter des commandes dans le formulaire du site :

---> exemple de commande utilisée : <script>alerte(1)</script>

<img width="605" height="311" alt="Image" src="https://github.com/user-attachments/assets/d7d50be1-2763-4c2d-889f-d6515a461093" />

Cependant, après moulte tentatives, il semblerait que le serveur filtre la balise <script>.

On essaye donc d'utiliser des combinaisons de caractères au hasard :

<img width="1687" height="791" alt="Image" src="https://github.com/user-attachments/assets/d264fd26-df82-438e-91b1-4f3033703fc2" />

On trouve le Flag :

<img width="1693" height="869" alt="Image" src="https://github.com/user-attachments/assets/07342ecc-68a1-410d-bcea-7ca602427563" />

Flag trouvé : 0fbb54bbf7d099713ca4be297e1bc7da0173d8b3c21c1811b916a3a86652724e
