Exercice 1
==========

Assurez-vous d'avoir bien installé les librairies suivantes :
```
pip install networkx
pip install numpy
pip install scipy
```

Networkx est une librairie Python permettant la manipulation de graphes directement en RAM. Au-delà des différents algorithmes (centralité, communauté, etc.), elle permet également de construire des graphes synthétiques, de charger des graphes sauvegardés sur le disque ou d'invoquer des graphes classiques comme le Karate Club.

Lien vers la doc :
https://networkx.org/documentation/stable/index.html

Dans cette série d'exercices, nous allons calculer l'ensemble des propriétés classiques du Karate Club : n, m, \<k\>, coefficient de clustering moyen, <L>, et le pagerank.

Exercices :
-----------

1. Dans un fichier `1_karate.py` que vous allez créer, aidez-vous de Google et de la documentation Networkx pour charger le graphe Zachary's Karate Club. 
2. Affichez le nombre de noeuds et le nombre d'edges. En déduire le degré moyen. A l'aide de la méthode `G.degree`, calculez le degré maximal du graphe. Puis affichez la liste des noeuds.
3. A l'aide de `nx.draw_networkx`, affichez une visualisation du graphe.
4. Affichez un graphique de la distribution des degrés
5. Créez une fonction `get_clustering_coefficient` qui pour un graphe et un noeud donnés calcule le coefficient de clustering local, sans bien-sûr utiliser la fonction native : utilisez `G.neighbors` et `nx.subgraph`. Comparez vos résultats avec la fonction native de networkx `nx.clustering`.
6. Construisez à partir de la question 5 une fonction calculant le coefficient de clustering moyen d'un graphe, et appliquez-la au Karate Club. Comparez vos résultats avec la fonction `nx.average_clustering`.
7. Comparez la valeur trouvée au coefficient de clustering moyen d'un graphe Gnm. Que remarquez-vous ?
8. Implémentez une fonction `dfs` qui effectue un depth-first search dans un graphe, et affiche les noeuds au fil de leur visite
9. Implémentez une fonction `bfs` qui effectue un breadth-first search dans un graphe, et affiche les noeuds au fil de leur visite
10. Implémentez une fonction `shortest_path_length` qui calcule la longueur du plus court chemin entre deux noeuds
11. Créez une fonction qui calcule une approximation de la longueur moyenne en sélectionnant aléatoirement 20 paires de noeuds distincts et en utilisant la fonction `shortest_path_length`
12. A l'aide de la fonction `nx.adjacency_matrix`, `normalize` de sklearn et de numpy, implémentez une fonction `pagerank_no_teleport` qui calcule le pagerank (sans téléport) d'un graphe par la méthode de la puissance itérée. Utilisez un epsilon de 1e-5 ou 1e-6. Affichez la valeur du pagerank pour chaque noeud. Affichez l'index des deux noeuds dont le pagerank est maximal.
13. Créez une fonction `pagerank` calculant le pagerank avec téléport à votre fonction (choisissez `beta=0.85` par exemple). Comment ont évolué les valeurs du pagerank après ajout du téléport ?
14. Comparez vos résultats avec la fonction `nx.pagerank` de networkx.