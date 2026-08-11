# NLP-message-user-predictor
Predicting **Telegram message authorship** using **fine-tuned RuBERT (Two-Stage Training)**.
An **NLP project** aimed at determining the author of a Telegram message using RuBERT. 
The model accepts text messages **without context** and **predicts which user sent them**.

To get the best results, I implemented a **Two-Stage Training** strategy: 
first training only the classification head to stabilize parameters, followed by full model fine-tuning. 
The repository also includes a simulation script to test performance on different subsets of users (for instance, 2 vs 3 users).

**Dataset Size:** Around **700** messages per person

**Performance:**
The **model** reached an **accuracy** of **82%** with **3 USERS**(significantly higher than **random chance**).

In addition, the **model** can **differentiate** individually
**USER 1 and USER 2** with **95% accuracy**, 
**USER 1 and USER 3** with **87% accuracy**, 
and **USER 2 and USER 3** with **83% accuracy**.

This shows that the **model** managed to learn different **"styles"** of every person,
and it can **confidently** tell the users apart.
