# 🇵🇰 Pakistan Travel Chatbot

An AI-powered chatbot that answers travel questions about Pakistan, grounded entirely in a reference travel guide document — not the model's general knowledge. Built with OpenAI + LangChain using a retrieval-augmented approach so answers stay accurate and source-backed.

**Tools:** Python · LangChain · OpenAI API · Retrieval-Augmented Generation (RAG)

---

## How It Works

1. The reference document (`travel guide.pdf`) is loaded and split into chunks.
2. Chunks are embedded and indexed for retrieval.
3. On each question, the most relevant chunks are retrieved and passed to the OpenAI model as context.
4. LangChain manages session memory, so the bot maintains conversation context across turns.
5. A lightweight Colab widget UI handles the chat interface.

## Features

- Answers grounded in a reference PDF (not free-form model guesses)
- Friendly, culturally respectful responses
- Session memory across a conversation
- Simple UI via Colab widgets

## Tech Stack

- Python
- LangChain
- OpenAI API
- Jupyter/Colab

## Setup

```bash
git clone https://github.com/ahmed191034/chatbot.git
cd chatbot

python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS/Linux

pip install -r requirements.txt
```

Create a `.env` file from the template and add your key:

```bash
cp .env.example .env
```

```
OPENAI_API_KEY=your_openai_api_key_here
```

## Running It

Open `pakistan_travel_chatbot.ipynb` in Jupyter or Google Colab and run all cells. The notebook loads `travel guide.pdf`, builds the retrieval index, and launches the chat widget.

## Project Structure

```
├── pakistan_travel_chatbot.ipynb   # main notebook — RAG pipeline + chat UI
├── travel guide.pdf                # source document the bot is grounded in
├── requirements.txt
├── .env.example
└── .gitignore
```

## Example

```
You: What's the best time of year to visit Hunza Valley?
Bot: Based on the travel guide, the best time to visit Hunza Valley is between
     April and October, with autumn (October) especially known for its
     colourful foliage...
```

*(Swap in a real transcript once you have one — it's the single most convincing thing you can add to this README.)*

## What I'd Improve Next

- Move off Colab widgets to a small Streamlit or Gradio interface for easier sharing
- Add source citations to each answer (which guide section it came from)
- Support multiple reference documents instead of a single PDF
