# Malayalam Song Lyrics Sentiment Analysis Across Five Decades

This project analyzes how the sentiment in Malayalam film songs has shifted from the 1980s – 2020s. I utilized manual annotations, rule-based tools, ChatGPT, and clear visualizations. Demonstrates an end-to-end NLP workflow, from scraping -> preprocessing -> analysis -> visualization.

---

## Project Motivation

1. **Under-resourced language NLP:** Malayalam’s abdundant morphology, diglossia (spoken vs written), and sparse resources makes this more challenging for computational analysis
2. **Lyrical and cultural comprehension:** Song and poetic lyrics gives consideration to social, mood, and dialect trends and changes across time  
3. **Methodological comparison:** This project analyzes how human sentiment labels, ChatGPT, VADER, and TextBlob might differ on the same data set 
---

## Dataset

| Decade | Songs (3 per decade) | Source |
| ------ | ------------------- | ------ |
| 2020s  | “Aangu Vaana Konilu” (2024) · “Minnal Vala” (2025) · “Eyy Banane” (2024) | malayalasangeetham.info |
| 2010s  | “Entammede Jimmiki Kammal” (2017) · “Malare Ninne” (2015) · “Kudukku” (2019) | same |
| 2000s  | “Picha Vaacha Naal” (2009) · “Nee oru puzhayaay” (2003) · “Mazhavil” (2006) | same |
| 1990s  | “Pathiravaayi Neram” (1992) · “Kilukilppambaram” (1991) · “Saarangi Maaril” (1990) | same |
| 1980s  | “Doore Kizhakkudikkin” (1988) · “Thumbi Vaa” (1982) · “Vellichillum” (1982) | same |

**Total**: 15 songs scraped with **Beautiful Soup** → stored as `Sentiment_of_Malayalam_song_with_decades.csv`.

---

## Method Overview

1. **Scrape & store** – `requests` + `beautifulsoup4`  
2. **Manual labeling** – (Positive, Neutral, Negative)  
3. **Automated sentiment**  
   * **ChatGPT** (GPT-4, zero-shot)  
   * **VADER**  
   * **TextBlob**  
4. **Evaluation** – Confusion matrix using `pandas`, accuracy, recall, F1 via `scikit-learn`  
5. **Visualization** – `matplotlib` + `seaborn` bar charts for decade timeline and trends
6. **Testing** – `pytest` unit tests for cleaning, tokenization, and sentiment result shape

---

## Project Structure

```text
malayalam-song-sentiment/
│
├─ data/
│   └─ Sentiment_of_Malayalam_song_with decades.csv            # final annotated dataset
├─ notebooks/
│   └─ Malayalam Sentiment Analysis.ipynb  # main Jupyter notebook (scraping, analysis, visualization) 
├─ visualizations/
│   ├─ Sentiment of Malayalam Songs by Decade (ChatGPT).png
│   ├─ Sentiment of Malayalam Songs by Decade (Manual).png
│   ├─ Sentiment of Malayalam Songs by Decade (TextBlob).png
│   ├─ Sentiment of Malayalam Songs by Decade (VADER).png
│   ├─ confusion_matrix_chatgpt.png
│   ├─ confusion_matrix_textblob.png
│   └── confusion_matrix_vader.png
│
├── LICENSE
└── README.md  # where you currently are at

## Installation
```bash
git clone https://github.com/squishridyvi/malayalam-song-sentiment.git
cd malayalam-song-sentiment
python -m venv .venv && source .venv/bin/activate      # create virtual env
pip install -r requirements.txt
```
---

## What I Plan to Improve In the Future 
1. Adding `pytest` unit tests for preprocessing steps (better cleaning, tokenization, etc.) 
2. Expand dataset to 100+ songs and annotations for more accurate results
3. Using part-of-speech for nuance
4. Exploring word frequency trends across decades 
   




