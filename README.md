# AnalyseDeSentimentsSurDesTweets - Projet IA
Classification d'émotions avec DistilBERT & TweetEval 

## Description :
Ce projet consiste à entraîner un modèle de traitement automatique du langage (NLP) pour prédire les émotions dans des tweets.
Il utilise le dataset TweetEval - Emotion, un benchmark standard pour les tâches NLP de classification de sentiments.

Le modèle choisi est DistilBERT, une version légère mais performante de BERT, entraînée ici via la bibliothèque HuggingFace Transformers.

Les labels possibles du dataset sont :
- 0 - anger
- 1 - joy
- 2 - optimism
- 3 - sadness

## Objectifs du projet :
- Prétraiter le dataset TweetEval
- Fine-tuner DistilBERT pour la classification d'émotions
- Évaluer le modèle avec Accuracy et F1-score
- Tester avec des phrases personnalisées
- Comparer l'inférence via Pipeline, PyTorch et TensorFlow
- Analyser les erreurs avec une matrice de confusion
- Interpréter le modèle grâce à la visualisation de l'attention

## Résultats obtenus : 
Avant entraînement :
- Le modèle non entraîné affiche des performances très faibles :
  - Accuracy : 16 %
  -  F1-macro : 13 %
- Ces valeurs montrent que le modèle pré-entraîné n'est pas adapté directement à la tâche.
  
Après entraînement :
- Le modèle fine-tuné obtient des performances nettement meilleures :
  - Accuracy : ~80 %
  -  F1-macro : ~76 %
-  Cela prouve que le fine-tuning sur TweetEval améliore fortement la capacité du modèle à reconnaître les émotions.

## Tests sur phrases personnalisées
Le notebook inclut un module permettant de tester des exemples personnalisés, par exemple :
- "I feel so sad..." -> sadness

Plusieurs méthodes sont proposées :
- Méthode classique Pipeline Transformers
- TensorFlow (non recommandé, car déprécié dans Transformers v5)
- PyTorch (recommandé)

Le projet note que les résultats diffèrent légèrement d'une méthode à l'autre à cause :
- de différences d'implémentation
- de conversions internes entre frameworks
- de versions différentes de Transformers

## Matrice de confusion :
Une matrice de confusion est utilisée afin d'analyser les erreurs de classification par classe.

Elle permet de :

- visualiser où le modèle confond certaines émotions,
- identifier les classes les plus difficiles à prédire,
- comprendre la qualité de généralisation du modèle.
  
Cette analyse met en évidence que certaines émotions proches sur le plan sémantique peuvent être confondues, notamment sadness et optimism dans des phrases ambiguës.

## Analyse de l'attention
Afin de rendre le modèle plus interprétable, une analyse des mécanismes d'attention de DistilBERT est réalisée.

Elle permet de visualiser :

- quels tokens influencent le plus la décision,
- comment le modèle pondère chaque mot,
- si les décisions sont cohérentes d'un point de vue linguistique.

Les visualisations montrent que le modèle se concentre principalement sur des mots porteurs de sens émotionnel (ex : sad, happy, angry), ce qui confirme la pertinence des prédictions.

## Comment exécuter le projet
1. Cloner le dépôt :
git clone https://github.com/longuetbriandavid/AnalyseDeSentimentsSurDesTweets.git
1. Ouvrir le fichier dans google colab:
AnalyseDeSentimentsSurDesTweets.ipynb
1. Modifier le type d'exécution :
Mettre sur GPU T4
1. Exécuter le notebook cellule par cellule?
