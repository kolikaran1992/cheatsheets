# 📌 **CHEAT SHEET: How Stock Prices Are Decided + Which Order to Use**



## 🧩 **1) How Prices Are Formed**

Prices come from the **order book**, made of:

* **Bids** → buyers’ limit orders
* **Asks** → sellers’ limit orders
* **Market orders** → instant trades that consume bids/asks

A trade happens when **bid ≥ ask**.

**LTP = price of the most recent trade (NOT the current buy/sell price).**



## 🧩 **2) Order Book Example (10:00 AM)**

### **BIDS (buyers — highest first)**

```
₹99.50   (best bid)
₹99.00
₹98.75
```

### **ASKS (sellers — lowest first)**

```
₹100.20  (best ask)
₹100.50
₹100.75
```

**Buy instantly = ₹100.20** **Sell instantly = ₹99.50**



# 🕒 **3) How Prices Move — Two Quick Examples**

## ✔️ Example 1: A Market Buy (40 shares) arrives

Consumes best ask ₹100.20 → removed from the book.

### New order book:

**ASKS:**

```
₹100.50  (new best ask)
₹100.75
```

**LTP = ₹100.20**



## ✔️ Example 2: A Limit Sell at ₹99.50 appears

Matches the best bid instantly → trade happens at ₹99.50.

### New order book:

**BIDS:**

```
₹99.00  (new best bid)
₹98.75
```

**LTP = ₹99.50**



# 📌 **4) What Actually Moves the Market**

* New **limit orders** → shift bids/asks
* **Market orders** → consume bids/asks → new LTP
* Big orders → eat multiple price levels → big jumps
* Many people doing this constantly → price keeps moving



# 🟩 **5) Which Order Type Should YOU Use as a Beginner?**

### ✔️ **ETFs (Nifty 50, Nifty Next 50, Midcap 150, S&P 500, Nasdaq)**

* **Use MARKET ORDER**
* These are *very liquid* → tiny spreads
* Your fill will be safe and close to shown price



### ✔️ **Large, High-Volume Stocks (Reliance, HDFC Bank, Infosys)**

* **Market order is usually safe**
* OR
* **Limit order slightly above bid** if volatility is high



### ✔️ **Small-Cap or Low-Liquidity Stocks**

* **Always use LIMIT ORDER**
* Spreads are wide → market order can give terrible fills
* Protect your price



### ✔️ **During Volatile Events (budget, earnings, panic days)**

* **Use LIMIT ORDER**
* Market orders can slip badly when price is moving fast



# ⭐ **One-Line Memory Shortcut**

* **Liquid ETFs → Market**
* **Large caps → Market or gentle limit**
* **Small caps → Limit only**
* **Volatile times → Limit only**

---