# 🎬 Movie Profit Analysis

An exploratory data analysis (EDA) of 3,400+ movies, looking at **budgets, box-office earnings, genres, MPAA ratings and distributors** to understand what drives a movie's financial success.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458)
![Matplotlib](https://img.shields.io/badge/Matplotlib-visualization-11557c)
![Jupyter](https://img.shields.io/badge/Jupyter-notebook-orange)

---

## 📌 Project Overview

The film industry spends hundreds of millions of dollars on production, yet many movies never earn that money back. This project explores a movie dataset to answer:

1. What does the data look like, and how clean is it?
2. How are budgets and box-office earnings distributed?
3. Which genres, ratings and distributors earn the most?
4. Does spending more money actually lead to higher earnings?
5. Which movies were the most (and least) profitable?
6. How has the movie business changed over time?

## 📂 Repository Structure

```
├── data/
│   └── movie_profit.csv          # Raw dataset
├── Movie_Profit_Analysis.ipynb   # Full analysis notebook
└── README.md
```

## 🗃️ Dataset

| Column | Description |
|---|---|
| `release_date` | Date the movie was released |
| `movie` | Movie title |
| `production_budget` | Estimated cost to produce the movie (USD) |
| `domestic_gross` | Box-office earnings in the US (USD) |
| `worldwide_gross` | Box-office earnings worldwide (USD) |
| `distributor` | Studio that distributed the movie |
| `mpaa_rating` | Age rating (G, PG, PG-13, R) |
| `genre` | Drama, Comedy, Action, Adventure or Horror |

**Source:** _add the dataset source/link here (e.g. Kaggle)_

## 🧹 Data Cleaning

- Dropped the unused `Unnamed: 0` index column
- Removed rows with missing `distributor` (48) or `mpaa_rating` (137), leaving **3,230** movies
- Checked for duplicates (none found)
- Converted `release_date` from text to a proper datetime
- Identified movies with **$0 gross** (likely missing data) and excluded them from the profit analysis so they would not appear as false 100% losses

## ⚙️ Feature Engineering

| New column | Meaning |
|---|---|
| `profit` | Worldwide gross − production budget |
| `roi` | Profit ÷ budget (profit per $1 spent) |
| `is_profitable` | Whether the movie earned more than it cost |
| `release_year`, `release_month`, `decade` | Date parts used for trend analysis |

## 🔍 Key Findings

- **The "average" movie is misleading.** Mean budget is about $34.6M but the median is $22M, and mean worldwide gross is about $98M vs a $44M median. A few blockbusters pull averages up.
- **Drama is the most common genre** (1,180 movies), followed by Comedy (775) and Action (540). Horror is the least common (266).
- **Action and Adventure are the most expensive genres**, averaging about $59M and $62M. Drama, Comedy and Horror average about $19-25M.
- **Family-friendly ratings earn more per movie.** G-rated films average about $82.5M domestic gross vs about $32.1M for R-rated films.
- **A few studios dominate.** Warner Bros. (about $48.2B), 20th Century Fox (about $47.0B) and Universal (about $46.0B) lead total worldwide gross.
- **Bigger budgets tend to earn more, but with more risk.** Spending does not guarantee profit.
- _Add your ROI-by-genre, profitability share and release-month findings here after running sections 6 and 7 of the notebook._

## 🛠️ Tools & Libraries

- **Python 3**
- **pandas** and **NumPy** for data cleaning and analysis
- **Matplotlib** for visualization
- **Jupyter Notebook**

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

# 2. Install dependencies
pip install pandas numpy matplotlib jupyter

# 3. Launch the notebook
jupyter notebook Movie_Profit_Analysis.ipynb
```

Make sure `movie_profit.csv` is inside the `data/` folder before running.

## ⚠️ Limitations

- Budgets exclude marketing and distribution costs, so real profits are lower than shown.
- Money values are not adjusted for inflation, which affects comparisons across decades.
- Only 5 genres and 4 ratings appear in the data, and rows with missing ratings or distributors were removed.
- This is exploratory analysis: it shows relationships, not causes.

## 🚀 Possible Next Steps

- Adjust all values for inflation
- Add IMDb or Rotten Tomatoes scores to test whether quality affects earnings
- Build a simple model to predict worldwide gross from budget, genre and rating
- Create an interactive dashboard (Power BI, Tableau or Streamlit)

## 👤 Author

**Vannovich**
Graduate student, MSc Information Science & Technology (Data Science), University of Buea

🔗 [LinkedIn](https://www.linkedin.com/in/awontu-vannovich-ndzifoin-a629b4225/) · 💻 [GitHub](https://github.com/vannovich)

---

⭐ If you found this project useful, feel free to star the repository.
