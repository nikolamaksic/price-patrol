# 🛒 Price Patrol

**Track grocery prices across Serbian online stores.**

---

## 📌 About

**Price Patrol** is a tool that helps users track and compare grocery prices from various online stores in Serbia. The goal is to make it easier for people to save money by seeing where specific products are cheapest — and how their prices change over time.

---

## 🎯 What It Does

- Let users track products from Serbian stores (e.g. IDEA, Lidl, Maxi)
- Scrape prices periodically and show price history
- Provide a dashboard for viewing tracked items

---

## ⚙️ Tech Overview

| Tech      | Role                            |
|-----------|---------------------------------|
| Django    | Web app, admin panel, data models |
| Python    | Scraping logic (async + threaded) |
| PostgreSQL| Data storage                     |

---

## 🚧 TODO – Development Plan

### 📁 Base Setup
- [ ] Set up Django project
- [ ] Create models: `Product`, `Store`, `TrackedItem`, `PriceSnapshot`
- [ ] Basic user system: signup/login

### 🕸 Scraping
- [ ] Build a basic scraper
- [ ] Add site support:
  - [ ] IDEA
  - [ ] Maxi
  - [ ] Lidl
- [ ] Store prices in DB + cache recent ones in Redis

### 🔄 Background Jobs
- [ ] Set up task system (e.g. Celery or periodic Django command)
- [ ] Automatically run scrapers every 6–12 hours

### 📊 User Dashboard
- [ ] List tracked products
- [ ] Show latest prices and change indicators
- [ ] Chart price history (with Chart.js or simple SVG)

### 💌 Alerts (optional)
- [ ] Allow email alerts for price drops

---

## 🧰 Running Locally

```bash
git clone https://github.com/yourusername/price-patrol
cd price-patrol

# Setup Python environment
python -m venv env
source env/bin/activate  # or .\env\Scripts\activate on Windows

pip install -r requirements.txt

# Run database migrations
python manage.py migrate

# Start the server
python manage.py runserver
