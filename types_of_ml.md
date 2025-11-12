# Types of Machine Learning

Machine Learning is generally divided into **four main types**, based on how models learn from data and the type of feedback they receive:

1. Supervised Learning  
2. Unsupervised Learning  
3. Semi-Supervised Learning  
4. Reinforcement Learning

---

## 1. Supervised Learning

**Definition:**  
Supervised learning is a type of machine learning where the model is trained using **labeled data** — data that already includes the correct output (target value).  
The model learns to map inputs to outputs by minimizing the error between predicted and actual results.

**Goal:**  
Predict outcomes for new, unseen data based on patterns learned from training data.

**Examples of Algorithms:**
- Linear Regression  
- Logistic Regression  
- Decision Trees  
- Random Forest  
- Support Vector Machines (SVM)  
- Neural Networks  

**Applications:**
- Email spam detection (spam / not spam)  
- Credit scoring  
- Sales forecasting  
- Disease diagnosis  

---

## 2. Unsupervised Learning

**Definition:**  
Unsupervised learning deals with **unlabeled data**, meaning there are no predefined outcomes.  
The model tries to find **hidden patterns, structures, or relationships** within the data.

**Goal:**  
Discover natural groupings or representations within the dataset without external guidance.

**Examples of Algorithms:**
- K-Means Clustering  
- Hierarchical Clustering  
- DBSCAN  
- Principal Component Analysis (PCA)  
- Autoencoders  

**Applications:**
- Customer segmentation  
- Anomaly detection  
- Market basket analysis  
- Data compression  

---

## 3. Semi-Supervised Learning

**Definition:**  
Semi-supervised learning is a hybrid approach that uses a **small amount of labeled data** and a **large amount of unlabeled data**.  
It combines the strengths of supervised and unsupervised learning to improve model performance when labeled data is scarce or expensive to obtain.

**Goal:**  
Leverage limited labeled examples to make sense of large unlabeled datasets.

**Examples of Algorithms:**
- Self-training models  
- Label propagation  
- Graph-based algorithms  
- Generative models (e.g., Variational Autoencoders)

**Applications:**
- Web content classification  
- Medical image analysis  
- Speech recognition  
- Text categorization  

---

## 4. Reinforcement Learning

**Definition:**  
Reinforcement learning (RL) is based on **learning by interaction**.  
An agent learns to make a sequence of decisions by interacting with an environment and receiving **rewards or penalties** for its actions.

**Goal:**  
Maximize cumulative reward through trial and error.

**Examples of Algorithms:**
- Q-Learning  
- Deep Q-Networks (DQN)  
- Policy Gradient Methods  
- Actor-Critic Models  

**Applications:**
- Game playing (e.g., AlphaGo, Chess AI)  
- Robotics and autonomous systems  
- Self-driving vehicles  
- Recommendation systems  

---

## Summary Table

| Learning Type | Uses Labeled Data | Learns From | Key Goal | Common Applications |
|----------------|------------------|-------------|----------|--------------------|
| Supervised Learning | Yes | Input–Output pairs | Predict known outcomes | Classification, regression |
| Unsupervised Learning | No | Hidden patterns | Discover structure | Clustering, dimensionality reduction |
| Semi-Supervised Learning | Partially | Labeled + unlabeled data | Improve learning with limited labels | Image or text classification |
| Reinforcement Learning | No (feedback-based) | Rewards & penalties | Learn optimal actions | Robotics, gaming, decision-making |
