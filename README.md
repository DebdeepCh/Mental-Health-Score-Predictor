# 🧠 Mental Health Score Predictor

> **An end-to-end Machine Learning web application that predicts a student's mental health score (0–10) from daily lifestyle, academic, digital, and stress-related habits.**

Built using **Python, Scikit-learn, FastAPI, and Vanilla JavaScript**, this project takes a complete ML workflow from **data exploration and model training to REST API development, frontend integration, and cloud deployment.**

---

<p align="center">

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge\&logo=scikit-learn\&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge\&logo=fastapi\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![Render](https://img.shields.io/badge/Deployed-Render-46E3B7?style=for-the-badge\&logo=render\&logoColor=black)

</p>

---

## ✨ Live Demo


### 🧠 [Mental Health Signal — Student Wellness Analytics](https://mental-health-score-predictor-1-x2ou.onrender.com/)

Explore the live application and generate a personalized, non-clinical wellness score based on daily lifestyle, academic, digital, and stress-related habits.

> ⚠️ **Note:** The application is hosted on Render's free tier. If the backend has been inactive, the first request may take **30–60 seconds** while the service spins up.


---

## 🎯 What Does It Do?

The application collects a few details about a student's **daily habits, academic routine, digital behavior, lifestyle, and perceived stress** and uses a trained regression model to estimate a **mental health score from 0 to 10**.

The result is displayed through an interactive **visual gauge** along with general, non-clinical wellness suggestions.

### 🧩 Input Categories

| Category                         | Information Collected                                                          |
| -------------------------------- | ------------------------------------------------------------------------------ |
| 👤 **Profile**                   | Age, Gender, Country                                                           |
| 🎓 **Academic & Digital Habits** | Academic Level, Most Used Platform, Purpose of Use, Screen Time, Phone Unlocks |
| 🏃 **Lifestyle**                 | Study Hours, Physical Activity, Sleep                                          |
| 🧘 **Stress**                    | Perceived Stress Level                                                         |
| 📊 **Prediction**                | Mental Health Score (0–10) + Visual Gauge                                      |

---

## 🔥 Key Features

* 🤖 **Machine Learning Prediction** — Regression model trained on student lifestyle and social-media data
* ⚡ **Fast REST API** — Model served through FastAPI
* 🌐 **Responsive Web Interface** — Built entirely with HTML, CSS & JavaScript
* 📊 **Interactive Result Visualization** — Predicted score presented through a visual gauge
* 🧹 **End-to-End ML Pipeline** — Data cleaning → EDA → Feature Engineering → Training → Deployment
* 🔌 **Swagger API Documentation** — Interactive API testing through `/docs`
* ☁️ **Cloud Deployment** — Backend and frontend deployed using Render
* 📱 **No Frontend Framework** — Lightweight Vanilla JavaScript implementation

---

## 🏗️ System Architecture

```text
                ┌─────────────────────────┐
                │       User Input        │
                │  Lifestyle & Habits    │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │   Vanilla JS Frontend   │
                │    HTML + CSS + JS      │
                └────────────┬────────────┘
                             │
                         POST /predict
                             │
                             ▼
                ┌─────────────────────────┐
                │      FastAPI Backend    │
                │   Request Validation    │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │   Scikit-learn Model    │
                │  Preprocessing + Model  │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │   Predicted Score 0–10  │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │  Gauge + Wellness Tips  │
                └─────────────────────────┘
```

---

# 🛠️ Tech Stack

### 🧠 Machine Learning

| Technology           | Purpose                             |
| -------------------- | ----------------------------------- |
| **Python**           | Data processing & model development |
| **Pandas**           | Data manipulation                   |
| **Scikit-learn**     | Preprocessing & regression model    |
| **Joblib**           | Model serialization                 |
| **Jupyter Notebook** | EDA & experimentation               |

The trained pipeline uses a **Scikit-learn `ColumnTransformer`** for preprocessing before generating the final prediction.

### ⚙️ Backend

| Technology   | Purpose                     |
| ------------ | --------------------------- |
| **FastAPI**  | REST API                    |
| **Pydantic** | Request/response validation |
| **Uvicorn**  | ASGI server                 |

### 🎨 Frontend

| Technology             | Purpose                     |
| ---------------------- | --------------------------- |
| **HTML5**              | Page structure              |
| **CSS3**               | Styling & responsive design |
| **Vanilla JavaScript** | UI logic & API integration  |
| **Fetch API**          | Backend communication       |

### ☁️ Deployment

**Render** — Backend and static frontend hosting.

---

# 📊 Dataset

### `Student Social Media And Mental Health Impact.csv`

The dataset contains student-level information covering:

* Demographics
* Academic level
* Social media usage
* Purpose of social media usage
* Daily screen time
* Phone unlock frequency
* Study hours
* Physical activity
* Sleep duration
* Perceived stress

These features are used to train a regression model that predicts an overall **mental health score**.

---

# 🔬 Machine Learning Workflow

The model development process follows a complete ML pipeline:

```text
Raw Dataset
     │
     ▼
Data Cleaning
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Feature Engineering
     │
     ▼
Categorical / Numerical Preprocessing
     │
     ▼
Model Training
     │
     ▼
Model Evaluation
     │
     ▼
Pipeline Serialization (.pkl)
     │
     ▼
FastAPI Deployment
```

The trained model is saved as:

```text
Mental_Health_Model.pkl
```

and loaded by the FastAPI backend during application startup.

---

# 🔌 API Reference

## `GET /`

Basic API health check.

### Response

```json
{
  "Welcome Guys"
}
```

---

## `POST /predict`

Accepts a student's lifestyle and behavioral information and returns a predicted mental health score.

### Request

```json
{
  "age": 21,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 4.5,
  "daily_unlocks": 60,
  "study_hours": 3.0,
  "physical_activity_hours": 1.0,
  "sleep_hours_per_night": 6.5,
  "stress_level": "Medium"
}
```

### Request Fields

| Field                     | Type     | Constraints                                                                                                     |
| ------------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| `age`                     | `int`    | 10–100                                                                                                          |
| `gender`                  | `string` | Male, Female                                                                                                    |
| `country`                 | `string` | Free text                                                                                                       |
| `academic_level`          | `string` | High School, Undergraduate, Graduate                                                                            |
| `most_used_platform`      | `string` | Facebook, LinkedIn, Instagram, Snapchat, Twitter, YouTube, TikTok, LINE, KakaoTalk, VKontakte, WhatsApp, WeChat |
| `purpose_of_use`          | `string` | Networking, Education, Entertainment, News                                                                      |
| `avg_daily_usage_hours`   | `float`  | 0–24                                                                                                            |
| `daily_unlocks`           | `int`    | ≥ 0                                                                                                             |
| `study_hours`             | `float`  | 0–24                                                                                                            |
| `physical_activity_hours` | `float`  | 0–24                                                                                                            |
| `sleep_hours_per_night`   | `float`  | 0–24                                                                                                            |
| `stress_level`            | `string` | Low, Medium, High, Very High                                                                                    |

### Response

```json
{
  "predicted_mental_health_score": 6.77
}
```

### 📚 Interactive API Documentation

Once the server is running, interactive Swagger documentation is available at:

```text
http://127.0.0.1:8000/docs
```

---

# 🚀 Run Locally

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/MrSingh-Badal/Mental-Health-Score-Predictor.git
cd Mental-Health-Score-Predictor
```

## 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
source venv/bin/activate
```

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

## 4️⃣ Start the Backend

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

Swagger documentation:

```text
http://127.0.0.1:8000/docs
```

## 5️⃣ Start the Frontend

You can open `index.html` directly in your browser, or serve it locally:

```bash
python -m http.server 5500
```

Then open:

```text
http://localhost:5500/index.html
```

### ⚙️ API Configuration

`script.js` contains an `API_BASE` / `API_BASE_URL` constant.

For local development, point it to:

```text
http://127.0.0.1:8000
```

For production, point it to your deployed backend URL.

---

# ☁️ Deployment — Render

### Build Command

```bash
pip install -r requirements.txt
```

### Start Command

```bash
uvicorn main:app --host 0.0.0.0 --port $PORT
```

### ⚠️ Important

Render runs on **Linux**, where filenames are case-sensitive.

For example, if your code contains:

```python
joblib.load("Mental_Health_Model.pkl")
```

the repository must contain the file with exactly the same capitalization:

```text
Mental_Health_Model.pkl
```

This can work on Windows but fail after deployment if the filename casing doesn't match.

---

# 📁 Project Structure

```text
Mental-Health-Score-Predictor/
│
├── 📄 main.py
│   └── FastAPI backend & prediction endpoint
│
├── 📓 mental_health.ipynb
│   └── EDA, feature engineering & model training
│
├── 🤖 Mental_Health_Model.pkl
│   └── Trained Scikit-learn pipeline
│
├── 📊 Student Social Media And Mental Health Impact.csv
│   └── Training dataset
│
├── 📦 requirements.txt
│   └── Python dependencies
│
├── 🌐 index.html
│   └── Frontend structure
│
├── 🎨 style.css
│   └── Frontend styling
│
├── ⚡ script.js
│   └── Frontend logic & API integration
│
└── 📖 README.md
```

---

# 🗺️ Future Improvements

The project can be extended in several directions:

* [ ] 🔍 Add **SHAP-based model explainability**
* [ ] 📈 Display which lifestyle factors contributed most to a prediction
* [ ] 🔐 Add user authentication
* [ ] 🗃️ Store prediction history
* [ ] 🌍 Expand the dataset to improve representation across countries and demographics
* [ ] 🧠 Experiment with additional regression algorithms and hyperparameter tuning
* [ ] 📊 Add model performance metrics to the web interface
* [ ] 🏗️ Separate frontend and backend into independently deployable services

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Commit your changes
5. Open a Pull Request

For major changes, please open an issue first to discuss the proposed modification.

---

# ⚠️ Disclaimer

This application is intended **strictly for educational, experimental, and self-reflection purposes**.

The predicted score is generated by a machine learning model and **should not be interpreted as a medical diagnosis, clinical assessment, or professional mental-health evaluation**.

If you are experiencing mental-health difficulties, consider speaking with a qualified mental-health professional or someone you trust.

---

# 📄 License

This project is open source.

If you plan to distribute or accept contributions, consider adding an appropriate license such as the **MIT License** through a `LICENSE` file.

---

# 👨‍💻 Author

### **Debdeep Choudhary**

**Final-year B.Tech — Mechanical Engineering**
**National Institute of Technology, Jamshedpur**

---

<p align="center">

⭐ If you found this project interesting, consider giving the repository a star!

</p>
