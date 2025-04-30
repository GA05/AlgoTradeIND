# **AlgoTradeIND**

**AlgoTradeIND** is a real-time stock trading web application that delivers **live price updates** using WebSockets and provides **automated trading signals** based on technical indicators. It supports both **NASDAQ (US)** and **Nifty Fifty (India)** markets, with signal logic tailored to each market’s trading hours.

---

## **Features**

- 🔄 **Real-Time Stock Prices**: Leverages `yliveticker` WebSockets for live market data.
- 📊 **Automated Signal Generation**: Analyzes the last 60 days of stock data via `yfinance` to produce buy/sell signals.
- 🎯 **Paper Trading**: Simulate trading using real-time signals without risking actual capital.
- 💻 **Modern UI**: Built with locally installed **TailwindCSS** for a sleek and responsive interface.

---

## **Usage Notes**

- You can use the **live pricing** and **trading signals** without setting up the database.
- To enable full **paper trading** functionality, including user accounts and admin access, you'll need to complete the database and admin setup.

---

## **Getting Started**

### **1. Clone the Repository**
```bash
git clone https://github.com/nestcub/AlgoTradeIND.git
cd AlgoTradeIND
```

### **2. Set Up Python Virtual Environment**

Create and activate a virtual environment:
```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

Install the required dependencies:
```bash
pip install -r requirements.txt
```

---

### **3. (Optional) Set Up SQLite Database for Admin & Paper Trading**

If you want to use the admin panel and simulate trades:

```bash
python manage.py makemigrations
python manage.py migrate
```

Create a Django superuser:
```bash
python manage.py createsuperuser
```

Provide the username, email, and password as prompted.

---

### **4. Set Up TailwindCSS**

Open a **new terminal** in the project root and run:

```bash
npm install
```

Then start the Tailwind build process:

```bash
npm run dev
```

This will generate the necessary CSS for your frontend.

---

### **5. Run the Django Server**

In your original terminal (with the virtual environment activated), start the server:

```bash
python manage.py runserver
```

---

### **6. (Optional) Access the Admin Panel**

If you created a superuser in Step 3:

1. Navigate to:  
   ```
   http://127.0.0.1:8000/admin/
   ```
2. Log in using your superuser credentials.
3. Create a new user and add them to the `accounts`.

---

### **7. (Optional) Update `views.py` for Paper Trading**

In `views.py`, update the dummy user reference to match the username you created in the admin panel.  
This line appears **twice**—update both:

```python
dummy_user = User.objects.get(username='your_username')
```

Replace `'your_username'` with the actual username you set up.

---

## **Tech Stack**

- **Backend**: Django, WebSockets (`yliveticker`), `yfinance`
- **Frontend**: Django Templates, TailwindCSS
- **Database**: SQLite (default), PostgreSQL (optional)

---

## **Contributing**

We welcome contributions from the community! Here's how to get started:

1. Fork the repository.
2. Create a new branch:  
   ```bash
   git checkout -b feature-branch
   ```
3. Commit your changes.
4. Open a pull request on GitHub.