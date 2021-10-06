Exercice 2
==========

Si Networkx permet de lire de nombreux formats de graphes, son inconvénient est qu'il charge l'intégralité d'un graphe en RAM. Si vous tentez d'ouvrir un graphe à plusieurs millions d'edges, deux risques s'ouvrent à vous :
- un temps de chargement très long
- le remplissage total de votre RAM disponible, entraînant dans certains cas un shutdown

Les graphes de plus de 100k edges sont généralement sauvegardés dans des bases de données server comme Neo4j ou OrientDB. Cependant, ces bases de données requièrent un serveur dédié et tournant en permanence, et peuvent s'avérer inutilement complexe pour sauvegarder et étudier des graphes statiques ou parfaire des algorithmes.

Installez nodlite si vous ne l'avez pas fait :
```
pip install nodlite
```

Cette librairie (disclaimer : créée par moi pour l'occasion il y a une semaine https://github.com/kerighan/nodlite) est une librairie rudimentaire construite sur SQLite permettant de manipuler des graphes (orientés) sans les charger en RAM, en payant le prix d'une vitesse d'exécution amoindrie.

Dans cet exercice, on s'intéresse à un échantillon du graphe Netflix (issu du Netflix Prize) : il s'agit d'un graphe biparti liant un utilisateur aux films qu'il a notés 5 étoiles. Dans Nodlite, tout graphe est orienté, et l'orientation est user->movie.

Téléchargez le graphe : https://we.tl/t-dzMPlbanhZ

Pour ouvrir le graphe netflix :
```python
from nodlite import Graph
G = Graph("datasets/netflix.db")
```

1. En utilisant la méthode `G.neighbors`, affichez la liste des films que l'utilisateur `2521079` a aimés
2. En utilisant la méthode `G.predecessors`, affichez la liste des utilisateurs qui ont aimé le film `The Matrix`.
3. Créez une fonction personalized_pagerank qui, pour un graphe, une liste de films et un nombre de steps (=100 par défaut) donnés affichent une recommandation de films (excluant les films fournis)
4. Quels films sont recommandés pour les queries suivantes :
```python
QUERY_NODES = [
    "Star Wars: Episode IV: A New Hope",
    "Star Wars: Episode II: Attack of the Clones",
    "Lord of the Rings: The Two Towers",
    "Lord of the Rings: The Fellowship of the Ring",
    "The Matrix"
]

QUERY_NODES = [
    'Dangerous Liaisons',
    'Sex and the City: Season 1',
    'Bridget Jones: The Edge of Reason'
]
```
5. Quelles idées avez-vous pour améliorer ces résultats ?
