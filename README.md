# 📊 PhonePe Pulse Data Project

This project extracts, transforms, and visualizes financial and user data from the official PhonePe Pulse GitHub repository using Python, PostgreSQL, and Streamlit.

---

## 📁 Project Structure

```
phonepe-project/
├── data/                       # Raw JSON data (from PhonePe Pulse GitHub)
├── scripts/
│   └── main.py                # ETL script to load data into PostgreSQL
├── dashboard/
│   └── phonepe_dashboard.py   # Streamlit dashboard
├── requirements.txt
└── README.md
```

---

## 🏗️ Setup Instructions

### 1. ✅ Clone the Repository

```bash
https://github.com/your-username/phonepe-project.git
cd phonepe-project
```

### 2. 📦 Install Python Packages

```bash
pip install -r requirements.txt
```

### 3. 🐘 Set Up PostgreSQL

```sql
CREATE DATABASE phonepe_data;
```

Run the table creation SQL from documentation or ETL script to create these 9 tables:

* aggregated\_user
* aggregated\_transaction
* aggregated\_insurance
* map\_user
* map\_map
* top\_user
* top\_map
* map\_insurance (optional)
* top\_insurance (optional)

### 4. ⚙️ Configure Database Credentials

Edit the `DB_CONFIG` in `dashboard/phonepe_dashboard.py` and `scripts/main.py`:

```python
DB_CONFIG = {
  'host': 'localhost',
  'database': 'phonepe_data',
  'user': 'postgres',
  'password': 'your_password'
}
```

### 5. 🛠️ Run the ETL Script

```bash
python scripts/main.py
```

This will load JSON data from the `data/` folder into the PostgreSQL tables.

### 6. 🚀 Launch the Streamlit Dashboard

```bash
streamlit run dashboard/phonepe_dashboard.py
```

It will open at [http://localhost:8501](http://localhost:8501)

---

## 📊 Dashboard Features

* Filter by year and quarter
* View total transactions by state
* Visualize top districts by amount
* Explore insurance activity

---

## 📌 Notes

* Ensure your local data path matches the directory structure expected by the ETL script
* Some quarters or states may contain empty or null data (these are skipped)

---

## 🤝 Contributions

Feel free to fork, modify, and improve. Pull requests welcome!

---

## 🛡️ License

This project is built for learning and research purposes. Not affiliated with PhonePe or any financial entity.
