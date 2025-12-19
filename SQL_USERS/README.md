##########################################

ALEXANDRE DENIS

##########################################

CTF

1ère attaque SQL : « search_member_sql_inj_error_based »

Nous allons nous intéresser a la section search du site.

on peut essayer en premier lieu de tester si le formulaire est sensible aux injections SQL :

---> '

<img width="605" height="322" alt="Image" src="https://github.com/user-attachments/assets/802b3a69-cdf1-4fda-ac02-f06474d180b8" />

Grâce à l'erreur renvoyée par le serveur, on sait qu'il est vulnérable aux injections.

On test des commandes pour découvrir les différentes tables :

---> 1=1

<img width="605" height="308" alt="Image" src="https://github.com/user-attachments/assets/aa8c9f2d-3e32-47a4-a0be-f22ba27522a6" />

Avec les informations que l'on a, on peut executer une commande UNION :

---> -1 UNION SELECT 1, countersign FROM users

Cette commande permet de sélectionner les utilisateurs de la table Countersign :

<img width="605" height="361" alt="Image" src="https://github.com/user-attachments/assets/e8e62893-ada7-404a-a726-77f801a251f0" />

Maintenant, on obtient ue suite de nom ayant un intérêts car ceux-ci ont l'air d'être chiffrés.

En passant l'un d'eux dans un déchiffreur MD5, le numéro 4, on obtient "fortytwo" :

<img width="605" height="218" alt="Image" src="https://github.com/user-attachments/assets/9f567369-9fee-4cc7-89c0-ab5dec87784e" />

Et, en rechiffrant le mot fortytwo en SHA256, on trouve le flag :

<img width="605" height="301" alt="Image" src="https://github.com/user-attachments/assets/ce097fdc-6250-4224-8a6e-66def7ccf849" />

Flag trouvé : 10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5




