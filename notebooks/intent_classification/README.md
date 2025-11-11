## 🧠 Model Description  

This project uses **DistilBERT**, a smaller and faster version of the original BERT model developed by Hugging Face. It’s built using a technique called *knowledge distillation*, where a large, complex model (the “teacher”) transfers its knowledge to a smaller one (the “student”).  

DistilBERT manages to keep about **97% of BERT’s accuracy** while being **40% smaller** and **60% faster**, which makes it perfect for real-time NLP tasks like intent detection and chatbot understanding.  

---

### ⚙️ How the model works  
DistilBERT is made up of six transformer layers (half of BERT’s twelve) that learn to understand the context and meaning of words in a sentence.  
When you pass in text like:  
> “Book me a flight to Paris tomorrow,”  

the model breaks it into small pieces (tokens), understands how the words relate to each other, and produces a numerical representation of the sentence (embeddings).  

A simple classifier layer is then placed on top to predict the **intent** behind the text — for example, `book_flight`.  

---

### 💡 Why DistilBERT  
I chose DistilBERT because it strikes the right balance between **speed, size, and performance**. It’s light enough to train on a single GPU and fast enough for production use, yet still understands natural language very well.  

It’s especially suitable for intent classification, where the inputs are short and precise, and real-time predictions matter more than tiny accuracy improvements from much larger models.  

---

### 🧩 Fine-tuning setup  
Instead of retraining all 66 million parameters, this project uses **LoRA (Low-Rank Adaptation)** — a technique that adds a few small, trainable layers on top of the frozen base model.  
That means we only train around **1% of the parameters**, making the fine-tuning process **faster, cheaper, and more memory-efficient**, without losing much accuracy.  

---

### 🏁 In short  
> **DistilBERT** is a compact yet powerful transformer model that understands English text remarkably well.  
> In this project, it’s fine-tuned with **LoRA adapters** to classify user utterances into different intents efficiently — combining strong language understanding with lightweight training.
