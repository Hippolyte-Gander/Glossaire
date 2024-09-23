# GLOSSAIRE

- [Général](#général)
- [Front-end](#front-end)
- [UX / UI](#ux-ui)
- [Architecture](#architecture)
- [Modélisation / Base de données](#modélisation---base-de-données)
- [Symfony](#symfony)
- [Sécurité](#sécurité)
- [RGPD](#rgpd)
- [SEO](#seo)
- [Gestion de projets / DevOps](#gestion-de-projets---devops)
- [English](#english)

## Général
1.	Quel est l’environnement à installer pour exécuter un script PHP ? Citer 2 exemples de logiciels permettant ce contexte
Il faut un logiciel d'éditeur de code (un éditeur de texte pourrait aussi fonctionner), un serveur web et un interpréteur  PHP(Laragon ou XAMPP font les 2).

2.	Qu’est-ce qu’un algorithme ?
Ensemble d'opérations, généralement successives, permettant d'obtenir un résultat en fonction d'éléments fournis en entrée.

3.	Qu’est-ce qu’une variable ? Par quel symbole est préfixée une variable en PHP ?
C'est une donnée qui peut être par exemple un entier, une chaîne de caractères ou un array / tableau. Elle stocke cette valeur mais peut être modifiée. symbole : $

4.	Qu’est-ce que la portée d’une variable ?
Ce sont les endroits d'où la variable est accessible, plus précisémment l'espace du script dans lequel elle va être accessible. Par exemple une valeur déclarée dans une boucle IF ne sera accessible qu'à l'intérieur de celle-ci.

5.	Qu’est-ce qu’une constante ? Quelle est la différence avec une variable ?
La variable est une valeur qui peut par la suite être modifiée, une constante est une valeur non modifiable une fois déclarée.

6.	Qu’est-ce qu’une superglobale, combien en existent-ils et donner un exemple d’utilisation 
Il en existe 9 : $GLOBALS $_SERVER $_GET $_POST $_FILES $_COOKIE $_SESSION $_REQUEST $_ENV
Ce sont des variables accessibles depuis n'importe où dans le script. Elle peuvent être appelées sans avoir été définies au préalable.
$_GET récupère des valeurs d'un tableau associatif via l'URL.

7.	Quels sont les différents types (primitifs) que l’on peut associer à une variable en PHP ? Les citer et en donner des exemples (ne pas oublier le type d’une variable sans valeur)
Integer : nombre entier (ex: 12)
Float : nombre décimal (ex: 4.2)
String : chaîne de caractères (ex: "Bonjour à tous")
Boolean : booléen ("true" ou "false")
Array : tableau de valeurs (peut aussi être vide) (ex: ["Toyota", "Mercedes", "Citroën"])
Object : instance de classe contenant des propriétés et des méthodes ($voiture = new Voiture("Audi"))
NULL : variable sans valeur ("null")
Ressource : resssources externes (ex: mysqli_connect()).

8.	Existe-t-il plusieurs types de tableaux en PHP, si oui lesquels ?
Les tableaux "basiques" qui contiennent plusieurs valeurs : ['Ford', 'BMW']
Et les tableaux associatifs qui ont une clef associée à une valeur selon le modèle "clef"=>"valeur" : $assArray = ["Audi"=>"Q5", "BMW"=>"Serie 1"].

9.	Quelles sont les différentes structures de contrôles qu’il existe en algorithmie ? Donner un exemple pour chacune d’entre elles
IF / ESLSE IF / ELSE 
$speed = 49;
if ($speed < 50){
    echo "Vous respectez la limitation";
} else {
    echo "Vous ne respectez pas la limitation";
};

SWITCH
$jour = "férié";
switch($jour){
    case "férié":
        echo "On ne travaille pas";
        breal;
    case "non férié":
        echo "On travaille";
        breal;
}

FOR
for ($i=0; $i<10; $i++) [
    echo "On a ajouté 1 à $i";
]

WHILE
while ($i > 10){
    echo "On a enlevé 1 à $i";
    $i--;
}

FOREACH
$array = ["Toyota", "Mercedes", "Citroën"];
foreach($array as $voiture){
    echo "La voiture est une " . $voiture "\n";
}


10.	Quelle est la fonction PHP permettant de demander la longueur d’une chaîne de caractères ?
strlen()

11.	Qu’est-ce qu’une session ? Quelle fonction permet de démarrer une session en PHP ? Donner un exemple d’utilisation en PHP
Une session est accessible grâce à la superglobale $_SESSION. Elle permetde conserver des informations (comme les variables) à travers plusieurs pages web.
session_start() permet de démarrer une session.
?

12.	Qu’est-ce qu’un cookie ? Donner un exemple d’utilisation en PHP
C'est une information stockée sur le navigateur du client. Cela peut être des préférences de site ou des identifiants de session. Un cookie peut par exemple stocker l'id d'un user afin de l'identifier pendant sa navigation sur le site.

13.	Quelle est la différence entre les instructions « require » et « include » en PHP
Dans le cas où le fichier n'est pas trouvé, REQUIRE déclenche une fatal error alors que INCLUDE n'empêche pas le fonctionnement du script.

14.	Comment effectuer une redirection en PHP ?
header("Location: https://www.example.com/nouvelle_page.php");
exit();
A mettre tout en haut de la page !

15.	Définir la partie « front-end » et « back-end » d’une application
Le front est tout le visuel, l'affichage et l'organisation des éléments à l'écran (HTML, CSS et JS par exemple). C'est la partie visible par l'utilisateur.
Le back c'est tout ce qui touche à la gestion des données, requêtes, authentification et échange avec un base de données.

16.	Définir le contrôle de version ? Qu’est-ce que Git ?
C'est un moyen de modifier des fichiers par plusieurs personnes en même temps, à distance, et d'en faire des backups des anciennes versions.
Git est le système de contrôle de version le plus utilisé.

17.	Qu’est-ce qu’un CMS ? Citer au moins 2 exemples
Un CMS (Content Management System)  est une plateforme logicielle accessible à ceux ayant peu de connaissances en programmation. Elle s'occupe du front comme du back.
WordPress, Salesforce Experience Cloud, Joomla, Shopify, Drupal.
NE PAS CONFONDRE AVEC LES FRAMEWORKS CSS (Bootstrap, Tailwind CSS ou Ulkit).


## Front-end
18.	Définir HTML
C'est un langage de balisage qui permet de gérer le contenu d'une page web.

19.	Définir CSS.
C'est un langage de programmation qui gère l'esthétique / le rendu visuel de la page, c'est à dire sa mise en forme et mise en page.

20.	Définir Javascript
C'est un langage permettant d'ajouter de l'interactivité avec l'utilisateur. Il permet également de faire des effet de style et des animations.


21.	Définir JSON. Dans quel contexte ce format est-il utilisé ? 
JavaScript Object Notation, c'est un format de donnée textuel conçu pour l'échange de données.

22.	Peut-on interpréter du Javascript côté serveur ? Si oui, comment ?
Oui grâce à l'environnement Node.js, une plateforme open-source qui permet de d'utiliser un seul langage pour le navigateur et le serveur.

23.	Qu’est-ce qu’un sélecteur CSS ?
C'est ce qui permet de sélectionner un élément ou un groupe d'éléments ou un classe afin de modifier par la suite leur caractéristiques. Par exemple h1 pour tous les gros titres ou .classe pour une classe en particulier et #id pour un élément unique.

24.	Quelle balise HTML permet de créer un lien hypertexte ?
La balise 'anchor' a : <a href="link"></a>. On peut rajouter target="_blank" pour que le lien s'ouvre dans un nouvel onglet.

25.	Qu’est-ce qu’une requête AJAX ?
Asynchronous JavaScript And XML, c'est une technique qui permet à une page web de communiquer avec un serveur en arrière-plan sans avoir besoin de recharger la page entière.
-> mettre à jour des éléments d'une page sans rafraîchir la page.

26.	Quel sélecteur CSS permet de sélectionner tous les éléments d’une classe spécifique ? D’un identifiant spécifique ?
le point . une classe et # pour l'identifiant.

27.	Définir le responsive design
C'est  un affichage qui s'adapte à la taille de l'écran sur lequel il est affiché (mobile, tablette, pc ou autre). Responsive c'est un affichage progressif.

28.	Qu’est-ce que le templating ?
Template en agnlais signifie modèle ou schéma. C'est une base qui peut se réutiliser ou se modifier (principalement pour des pages HTML).

29.	Qu’est-ce qu’une fonction anonyme en Javascript ?
C'est une fonction qui contrairement aux autres n'est pas définie par un nom et écrite comme ça: public function() { contenu de la fonction }
En général elles sont utilisées lorsqu'une fonction n'est utilisée qu'une seule fois.

30.	Quelle méthode JavaScript est utilisée pour ajouter un élément à la fin d'un tableau ?
Array.prototype.push()

31.	Qu’est-ce qu’un « media query » ?
En CSS c'est un moyen de définir un affichage particulier lié à la taille de l'écran utilisé.

32.	Qu’est-ce qu’un pseudo élément en CSS ?
C'est un sélecteur CSS qui ne cible qu'une partie d'un élément.
Il en existe 4 (reconnus W3C):
    ::first-letter
    ::first-line
    ::before
    ::after

33.	Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent
C'est un framework CSS gratuit et open source. Il permet d'avoir une mise en forme par défaut et permet de facilement modifier l'apparence d'une page. C'est plus rapide que de faire tout le CSS à la main mais c'est moins personnalisable. On peut utiliser Bootstrap et ajouté de CSS personnalisé par dessus mais cela réduira les performances du site.
Équivalents :
Tailwind CSS
Bulma
Ulkit
Kendo UI
Material UI

34.	Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes
POST : transmission de données
GET : récupération d'informations via l'URL

## UX UI
35.	Quelle est la différence entre UX Design et UI Design ?
UX Design => objectif : faciliter et rendre agréable l'expérience utilisateur -> facilité d'utilisation
UI Design => objectif : le site soit lisible,texte comme fonctionnalités (un menu par défaut c'est en haut, pas en bas) + une charte graphique attirante

36.	Qu’est-ce qu’un wireframe ? 
Littéralement "maquette fonctionnelle", c'est à dire une maquette sans style particulier, comprenant juste les éléments principaux de la page.

37.	Qu’est-ce qu’un prototype ?
C'est une simulation du produit final, elle permet de visualiser l'interaction de l'utilisateur avec la page.

38.	Qu’est-ce que la hiérarchie visuelle en UI Design ?
C'est respecter l'ordre d'importance des éléments selon leur représentation (taille, couleur, position). ex: un texte en grand dans un cadre rouge  = importance numéro 1 sur la page.

39.	Qu’est-ce que l’accessibilité en UX Design ?
C'est l'accès au numérique pour les personnes en situation de handicap.
ex :
- description d'une image pour les utilisateurs aveugles dont la page est lue par le navigateur.
- ne pas mélanger des couleurs qui apparaissent identiques pour certains type de daltonismes.

40.	Qu’est-ce qu’une grille de mise en page ?
C'est un cadrillage virtuel qui recouvre une page, permettant de séparer les éléments en colonnes ou de les aligner.

41.	Qu’est-ce que la notion d’affordance en UX Design ?
Ce sont les "call to action", de actions / boutons qui incitent le visiteur à cliquer sur un objet du site.

42.	Qu’est-ce qu’un « mobile first design » ?
C'est le fait de réaliser les maquettes en créant d'abord la version mobile d'un projet qui ensuite sera adaptée en version desktop. C'est dû au fait que 75% du traffic internet se fait maintenant sur smartphone.


## Programmation orientée objet (POO)
43.	Donner une définition de la programmation orientée objet 
C'est lorsque l'on manipule des objets (possédant des caractéristiques) via des classes.

44.	Qu’est-ce qu’une classe ? Comment la déclare-t-on ?
On la déclare avec "class NomClasse {}". C'est une manière de définir les caractéristiques d'un objet -> des attributs et des méthodes.

45.	Qu’est-ce qu’un objet ?
C'est une instance appartenant à une classe.

47.	Définir la notion de propriété / attribut / méthode
propriété : nature d'une valeur (srting / int /float / DateTime etc)
attribut : ce sont les valeurs qui composent une classe (ex nom, date de naissance)
méthode : succession d'opération effectuée sur une ou plusieurs variables, doit toujours retourner  quelque chose.

48.	Qu’est-ce que la visibilité d’une propriété ou d’une méthode ? Citer les différents types de visibilité
C'est son accessibilité.
Private = non accessible en dehors de la classe
Protected = accessible uniquement par la / les classe(s) qui hérite de la caractéristique
Public = accessible de n'importe où par n'importe qui

49.	Quelle est la méthode spécifique utilisée pour créer un nouvel objet à partir d’une classe ?
__construct()

50.	Qu’est-ce que l’encapsulation ?
C'est le regroupement de données avec un ensemble de routines qui en permettent la lecture et la manipulation -> cela sert à empêcher que certaines propriétés d'une classe ne soit accessible en dehors de celle-ci.

51.	Que signifie « étendre une classe » ? Quelle est le concept clé mis en œuvre ? Donner un exemple
C'est le concept d'héritage. une classe qui est étendue d'une autre possédera les mêmes propriétés ainsi que l'accès aux méthode de celle-ci.
Exemple:
On a une classe voiture qui a comme attributs "marque" "modèle" et "année".
On crée une classe Voiture électrique extends Voiture, qui a comme attributs "autonomie" et "puissance". Un objet voiture éléctrique pourra donc avoir, sans être déclarés dans la classe, une marque un modèle et une année et aurra accès aux méthodes de la classe Voiture (ex: getModele()).

52.	Définir l’opérateur de résolution de portée
C'est un moyen d'accéder aux éléments d'une classe (ou de l'une de ses classes parentes). il s'agit du double points ::
Ex:
$form = $this->createForm(CommentaireType::class, $commentaire);

53.	Définir une méthode / propriété statique
C'est un méthode accessible sans avoir à instancier la classe. Elle est associée à la classe elle-même et non aux objets de la classe

-> pas très clair pour moi

54.	Définir le polymorphisme en POO
Fonction polymorphe = fonction qui peut appeler plusieurs types d'objets.
Ex:
Une fonction qui peut afficher plusieurs objets de classe différente ? (si j'ai bien compris)

55.	Définir une méthode / classe abstraite ?


56.	Définir le chaînage de méthodes


57.	Qu’est-ce que la méthode __toString() ? Existe-t-il d’autres méthodes « magiques »


58.	Qu’est-ce qu’un « autoload » ?


59.	Comment appelle-t-on en français les « getters » et les « setters » ?


60.	Qu’est-ce que la sérialisation en PHP ? 


## Architecture 
60.	Qu’est-ce que l’architecture client / serveur ? Grâce à quel type de requête peut-on interroger le serveur. Définir l’acronyme de ce type de requête. Si on ajoute un « S » à cet acronyme, expliquer la différence

61.	Donner la définition d’un design pattern. Citer au moins 3 exemples de design pattern

62.	Qu’est-ce que l’architecture MVC ?

63.	Quel est le rôle de chaque couche du design pattern MVC : Model, View, Controller ?

64.	Quels sont les avantages de l’architecture MVC ?

65.	Existe-t-il des variantes à l’architecture MVC ?

66.	Qu’est-ce qu’une API ? Définir l’architecture REST

## Modélisation - Base de données
67.	Qu’est-ce que la modélisation de données ? Définir la méthode Merise
68.	Quelles sont les 3 étapes principales de la méthode Merise ? 
a.	Analyse, conception et réalisation
b.	Planification, exécution et contrôle
c.	Création, modification et suppression
69.	Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?
70.	Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?
71.	Donner la définition des mots suivants :
a.	Entité
b.	Relation
c.	Cardinalité
d.	Clé primaire / clé étrangère
72.	Que devient une relation de type « Many To Many » dans le modèle logique de données ?
73.	Qu’est-ce qu’une base de données ?
74.	Définir les notions suivantes : 
a.	SQL
b.	MySQL
c.	SGBD (donner 2 exemples de SGBD)
75.	Dans une base de données, les données sont stockées dans des ___. Celles-ci sont constituées de lignes appelées ___ et de colonnes appelées ___
76.	Quelle est la différence entre une base de données relationnelle et non relationnelle ?
77.	Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?
78.	A quoi sert une vue dans une base de données ?
79.	Qu’est-ce que l’intégrité référentielle dans une base de données ?
80.	Quelles sont les fonctions d’agrégation en SQL ?
81.	Qu’est-ce qu’un CRUD dans le contexte d’une base de données ?
82.	Quelles sont les clauses qui permettent de :
a.	Insérer un nouvel enregistrement dans une table
b.	Modifier un enregistrement dans une table
c.	Supprimer un enregistrement dans une table
d.	Supprimer la base de données
e.	Filtrer les résultats d’une requête SQL
f.	Trier les résultats d’une requête SELECT
g.	Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique
h.	Concaténer 2 chaînes de caractères 
83.	Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?

## Symfony
84.	Qu’est-ce que Symfony ?
85.	Sur quel langage de programmation et design pattern repose Symfony ? 
86.	Quelle est la dernière version en date de Symfony ?
87.	Qu’est-ce qu’un bundle ? 
88.	Quel est le moteur de template utilisé par défaut dans Symfony ?
89.	Qu’est-ce qu’un ORM ? Quel est son utilité et comment s’appelle-t-il au sein de Symfony ?
90.	Qu’est-ce que l’injection de dépendances ? Quel est l’outil utilisé dans ce contexte et quel fichier contient l’intégralité des dépendances du projet ?
91.	Que permet le bundle Maker au sein de Symfony ? 
92.	Quel est le langage de requêtage exploité au sein d’un projet Symfony ?
93.	Quel est le composant qui garantit l’authentification et l’autorisation des utilisateurs ?

## Sécurité
94.	Qu’est-ce que l’injection SQL ? Comment s’en prémunir ?
95.	Qu’est-ce que la faille XSS ? Comment s’en prémunir ?
96.	Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?
97.	Définir l’attaque par force brute et l’attaque par dictionnaire
98.	Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement
99.	A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?
100.	Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage
101.	Qu’est-ce qu’une politique de mots de passe forts ?
102.	Qu’est-ce que l’hameçonnage ?
103.	Définir la « validation des entrées »

## RGPD
104.	Qu’est-ce que le RGPD ?
105.	Quel est son objectif principal ?
106.	Quelle est la date d’entrée en vigueur du RGPD ?
107.	Quelles sont les sanctions possibles en cas de non-respect du RGPD ?
108.	En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?
109.	Quel est le consentement valide selon le RPGD ?
110.	Qu’est-ce qu’une politique de confidentialité ?
111.	Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?
112.	Quels sont les droits des utilisateurs selon le RGPD ?
113.	Qu’est-ce que le principe de minimisation des données selon le RGPD ?

## SEO
114.	Qu’est-ce que le SEO ? 
115.	Quel est l’objectif principal du SEO ?
116.	Existe-t-il plusieurs types de référencement ? Lesquels ?
117.	Qu’est-ce que la densité de mots-clés en SEO ?
118.	Qu’est-ce qu’une balise « alt » ?
119.	Qu’est-ce que la balise « meta description » ?
120.	Qu’est-ce que le « nofollow » en SEO ?
121.	Quelle est l'importance du contenu de qualité pour le référencement d'un site web ?
122.	Pourquoi est-il important d'utiliser des balises de titre (h1, h2, h3, etc.) de manière structurée ?
123.	Quelle est la recommandation pour les URL d'un site web bien référencé ?
124.	Qu'est-ce que le maillage interne et pourquoi est-il important pour le référencement ?
125.	Qu'est-ce que l'optimisation des images pour le référencement ?
126.	Qu'est-ce qu'un plan de site (sitemap) et pourquoi est-il important pour le référencement ?

## Gestion de projets - DevOps
127.	Qu’est-ce que la gestion de projet ?	
128.	Qu’est-ce qu’une méthode Agile de gestion de projet ? 
129.	Expliquer la méthode MoSCoW en quelques lignes et citer ses avantages
130.	A quoi sert la méthodologie MVP ? Citer les caractéristiques clés
131.	Qu’est-ce que la planification itérative ?
132.	Citer 3 méthodes Agiles dans le cadre d’un projet informatique
133.	Qu’est-ce qu’une réunion de revue de projet ?
134.	Qu’est-ce qu’un livrable dans un projet ? 
135.	Quels sont les 3 piliers SCRUM ? Définir chacun d’entre eux
136.	Qu’est-ce que le DevOps et quel est son objectif principal ?
137.	Qu’est-ce que l’intégration continue ? 
138.	Qu’est-ce que Docker ? Et en quoi est-il utile dans le cadre du DevOps ?
139.	Qu’est-ce qu’un test unitaire ? 
140.	Quelle est l'unité de code testée lors d'un test unitaire ?
141.	Quelles sont les caractéristiques d'un bon test unitaire ?
142.	Qu'est-ce qu'une assertion dans un test unitaire ?
 
## English
1)	What does JavaScript enable you to do on a website ? A
a.	Add interactive behavior and dynamic content
b.	Define the layout and design of web pages
c.	Handle server-side operations

2)	Which programming language is primarily used for server-side web development ? A
a.	PHP
b.	JavaScript
c.	HTML

3)	What is the purpose of a web browser ? A
a.	To render and display web pages
b.	To execute serve-side code
c.	To manage databases

4)	What is the difference between GET and POST methods in HTTP ? A
a.	GET retrieves data from a server, while POST submits data to a server
b.	GET submits data to a server, while POST retrieves data from a server
c.	GET and POST methods are interchangeable

5)	What is the purpose of version control systems (e.g., Git) in web development ? A
a.	To track changes and manage collaborative development
b.	To optimize website loading speed
c.	To handle server-side scripting

6)	What is the purpose of a framework in web development ? 
a.	To provide a structured environment for building web applications
b.	To handle network protocols and data transfer
c.	To create visual designs and layouts for websites

7)	What does NoSQL stand for ?
a.	Not Only SQL
b.	Non-Structured Query Language
c.	New Object-Oriented Language
8)	Which of the following is a characteristic of NoSQL databases ?

a.	Strict schema enforcement
b.	Support for complex transactions
c.	Scalability and flexible data models
