# 🎬 Movie Recommender System

A content-based movie recommendation web app built with Python and Streamlit, deployed on Streamlit Cloud.

---

## 🔗 Live Demo

Try it here:
https://movie-recommender-system-rvo7wwhvyjwx74zjnwlutd.streamlit.app/
---

## 🛠️ Tech Stack

- **Python 3.12**  
- **Streamlit** for UI  
- **Pandas** for data handling  
- **Scikit-learn** for similarity computation  
- **Requests** for TMDB & Hugging Face integration  
- **Hugging Face Datasets** to host large `.pkl` files  

---

## ⚙️ Architecture Overview

1. **Data Preparation** (offline)  
   - Compute cosine-similarity matrix on movie metadata  
   - Serialize `movie_list.pkl` & `similarity.pkl`

2. **Hosting Assets**  
   - Code (without `.pkl`) in GitHub  
   - `.pkl` files on Hugging Face

3. **Streamlit App (`app.py`)**  
   - **On startup**: download & cache `.pkl` files  
   - **UI**: dropdown + “Show Recommendation” button  
   - **Logic**: top-5 similar movies + TMDB poster fetch

4. **Deployment**  
   - GitHub → Streamlit Cloud → Public URL

---

## 🚀 Getting Started Locally

```bash
git clone https://github.com/vanshhari222/movie-recommender-system.git
cd movie-recommender-system

python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
streamlit run app.py
