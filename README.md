## Netflix-LLM-Profiling

README: AI-Driven Ad Category Matching System

## Overview
This repository contains two AI-driven implementations for personalized recommendations:
1. Movie-Based Narrative Generation (`Group_project_Netflix_Scenecraft.ipynb`): Uses LLMs (Meta Llama 3.1) to analyze user preferences and generate alternate movie endings.
2. Ad Category Matching System (`GroupProject_Netflix_Adsense.ipynb`): Uses BERT for user profiling, movie context analysis, and an FFNN model to match movies and users with the most relevant ad category.

---

## 1. Movie-Based Narrative Generation
### How It Works
- User Profiling: Analyzes watch history and user comments to determine preferred movie genres and narrative styles.
- Preference Analysis: Uses LLM to infer preferred storytelling elements (narrative structure, emotional tone, etc.).
- Narrative Generation: The LLM generates a movie ending aligned with the user's taste.

### How to Run (Google Colab)
1. Open `Group_project_Netflix_Scenecraft.ipynb` in Google Colab.
2. Install dependencies:
   ```bash
   pip install transformers torch pandas
   ```
3. Ensure you have access to Meta Llama 3.1 and login with your Hugging Face token:
   ```python
   from huggingface_hub import login
   from google.colab import userdata
   hf_token = userdata.get('HF_token')
   login(token=hf_token)
   ```
4. Run the notebook cells sequentially.

### Expected Output
- The script outputs a structured movie ending based on user preferences.
- Example:
  ```
  Generated Movie Ending:
  "As Maya walks into the unknown, the sun sets, symbolizing the dawn of a new journey."
  ```

---

## 2. Ad Category Matching System
### How It Works
- User Profiling (BERT): Analyzes watch history and user comments to infer genre and interest preferences.
- Movie Context Analysis: Extracts movie genres, mood, themes, and ad suitability.
- FFNN-Based Ad Category Matching: Uses a 40-dimensional feature vector (user + movie attributes) to predict the most relevant ad category.

### How to Run (Google Colab)
1. Open `GroupProject_Netflix_Adsense.ipynb` in Google Colab.
2. Install dependencies:
   ```bash
   pip install torch transformers pandas scikit-learn
   ```
3. Run all notebook cells to profile users, analyze movie context, and match ad categories.

### Expected Output
- The script displays the user's profile, movie context, and the best-matched ad category.
- Example:
  ```
  BEST AD CATEGORY MATCH:
  ► Family (Confidence: 0.99)
  ```

---

## Data Structure
- The data used in the implementation is generated within the code dynamically.
- Additionally, a dummy dataset file (`GroupProject_DummyData.xlsx`) is provided with separate sheets for users, watch history, user comments, movies, and ad categories.

---

## Execution Requirements
- This code is optimized to run on Google Colab with a T4 GPU for efficient processing.
- Ensure that GPU acceleration is enabled in Colab (`Runtime > Change runtime type > Hardware accelerator: GPU`).

---
