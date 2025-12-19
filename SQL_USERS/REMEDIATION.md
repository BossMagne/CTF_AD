Pour se prémunir des injections SQL dans un formulaire de recherche, il est essentiel de ne jamais inclure directement les entrées de l’utilisateur dans les requêtes SQL. 
Il faut utiliser des requêtes préparées (prepared statements) ou des ORM qui gèrent automatiquement l’échappement des caractères dangereux.
Il est également recommandé de valider et filtrer les données côté serveur, en limitant par exemple la longueur et le type de caractères autorisés, et d’éviter d’afficher directement les messages d’erreur de la base de données à l’utilisateur. 
