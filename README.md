
##  Project: Voice Similarity Using ECAPA-TDNN, Wav2Vec2 & SQLite

###  Purpose

To determine whether a given voice recording matches any known speaker in a local database using advanced embedding models for **speaker recognition**, with data stored in a lightweight **SQLite** system.

---

### How It Works

1. **Audio Input**

   * Users upload `.wav` files.
   * Each file is processed and normalized using `torchaudio`.

2. **Speaker Embedding Extraction**

   * Two models can be used:

     * **Wav2Vec2**: A general-purpose speech model that provides speech embeddings.
     * **ECAPA-TDNN (from SpeechBrain)**: A powerful speaker embedding model specifically designed for **speaker recognition**.
   * Embeddings are extracted and converted into fixed-size vectors (e.g., 192 or 768 dimensions).

3. **Database Storage**

   * Embeddings and associated file names are stored in a **SQLite** database using BLOB format.
   * This allows persistent and searchable storage without needing a full server.

4. **Similarity Computation**

   * New voice uploads are compared against existing embeddings in the database using **cosine similarity**.
   * A threshold (e.g., 0.75) is used to determine if the voice is:

     * **Matched** to a known speaker
     * Or a **new speaker**, to be added to the database

---

###  Technologies Used

* **ECAPA-TDNN (SpeechBrain)**: State-of-the-art speaker embedding model
* **Wav2Vec2 (Facebook AI)**: Self-supervised speech model
* **Torchaudio**: Audio loading and processing
* **Transformers**: Model management
* **SQLite**: Local embedding database
* **Scikit-learn**: Cosine similarity analysis

---

###  Applications

* Speaker verification systems
* Voice deduplication in datasets
* Lightweight voice ID systems for edge devices
* Audio forensics & voiceprint comparison

---
![voice similarity](https://github.com/user-attachments/assets/4a79190f-b1b4-4f3e-9863-5d7654d333d9)

