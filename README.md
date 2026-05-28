# ✈️ British Airways — Data Science Virtual Experience

**Forage Programme | Warda Afsheen | 2026**

A two-task data science project completed as part of the British Airways Virtual Experience on Forage. The project covers customer review analysis, predictive modelling of booking behaviour, and lounge capacity planning using assumptions-based modelling.

---

## 📁 Project Structure

```
british-airways-forage/
│
├── task1_review_analysis/
│   └── (web scraping + sentiment analysis notebooks)
│
├── task2_booking_prediction/
│   ├── BA_Task2_Summary_Warda.pptx     # Findings presentation
│   └── booking_prediction.ipynb        # Model notebook
│
├── task3_lounge_eligibility/
│   └── BA_Lounge_Eligibility_Model_Warda.xlsx   # Lookup model + analysis
│
└── README.md
```

---

## Task 1 — Customer Review Analysis

**Objective:** Scrape and analyse British Airways customer reviews to surface sentiment trends and key pain points.

**Approach:**
- Scraped customer review data from a third-party airline review site using Python (`BeautifulSoup` / `requests`)
- Cleaned and pre-processed raw text data with `pandas`
- Performed sentiment analysis to classify reviews and identify the most frequently mentioned themes (delays, service quality, seat comfort, food, staff)

**Tools:** Python · BeautifulSoup · pandas · NLTK / TextBlob

---

## Task 2 — Predicting Customer Booking Completion

**Objective:** Build a machine learning model to predict whether a customer will complete a flight booking, using behavioural and trip features.

### Dataset
| Property | Value |
|----------|-------|
| Records | 50,000 customer entries |
| Features | 13 variables |
| Target | Booking completion (binary) |
| Completion rate | 14.96% (class imbalance present) |

### Model
**Random Forest Classifier** (scikit-learn)

| Metric | Score |
|--------|-------|
| Accuracy | 85.2% |
| ROC-AUC | 0.779 |
| CV AUC (5-fold) | 0.771 |
| Precision (bookings) | 54.1% |

### Key Findings

- **Purchase lead time** is the single strongest predictor — customers who book further in advance are significantly more likely to complete their booking
- **Route and booking origin** account for ~31% of total predictive power — destination matters
- **Time-based features** (flight hour, day of week) are strong signals, suggesting behaviour varies by travel window
- **Add-on selections** (meals, extra baggage) indicate higher purchase intent and correlate with completed bookings

**Tools:** Python · scikit-learn · pandas · matplotlib

---

## Task 3 — Lounge Eligibility Capacity Model

**Objective:** Build a scalable lookup model to estimate how many passengers on any given flight are eligible for each BA lounge tier at Heathrow Terminal 3.

### Lounge Tiers Modelled
| Tier | Lounge | Eligible Passengers |
|------|--------|-------------------|
| Tier 1 | Concorde Room | First Class passengers (0–1%) |
| Tier 2 | First Lounge | BA Gold Members (3–6%) |
| Tier 3 | Club Lounge | BA Silver / Club World Business Class (11–22%) |

### Grouping Approach

Flights grouped by two variables that are available for any future schedule:

- **Route type** — Short-haul (European) vs Long-haul (intercontinental). Long-haul routes carry proportionally more premium class and high-tier loyalty card holders.
- **Time of day** — Morning/Evening flights attract more business travellers (higher lounge eligibility); Lunchtime/Afternoon skew leisure (lower eligibility).

This makes the model reusable without needing specific aircraft details or flight numbers.

### Sample Output (20 representative flights)

| Flight | Departure | Destination | Category | Tier 2 % | Tier 3 % |
|--------|-----------|-------------|----------|----------|----------|
| BA4878 | 09:55 | IST | Short-haul Morning | 6.1% | 21.7% |
| BA7282 | 06:42 | LAX | Long-haul Morning | 3.0% | 11.9% |
| BA5497 | 18:29 | IST | Short-haul Evening | 8.9% | 30.0% |
| BA5903 | 13:23 | ORD | Long-haul Lunchtime | 0.9% | 4.3% |

> Note: Tier 1 (Concorde Room) does not currently operate at Terminal 3. Estimates model hypothetical future demand.

**Tools:** Microsoft Excel · lookup tables · assumptions-based modelling

---

## Skills Demonstrated

`Python` `pandas` `scikit-learn` `Random Forest` `Machine Learning` `Web Scraping` `Data Cleaning` `Feature Engineering` `Data Visualisation` `Assumptions-Based Modelling` `Business Communication`

---

## Programme

[British Airways Data Science Virtual Experience — Forage](https://www.theforage.com/simulations/british-airways/data-science-XNS9)

---

## Author

**Warda Afsheen**
CS Undergraduate, Lahore College for Women University | Honhaar Merit Scholar
📧 wardaafsheen@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/wardaafsheen)
