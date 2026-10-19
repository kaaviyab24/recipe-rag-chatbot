# Recipe Recommendation Chatbot (RAG)

An ingredient-based recipe chatbot: you enter the ingredients you have, and it suggests dishes you can cook.

## How it works
- Recipes are embedded with sentence-transformers and stored in a FAISS index.
- Hybrid ranking combines semantic similarity with ingredient coverage.
- The top recipes are passed to Llama 3.2 (via Ollama), which writes a grounded answer.
- Gradio provides the chat interface.

## Setup
1. Install dependencies:
   pip install -r requirements.txt
2. Install Ollama and pull the model:
   ollama pull llama3.2
3. Download the recipe dataset and save it as data/food_recipes.csv
   (the CSV is not included in this repo).
4. Open recipe-rag.ipynb and run the cells in order.

## Files
- recipe-rag.ipynb: data cleaning, embeddings, FAISS index, ranking, chatbot
- recipes.faiss, recipe_embeddings.npy, recipes_clean.json: prebuilt index and cleaned data