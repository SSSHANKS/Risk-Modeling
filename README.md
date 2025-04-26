
# Real Estate Price Prediction

This project focuses on predicting real estate prices in Poland using a combination of **web-scraped** data and **synthetic** external datasets, such as unemployment rates, inflation, salaries, and population statistics.

The process involves:
- Scraping real estate offers (apartments, houses, studios) from the Otodom platform.
- Generating synthetic observations to expand the dataset.
- Enriching the data with additional economic indicators.
- Geocoding listings to obtain location coordinates.
- Preprocessing and combining all data sources.
- Building and evaluating machine learning models to predict property prices.

---

## Project Structure

```
.
├── Datasets/
│   ├── average_salary.csv
│   ├── data_final.csv
│   ├── gradual_unemployment_rate.csv
│   ├── inflation.xlsx
│   ├── otodom_apartment_offers.csv
│   ├── otodom_house_offers.csv
│   ├── otodom_offers_coordinates.csv
│   ├── otodom_studio_offers.csv
│   └── population.csv
├── WebScraping/
│   ├── WebScraping_apartments.ipynb
│   ├── WebScraping_house.ipynb
│   └── WebScraping_studio.ipynb
├── Coordianetes.ipynb
├── real_estate_prediction.ipynb
├── raport_rep_project.html
├── LICENSE
└── README.md
```

---

## How It Works

### Web Scraping
The `WebScraping` notebooks collect listing data for:
- **Apartments** (`WebScraping_apartments.ipynb`)
- **Houses** (`WebScraping_house.ipynb`)
- **Studios** (`WebScraping_studio.ipynb`)

Scraping is done with libraries like:
- `requests`
- `BeautifulSoup`
- `pandas`

The data is cleaned and saved into CSV files.

---

### Data Preprocessing

#### Coordinates Assignment
`Coordianetes.ipynb` retrieves missing geographical coordinates for listings using geocoding techniques.

#### Synthetic Observations Generation
To increase the size and diversity of the dataset, the project generates **synthetic real estate offers** by simulating new property listings based on the real data distributions.  
This step helps improve the machine learning models' generalization ability by providing a richer training set.

#### External Data Merging
The real estate listings are enriched with external data sources such as:
- Average Salaries
- Unemployment Rate
- Population Statistics
- Inflation Rates

These datasets are merged with the offers to simulate broader economic conditions.  
All final data are saved in `data_final.csv`.

External data sources:
- [Unemployment Rate (GUS)](https://bdl.stat.gov.pl/bdl/dane/podgrup/wymiary)
- [Average Salary (GUS)](https://bdl.stat.gov.pl/bdl/dane/podgrup/wymiary)
- [Population (World Bank)](https://data.worldbank.org/indicator/SP.POP.TOTL?locations=PL)
- [Inflation (NBP)](https://nbp.pl/statystyka-i-sprawozdawczosc/inflacja-bazowa/)

---

### Model Building
The core machine learning steps are contained in `real_estate_prediction.ipynb`:
- **Data cleaning**
- **Feature engineering**
- **Model training** (e.g., Linear Regression, Decision Trees, XGBoost)
- **Model evaluation** (error metrics like RMSE, R²)

---

## 📑 Check the Report

A detailed description of the data processing, modeling, evaluation metrics, and visualizations can be found in the final report:  
👉 **[`raport_rep_project.html`](./raport_rep_project.html)**

---

## Technologies Used

- Python
- Jupyter Notebook
- pandas, numpy
- scikit-learn
- xgboost
- matplotlib, seaborn
- BeautifulSoup (for scraping)
- requests

---

## How to Run

1. Install the required libraries (suggested: create a virtual environment):
   ```bash
   pip install -r requirements.txt
   ```

2. Run the WebScraping notebooks (optional — data is already provided).

3. Run:
   - `Coordianetes.ipynb` to attach coordinates.
   - `real_estate_prediction.ipynb` to train and evaluate models.

4. Review the final results in `raport_rep_project.html`.

---

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.
