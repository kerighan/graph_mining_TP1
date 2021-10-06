Exercice 2
==========

Networkx contient de nombreuses fonctions permettant de lire ou écrire un graphe sur le disque. Un format classique pour un graphe et le format GXF, notamment supporté par Gephi.

Dans cette série d'exercices, on s'intéresse au réseau du métro parisien. 

Exercices :
-----------

1. Chargez le graphe situé ici : `datasets/subway.gexf`.
2. Calculez n, m, \<k\>, \<L\> (approximé). Comparez \<L\> à celui d'un graphe Gnm.
3. A l'aide de la fonction `nx.betweenness_centrality`, calculez la centralité d'intermédiarité du graphe et affichez les 10 stations les plus centrales
4. A l'aide de la fonction `nx.closeness_centrality`, calculez la centralité de proximité du graphe et affichez les 10 stations les plus centrales. Comparez ces deux résultats
5. Identifiez les deux stations les plus éloignées
6. En simulant la suppression des stations parmi les 20 plus centrales, identifiez les 5 stations qui rallongeraient le plus \<L\> si elles étaient fermées.
7. En simulant la création d'edges entre les stations parmi les 20 plus centrales, identifiez la ligne qui, si ajoutée, raccourcirait le plus \<L\>