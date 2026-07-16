# NLP-message-user-predictor
Predicting Telegram message authorship using fine-tuned RuBERT (Two-Stage Training).
An NLP project aimed at determining the author of a Telegram message using RuBERT. 
The model accepts text messages without context and predicts which user sent them.

To get the best results, I implemented a Two-Stage Training strategy: 
first training only the classification head to stabilize parameters, followed by full model fine-tuning. 
The repository also includes a simulation script to test performance on different subsets of users (e.g., 2 vs 3 users).
