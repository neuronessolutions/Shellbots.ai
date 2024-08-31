# Introduction - Module de détection de mélanomes "DermaBots"
> Version 2024.08.31.1, Auteur : Dominique Delaire, Neurones Solutions Inc.

Cet article **est le premier article d'une série de 5 articles au total et qui constitue la documentation de notre Module de détection de mélanomes nommé "DermaBots" pour démontrer les possibilités des outils IA intégrés à notre OS et framework Shellbots pour créer des services d'IA innovants pour la recherche dans différents domaines et les entreprises.**

## Introduction
Dans un monde où les technologies de l'intelligence artificielle évoluent à une vitesse fulgurante, leur application dans le domaine médical devient de plus en plus cruciale. Parmi les nombreux défis que les professionnels de la santé doivent relever, la détection précoce du mélanome, une forme agressive de cancer de la peau, est particulièrement primordiale. C'est dans cette optique que cet article propose une exploration approfondie d'un système de machine learning capable de différencier les grains de beauté bénins des mélanomes potentiels à partir d'images dermatologiques.

Ce projet ambitieux se décompose en quatre parties. Nous commencerons par une introduction à l'utilisation de Shellbots, notre environnement puissant pour le développement de modèles de machine learning et d'IA générative intégrant les moteurs principaux du marché (Pytorch, Google Tensor Flow, Dataiku, etc.). 

Nous montrerons comment intégrer efficacement Dataiku pour la préparation et l'analyse des données d'image, une étape cruciale pour garantir la précision des prédictions. Ensuite, nous plongerons dans l'utilisation de Pytorch, une bibliothèque de deep learning, pour entraîner un modèle capable d'identifier les caractéristiques distinctives d'un mélanome. Enfin, nous démontrerons comment ce modèle peut être intégré dans Shellbots pour offrir un outil précieux aux médecins, dermatologues et patients.

Ce système ne vise pas seulement à automatiser la détection, mais également à fournir un soutien décisionnel aux professionnels de santé, augmentant ainsi les chances de détection précoce et améliorant les résultats cliniques. À travers cet article, nous allons découvrir comment les technologies de l'IA peuvent transformer le domaine médical, offrant des solutions innovantes et accessibles pour lutter contre l'une des menaces les plus graves pour la santé humaine.

## Création d'un contexte dans Shellbots pour accueillir les données et images d'entraînement avec Dataiku

Dans la console du système d'exploitation Shellbots, nous **créons un contexte** avec la commande **"createcontext"**   

Un **contexte** est une **sorte de projet** Shellbots où on entrepose et **gère différentes choses** : nos **données, nos modèles, nos services** pour notre base de **machine learning et/ou d'IA générative**.   

Puis pour **changer de contexte et travailler sur celui-ci** dans Shellbots, il suffit d'utiliser la **commande "usecontext"** et de choisir son contexte spécifique.

![Dermabots1](https://github.com/user-attachments/assets/d6b27b9e-b621-4591-a268-e28d532b9c6a)

## Données de référence représentant des grains de beauté bénins ou malins

Nous utiliserons ici des données de différentes sources :
-- ISIC (International Skin Imaging Collaboration) : qui contient des milliers d'images de lésions cutanées y compris des mélanomes. Ces images sont annotées par des experts, ce qui en fait une ressource idéale pour l'entraînement de modèles d'apprentissage automatique.
-- PH2 Database : Une autre base de données contenant des images de mélanomes et d'autres types de lésions cutanées
-- D'autres sources anonymes de sources médicales
