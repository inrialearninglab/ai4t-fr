---
title: Jouez avec les neurones de la machine
description:
---

Le logiciel en ligne **[TensorFlow](https://www.tensorflow.org/overview/)**  permet de constituer des réseaux de neurones artificiels et de tester leurs réponses pour différents types de problèmes et ce, sur différents types de données (data). Dans le type de problème «Classification », l'objectif est de séparer les points de couleur bleue et les points de couleur orange. Une application de ce type de problème est, par exemple, un algorithme de classement de photographies. Dans l'exemple ci-dessous, il y a une entrée (feature) qui sépare horizontalement les points et une autre qui sépare verticalement En combinant ces deux entrées, on obtient une séparation oblique. Le résultat obtenu (output) est bien adapté au type de données choisi (data).


![Vue du playground de Tensor flow](../Images/tensor-flow.png)


###TensorFlow : Quelques explications avant d'essayer la simulation d'un réseau de neurones

_Source: translation from [Pixees French web site](https://pixees.fr/jouez-avec-les-neurones-de-la-machine/)_

**Qu'est-ce qu'un réseau neuronal et comment fonctionne-t-il?**
Un réseau neuronal est un mécanisme générique composé de petites unités (pseudo-neurones) connectées entre elles. Chaque unité effectue une opération très simple : elle prend des valeurs en entrée, les combine très simplement (une simple moyenne avec des coefficients) et applique une transformation sur le résultat (par exemple, ne garder que les valeurs positives).

Les coefficients utilisés pour pondérer la moyenne sont les paramètres de cet algorithme. C'est la combinaison d'un très, très grand nombre de ces unités qui permet d'effectuer des opérations très complexes. Un réseau de tels "neurones" est obtenu en accumulant plusieurs couches de ces unités. L'entrée est constituée des données que l'on veut traiter. Elles sont transformées à travers toutes les couches et la dernière couche donne en sortie une prédiction sur ces données, par exemple pour détecter s'il y a un visage dans une image. Le réseau de neurones est donc une fonction paramétrée avec de nombreux coefficients (appelés "poids") et c'est le choix de ces poids qui définit le traitement effectué.

**Où sont les neurones dans TensorFlow ?**
Sur l'interface web de TensorFlow, on peut facilement créer un réseau d'une dizaine de neurones, chacun ayant entre 3 et 10 paramètres. La sortie calculée dépend donc de centaines de paramètres en plus des deux coordonnées (x,y) du point d'entrée. Sur l'interface, chaque carré représente un neurone et la couleur du pixel de coordonnées (x,y) dans le carré représente la sortie du neurone lorsqu'on met (x,y) en entrée du réseau. S'il n'y a qu'un seul neurone en sortie, il est représenté par un carré plus grand à droite du réseau. Les paramètres du réseau sont initialisés avec des valeurs aléatoires.

**Mais comment apprendre ces poids ?**
L'apprentissage supervisé consiste à fournir des exemples de données avec la solution à trouver afin d'entraîner le réseau à ajuster ces poids en fonction des besoins. Dans l'exemple de la figure ci-dessus, il s'agit d'une série de points dans un carré, chacun avec une couleur attendue (bleu ou orange), dans le but de prédire la couleur du point à un endroit donné.  Un algorithme classique d'ajustement progressif des poids est utilisé pour trouver les paramètres en question.
Le bouton "play" en haut à gauche de l'interface permet de lancer cet algorithme, et l'on voit alors la sortie du réseau de neurones évoluer au cours du processus "d'apprentissage" : la couleur de fond du neurone de sortie tend à prendre la couleur des points d'entraînement qui sont dessinés sur lui. Une autre partie de l'ensemble de données est ensuite utilisée pour tester la qualité de la fonction résultante du réseau. Une courbe en haut à droite montre le taux d'erreur des données utilisées pour l'apprentissage (pour vérifier que les poids ont été correctement ajustés) et le taux d'erreur des autres données de test (pour vérifier que ce qui a été appris se généralise bien à de nouvelles données). Les boutons sur le côté gauche permettent d'ajuster la distribution des données entre l'ensemble d'apprentissage et l'ensemble de test et aussi d'ajouter des erreurs aux données (données bruitées) pour voir si le mécanisme est robuste à ces erreurs.

En pratique, on arrive à trouver des paramètres satisfaisants, mais il n'y a pas vraiment de cadre théorique pour formaliser tout cela, c'est une question d'expérimentation : choisir le bon nombre de neurones, le bon nombre de couches de neurones, quels calculs préliminaires ajouter en entrée (par exemple multiplier les entrées pour augmenter les degrés de liberté du calcul).
Ce type de techniques peut donner des résultats impressionnants dans la pratique, comme dans la reconnaissance de la voix ou des objets dans une image.

Cependant, comprendre pourquoi (et comment) de si bons résultats sont obtenus reste une question scientifique assez ouverte.

### Essayez TensorFlow

_Cliquez sur l'image ci-dessous pour accéder à l'application TensorFlow dans une nouvelle fenêtre_

[![Vue du playground de TensorFlow](../Images/tensor-flow.png)](https://playground.tensorflow.org/#activation=tanh&amp;batchSize=8&amp;dataset=circle&amp;regDataset=reg-plane&amp;learningRate=0.03&amp;regularizationRate=0&amp;noise=10&amp;networkShape=5,2&amp;seed=0.02708&amp;showTestData=false&amp;discretize=false&amp;percTrainData=50&amp;x=true&amp;y=true&amp;xTimesY=false&amp;xSquared=false&amp;ySquared=false&amp;cosX=false&amp;sinX=false&amp;cosY=false&amp;sinY=false&amp;collectStats=false&amp;problem=classification&amp;initZero=false&amp;hideText=false;target=blank){:target="_blank" }
