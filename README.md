## AnalyseDeSentimentsSurDesTweets
Classification d'émotions avec DistilBERT & TweetEval 

# Description :
Ce projet consiste à entraîner un modèle de traitement automatique du langage (NLP) pour prédire les émotions dans des tweets.
Il utilise le dataset TweetEval - Emotion, un benchmark standard pour les tâches NLP de classification de sentiments.

Le modèle choisi est DistilBERT, une version légère mais performante de BERT, entraînée ici via la bibliothèque HuggingFace Transformers.

Les labels possibles du dataset sont :
- 0 - anger
- 1 - joy
- 2 - optimism
- 3 - sadness

# Objectifs du projet :
- Charger et préparer le dataset TweetEval
- Tokenizer les tweets avec DistilBERT
- Entraîner un modèle de classification avec Trainer
- Évaluer les performances (accuracy, F1-macro)
- Tester le modèle avec des phrases personnalisées
Comparer les résultats avec différentes méthodes :
1. Méthode pipeline directe
1. TensorFlow (déprécié dans Transformers)
1. PyTorch (recommandé) 

# Résultats obtenus : 
1. Avant entraînement :
- Le modèle non entraîné affiche des performances très faibles :
  - Accuracy : 16 %
  -  F1-macro : 13 %
- Ces valeurs montrent que le modèle pré-entraîné n'est pas adapté directement à la tâche.
  
2. Après entraînement :
- Le modèle fine-tuné obtient des performances nettement meilleures :
  - Accuracy : ~80 %
  -  F1-macro : ~76 %
-  Cela prouve que le fine-tuning sur TweetEval améliore fortement la capacité du modèle à reconnaître les émotions.



    

   


