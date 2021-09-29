---
title: Réseaux Antagonistes Générateurs (GAN)
description:
hide:
- toc
---

Les Réseaux Antagonistes Générateurs se situent entre l'apprentissage supervisé basé sur la fourniture de données en entrée, dont on connaît la sortie désirée correspondante dans le but d'estimer la relation entrée-sortie au delà des échantillons fournis pour l'apprentissage, et l'apprentissage non-supervisé.

Quand on ne dispose que de données en entrée, pour découvrir certaines structures au sein des données (par exemple le nombre de paramètres qui les caractérisent), il y a beaucoup d'autres paradigmes, par exemple **semi-supervisés** où on mélange des données dont on connaît la sortie désirée et d'autres pas, afin de mixer les deux approches.

Un autre paradigme dit **auto-supervisé** (self-supervised) consiste, à partir de données en entrée, à trouver un mécanisme externe pour générer les sorties correspondantes. Ceci, afin d'économiser l'énorme travail humain de rentrer pour chaque donnée la sortie désirée, par exemple étiqueter des images à la main, pixels par pixels le cas échéant (si on veut trouver où se trouve le chat dans une image). Par exemple, pour apprendre à coloriser automatiquement des images, on peut partir d'images couleur, les réduire à des images en noir et blanc, puis entraîner le mécanisme en lui fournissant les images couleurs désirées, ici connues sans avoir besoin de les reconstruire pour chaque image noir et blanc.

Cela marche aussi pour apprendre la position relative d'éléments dans une image que l'on découpe, ou la cohérence temporelle dans une vidéo. Mais cela ne marche pas pour tout. Cela marche chaque fois qu'on trouve une astuce pour générer automatiquement les entrées et la sortie désirée à partir des données. **C'est en quelque sorte de l'apprentissage non-supervisé qui auto-génère des données pour un paradigme d'apprentissage supervisé**.
