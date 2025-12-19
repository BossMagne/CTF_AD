##########################################

ALEXANDRE DENIS

##########################################

CTF

2eme attaque SQL :« search_image_sql_inj_union »

Comme pour le search_users, nous allonrs utiliser les mêmes procédés pour cette attaque.
Nous savons que les formulaires sont vulnérables aux injections SQL.

Il y'a également un formulaire de recherche d'image sur le site.

Nous allons tenter également d'éxécuter des commandes ici.

Toujours à l'aide de la commande UNION :

---> ID: -1 UNION SELECT id, CONCAT(url, 0x20, title, 0x20, comment) FROM list_images

<img width="605" height="310" alt="Image" src="https://github.com/user-attachments/assets/df99985c-afba-4d24-a1c7-d7604521f9e2" />

Cette commande va nous permettre de de récupérer les informations des colonnes id et list_images :

<img width="605" height="308" alt="Image" src="https://github.com/user-attachments/assets/43554368-02fa-434e-871f-7895a831e0d5" />

Sur le renvoi de la commandes, tout en bas, il y'a notre flag, ou plutôt comme pour l'injeciton SQL précédente, une étape de déchiffrage et de chiffrage en plus :

<img width="605" height="191" alt="Image" src="https://github.com/user-attachments/assets/a34fdec2-77ad-42b9-9401-9cc12bc3d631" />

Puis on rechiffre en sha256 :

<img width="1699" height="559" alt="Image" src="https://github.com/user-attachments/assets/a61ef364-6db6-48b2-9507-8de4175b9474" />

Flag trouvé : f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188
