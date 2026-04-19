# Transformers & LLMs (Stanford CME295)

Detailed reading notes from [Stanford CME295 | Autumn 2025 | Lecture 1 - Transformer](https://youtu.be/Ub3GoFaUcds)

---

## 1. Introduction to NLP & Task Taxonomy
The lecture categorizes Natural Language Processing (NLP) into three main functional buckets:

*   **Classification:** Single output from text (e.g., Sentiment analysis, Intent detection).
*   **Multi-classification:** Multiple labels for a single text (e.g., Named Entity Recognition or NER).
*   **Generation:** Text in, variable-length text out (e.g., Machine Translation, Summarization, Chatbots).

### Evaluation Metrics
| Metric | Purpose |
| :--- | :--- |
| **Accuracy/ Precision / Recall / F1** | Used for classification; crucial when data is imbalanced. |
| **BLEU / ROUGE** | Rule-based metrics comparing model output to reference text. |
| **Perplexity** | Measures how "surprised" a model is by its output (lower is better). |

#### Deep Dive: Precision vs. Recall
In classification tasks, accuracy isn't enough—especially when dealing with imbalanced datasets. We use these two metrics to judge the model's reliability:

| Feature | Precision | Recall |
| :--- | :--- | :--- |
| **Key Question** | "How accurate are my positive hits?" | "How many of the actual targets did I find?" |
| **Goal** | **Quality:** Measures how many of the model's positive predictions were correct. | **Quantity:** Measures how many of the actual positive cases were caught. |
| **Formula** | \\( \frac{TP}{TP + FP} \\) | \\( \frac{TP}{TP + FN} \\) |
| **Example** | 7/10 spam flags are correct (70%). | 10/20 actual spam emails were caught (50%). |
| **Penalty** | Punishes **False Positives (FP)** (e.g., flagging work email as spam). | Punishes **False Negatives (FN)** (e.g., missing a real spam email). |

#### The F1 Score: The Balance
The **F1 Score** is the harmonic mean of Precision and Recall. It is used when you need a single number to represent model performance while balancing the trade-offs between precision and recall.

*   **The Trade-off:** Usually, improving Recall makes the model less "picky," which causes Precision to drop.
*   **Peak Performance:** The F1 score only reaches its maximum (1.0) when both Precision and Recall are at their highest. If either is low, the F1 score stays low.

#### Comparison Summary
| Feature | Precision | Recall |
| :--- | :--- | :--- |
| **Alternative Name** | Positive Predictive Value | Sensitivity / True Positive Rate |
| **Key Question** | Is it really what the model says it is? | Did the model find everything? |
| **Real-World Priority** | **High Precision:** Important for Spam Filters (don't lose real mail). | **High Recall:** Important for Medical Screening (don't miss a sick patient). |


---

## 2. Text Representation: From Tokens to Embeddings
Models do not understand text; they understand numbers. This requires two steps:

### Step A: Tokenization
The process of breaking text into units (tokens).
*   **Word-level:** Simple but suffers from "Out of Vocabulary" (OOV) issues.
*   **Character-level:** Robust but computationally slow and lacks semantic meaning per unit.
*   **Subword-level:** The modern standard; balances vocabulary size and captures word roots (e.g., "bear" vs "bears").

### Step B: Embeddings & Word2Vec
*   **One-Hot Encoding:** Inefficient as all words are orthogonal (no similarity).
*   **Word2Vec:** A breakthrough using **Proxy Tasks** (predicting a word based on its context) to learn meaningful vectors. It allows for vector math like `King - Man + Woman = Queen`.

---

## 3. The Evolution Toward Attention
### Recurrent Neural Networks (RNNs) & LSTMs
*   **How they work:** Process tokens sequentially, maintaining a "hidden state" (memory) of the sentence so far.
*   **The Problem:** **Vanishing Gradients**. In long sentences, the model "forgets" earlier words because the gradient diminishes during backpropagation.

### The Attention Mechanism
Instead of a single memory vector, attention creates direct links between what is being predicted and specific parts of the input text, regardless of distance.

---

## 4. The Transformer Architecture
Introduced in the landmark paper *Attention is All You Need* (2017), it replaces recurrence with **Self-Attention**.

### Key Components
*   **Encoder:** Processes the input text to create rich, context-aware embeddings.
*   **Decoder:** Generates output tokens one by one, looking back at the encoder's output and previously generated tokens.
*   **Position Encoding:** Since the model processes everything at once, it needs added signals to know the order of words.

### Query, Key, and Value (Q, K, V)
The mathematical "language" of attention:
*   **Query (Q):** What I am looking for.
*   **Key (K):** What I have to offer.
*   **Value (V):** The information content I provide if matched.

> **Analogy:** Finding a book in a library. The **Query** is your search term, the **Key** is the book title on the spine, and the **Value** is the content inside the book.

### Multi-Head Attention
Running the attention mechanism multiple times in parallel with different learned projections. This allows the model to attend to different types of relationships (e.g., one head for grammar, another for entity relationships) simultaneously.

---

## 5. Summary of the Decoding Process
1.  **Start:** Begin with a special **BOS** (Beginning of Sentence) token.
2.  **Self-Attention:** Look at already generated tokens.
3.  **Cross-Attention:** Look at the Encoder's representation of the source text.
4.  **Softmax:** Predict the probability of the next word in the vocabulary.
5.  **Stop:** End when the **EOS** (End of Sentence) token is generated.

---

## Resources Mentioned
*   **Lecture Slides & Syllabus:** Check the official Stanford Online portal.
*   **VIP Cheat Sheet:** Available on GitHub for a condensed version of these concepts.
