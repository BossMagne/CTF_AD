Afin de corriger cette vulnérabilité XSS, il est indispensable de mettre en place une validation stricte des données saisies par l’utilisateur avant leur utilisation dans le code HTML.
Les paramètres dynamiques, notamment ceux intégrés dans des attributs sensibles comme src, doivent être contrôlés à l’aide d’une liste blanche limitant les schémas autorisés à des protocoles sûrs tels que http et https.
Par ailleurs, l’échappement systématique des sorties HTML permet de prévenir toute injection de code malveillant.
Enfin, l’application d’une Content Security Policy (CSP) restrictive constitue une couche de protection supplémentaire en bloquant l’exécution de contenus non autorisés, réduisant ainsi considérablement le risque d’exploitation.
