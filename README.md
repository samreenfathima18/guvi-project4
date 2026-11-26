# 🎬 IMDb 2024 Movie Recommendation System Using Storylines

A content-based movie recommendation system built with **Python**, **Natural Language Processing (TF-IDF & Cosine Similarity)**, and **Streamlit**. Users can input any custom plot description or storyline idea to discover the **Top 5 most similar 2024 movies** from IMDb in real time.

## 📌 Project Overview

Traditional recommendation systems rely heavily on user watch history or ratings, creating a "cold-start" problem for brand-new releases. This project solves that challenge by recommending 2024 IMDb movies purely based on **storyline text similarity**.

### Key Features
- **Automated Web Scraping:** Extracts 2024 movie titles and plot summaries from IMDb using **Selenium**.
- **NLP Text Preprocessing:** Cleans text by lowercasing, stripping punctuation/whitespace, and filtering English stop words.
- **TF-IDF & Cosine Similarity Engine:** Converts storylines into numerical vectors and computes similarity angles to rank the top 5 matches with confidence scores.
- **Interactive Web Interface:** Built with **Streamlit**, utilizing `@st.cache_data` and `@st.cache_resource` for fast, responsive queries.

## 📁 Project Structure

```text
imdb-movie-recommender/
├── data/
│   └── imdb2024_movies.csv    # Scraped/cleaned dataset of 2024 IMDb movies
├── scraper.py                 # Selenium script to scrape IMDb movie titles & storylines
├── app.py                     # NLP preprocessing, similarity engine & Streamlit UI
├── requirements.txt           # Python dependencies for cross-platform portability
└── README.md                  # Project documentation and setup instructions
```

## ⚙️ System Workflow

1. **Data Collection (`scraper.py`):**
   - Launches a headless Chrome browser via Selenium to scrape 2024 movie titles and storylines from IMDb and exports the data to `data/imdb2024_movies.csv`.
2. **Text Preprocessing (`clean_text`):**
   - Removes null entries, converts text to lowercase, strips punctuation and extra spaces using Regular Expressions (`re`), and removes common English stop words.
3. **Feature Extraction (`TfidfVectorizer`):**
   - Transforms cleaned storylines into a TF-IDF matrix, assigning higher weights to distinctive plot keywords over generic words.
4. **Recommendation Scoring (`cosine_similarity`):**
   - Vectorizes the user's input storyline and calculates the cosine similarity against all indexed 2024 movies, returning the **Top 5 matches** (`score > 0`).

## 🚀 Installation & Execution

Follow these steps to run the project locally on Windows, macOS, or Linux:

### 1. Clone the Repository
```bash
git clone :https://github.com/samreenfathima18/guvi-project4/blob/main/project4.ipynb
```
### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. (Optional) Run the Web Scraper
If you want to scrape fresh data from IMDb:
```bash
python scraper.py
```
*(Note: A pre-collected dataset is already included in `data/imdb2024_movies.csv`.)*

### 4. Launch the Streamlit Application
```bash
streamlit run app.py
```
Open your browser and navigate to `http://localhost:8501`.

---

## 💡 Example Usage

- **User Input:**
  > *"A young wizard begins his journey at a magical school where he makes friends and enemies, facing dark forces along the way."*
- **System Output:**
  - Displays the **Top 5 most similar 2024 movies** along with their full storylines and **Match Confidence (%)** scores.

## 🛠️ Tech Stack & Standards

- **Language:** Python 3.x (Formatted according to **PEP 8** coding standards)
- **Data Manipulation:** Pandas
- **Web Scraping:** Selenium
- **NLP & Machine Learning:** Scikit-Learn (`TfidfVectorizer`, `cosine_similarity`)
- **Frontend UI:** Streamlit
