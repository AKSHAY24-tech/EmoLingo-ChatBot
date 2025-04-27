# EmoLingo-ChatBot
EmoLingo is an NLP-based chatbot that predicts user emotion, tone, and English proficiency using fine-tuned transformer models. It integrates these predictions into a unified response pipeline and features an interactive Streamlit UI for real-time, emotionally aware conversations.

## 🚀 Features

- 🎭 **Emotion Detection** — Identifies emotions like joy, sadness, anger, etc.
- ✍️ **Tone Classification** — Distinguishes between various writing tones (formal, casual, empathetic, etc.)
- 🧠 **English Proficiency Estimation** — Assesses language fluency and command of English
- 🔗 **Multi-Model Response Pipeline** — Combines outputs for emotion-aware and style-consistent replies
- 💬 **Streamlit Interface** — User-friendly, interactive chat experience

## 📁 Project Structure

    Emolingo-ChatBot/
    ├── app.py                       # Main application script for Streamlit UI
    ├── emotion_classification       # Module for emotion detection models
    ├── writing_tone.py              # Module for tone classification
    ├── Writing_proficiency.py       # Module for assessing English proficiency
    ├── pipeline.py                  # Integrates all models into a unified pipeline
    ├── writing_tone_dataset.csv     # Dataset for training tone classification model
    ├── requirements.txt             # Necessary Packages
    └── README.md

## 📚 Datasets

- **Emotion Classification**  
  [GoEmotions Dataset (Kaggle)](https://www.kaggle.com/datasets/ankurzing/sentiment-analysis-for-goemotions)  
  Used for training and evaluating the emotion detection models across 27 fine-grained emotion categories.

- **Writing Tone Classification**  
  Custom labeled dataset: `writing_tone_dataset.csv` (included in this repository)  
  Used to train a RoBERTa-based model to classify user input into various writing styles such as Formal, Casual, Empathetic, etc.

- **English Proficiency Classification**  
  [ICNALE Corpus](https://language.sakura.ne.jp/icnale/)  
  A comprehensive corpus of non-native English texts used to assess language fluency and proficiency levels across learners from multiple linguistic backgrounds.


## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/akshay-menta/EmoLingo-ChatBot.git
cd EmoLingo-ChatBot
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

#### 🔐 Hugging Face Token Required

Hugging Face API tokens have been removed from the code for security purposes.

To use the application, you must insert **your own Hugging Face API token** manually in the code.

1. Go to [https://huggingface.co/settings/tokens](https://huggingface.co/settings/tokens) to generate a new token.
2. Open the relevant file (e.g., `emotion_classification module`) and locate the line where the token is used.
3. Replace the placeholder or comment with your actual token, like this:

```python
HUGGINGFACEHUB_API_TOKEN = "your_token_here"
```

3. **Set up the English Proficiency Model**

⚠️ Important: The English proficiency model is not stored in the repository due to size limitations. You must generate it before running the app.

Run the following command to create and save the model locally:

```bash
python Writing_proficiency.py
```
This step will save the model artifacts required by the ```app.py```.

4. **Run the Streamlit Application**

```bash
streamlit run app.py
```

## 📊 Model Architecture
```
| Component              | Method                                 | Framework      |
|------------------------|----------------------------------------|----------------|
| Emotion Detection      | Ensemble method (T5,ROBERTA,ELECTRA)   | Hugging Face   |
| Writing Tone Classifier| RoBERTa-based model + custom data      | Hugging Face   |
| Proficiency Estimator  | DistilBERTa-based model                | Hugging Face   |
| Response Generator     | Dynamic prompt logic with UI           | Streamlit      |
```

## 🧪 Usage

1. Type your message in the chatbot UI.

2. EmoLingo will:
   - 🎭 Detect the emotional state of the user
   - ✍️ Assess the tone and English proficiency
   - 💬 Generate a thoughtful, style-matching reply

3. Watch how the chatbot dynamically adapts responses based on emotional and stylistic cues.


## 🎥 Demo

Check out the EmoLingo ChatBot in action:

https://github.com/user-attachments/assets/ab90e120-3d03-4862-ae7d-fcd1560f3161

