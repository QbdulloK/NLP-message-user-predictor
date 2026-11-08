# NLP-message-user-predictor

Predicting **Telegram message authorship** using a fine-tuned **RuBERT** model with **two-stage training**.

This is an **NLP** project where the model gets **only the text of a message (no context)** and tries to **guess** which of my **three** friends wrote it.

To get better results, I used a **two-stage training** approach: first I trained **only the classification head** to stabilize the parameters, and after that I **fine-tuned the whole model**. The code also includes a script to test the model on different subsets of users (for example, 2 vs 3 users).

**Dataset size:** around 2,500 messages in total (roughly 950 for User 1 and 770 for the other two).

**Performance:**
The model reached an **accuracy** of **92.57% ± 3.41%** with **3 users**, which is **way higher** than **random chance (33.33%)**.

It can also tell users apart individually:
- **User 1 vs User 2:** 93.54% ± 2.9%
- **User 1 vs User 3:** 95.16% ± 1.81%
- **User 2 vs User 3:** 97.54% ± 1.16%

So the model clearly learned the different **"styles"** of each person and can **confidently** tell them apart. The easiest pair to distinguish is User 2 vs User 3, and the hardest is User 1 vs User 2 (User 1 was generally the most difficult to separate from the others).

I also used a sliding window to generate longer, more informative messages from short ones, and added about 30% augmented messages to the training data. The best dropout rate turned out to be around 0.08.
