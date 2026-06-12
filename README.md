# Binance Futures Testnet Trading Bot

A Streamlit-based trading bot that connects to the Binance Futures Testnet and allows users to place Market, Limit, and Stop orders through a simple web interface.

## Features

* Connects to Binance Futures Testnet using API credentials
* Displays available trading symbols
* Shows real-time market prices
* Supports:

  * Market Orders
  * Limit Orders
  * Stop Orders
* Displays USDT account balance
* Maintains session-based order history
* Logs trading activity and errors
* Automatic Binance server time synchronization

---

## Project Structure

```
trading_bot/
│
├── app.py                 # Main Streamlit application
├── trading_bot.log        # Application logs (generated automatically)
├── requirements.txt       # Project dependencies
└── README.md
```

---

## Prerequisites

* Python 3.9+
* Binance Futures Testnet account
* Binance Testnet API Key and Secret

---

## Installation

### 1. Clone or Download the Project

```bash
git clone <repository-url>
cd trading_bot
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

Linux/Mac:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Example `requirements.txt`:

```txt
streamlit
python-binance
```

---

## Binance Testnet Setup

### Create a Testnet Account

Visit Binance Futures Testnet:

https://testnet.binancefuture.com

### Generate API Keys

1. Log in to Binance Futures Testnet.
2. Navigate to API Management.
3. Create a new API key.
4. Copy:

   * API Key
   * Secret Key

These credentials are required to connect the application.

---

## Running the Application

From the project directory:

```bash
streamlit run app.py
```

If the project is located elsewhere:

```bash
streamlit run "D:\Download-(D)\Code\Python\Internship\trading_bot\app.py"
```

The application will open automatically in your browser.

Default URL:

```text
http://localhost:8501
```

---

## How to Use

### Step 1: Enter API Credentials

In the sidebar:

* Enter Binance Testnet API Key
* Enter Binance Testnet Secret Key

After successful connection:

* Trading symbols are loaded
* USDT balance is displayed
* Real-time prices become available

### Step 2: Select a Trading Pair

Choose a symbol such as:

* BTCUSDT
* ETHUSDT
* BNBUSDT

### Step 3: Configure Order

Select:

* Order Type

  * MARKET
  * LIMIT
  * STOP

* Side

  * BUY
  * SELL

Enter:

* Quantity
* Price (for LIMIT orders)
* Price + Stop Price (for STOP orders)

### Step 4: Place Order

Click:

```text
Place Order
```

The application:

* Sends the order to Binance Futures Testnet
* Displays order confirmation
* Shows order details
* Stores order in session history

---

## Example Usage

### Example 1: Market Buy Order

Input:

```text
Symbol: BTCUSDT
Order Type: MARKET
Side: BUY
Quantity: 0.01
```

Result:

```text
Market Buy Order submitted immediately at current market price.
```

---

### Example 2: Limit Sell Order

Input:

```text
Symbol: ETHUSDT
Order Type: LIMIT
Side: SELL
Quantity: 0.05
Price: 4000
```

Result:

```text
Order remains open until market reaches specified price.
```

---

### Example 3: Stop Order

Input:

```text
Symbol: BTCUSDT
Order Type: STOP
Side: SELL
Quantity: 0.01
Price: 95000
Stop Price: 96000
```

Result:

```text
Order is triggered when stop price condition is met.
```

---

## Logging

Application logs are stored in:

```text
trading_bot.log
```

The log file contains:

* Connection events
* Order placement attempts
* API errors
* Validation errors
* System events

Example:

```text
2026-06-12 10:15:30 INFO API connected
2026-06-12 10:16:22 INFO Order placed successfully
```

---

## Assumptions

The application was developed with the following assumptions:

1. Users possess valid Binance Futures Testnet API credentials.

2. The Binance Futures Testnet service is available and reachable.

3. Users understand basic futures trading concepts.

4. Internet connectivity is stable while placing orders.

5. System time is reasonably synchronized with real time.

6. Orders are intended for testing only and not for live trading.

7. Session order history is temporary and resets when:

   * Browser refreshes
   * Streamlit server restarts
   * Session expires

8. Only USDT futures contracts are considered for balance display.

9. No database persistence is implemented.

10. No risk management features (stop-loss automation, position sizing, leverage controls) are included.

---

## Error Handling

The application handles:

* Invalid API credentials
* Binance API exceptions
* Invalid order parameters
* Connection failures
* Timestamp synchronization issues

Error messages are displayed directly in the UI and recorded in the log file.

---

## Future Improvements

* Persistent database storage
* Position monitoring dashboard
* PnL tracking
* Advanced order types
* Leverage controls
* Risk management module
* Real-time WebSocket price updates
* Trade analytics and reporting

---

## Disclaimer

This project is intended for educational and testing purposes only.

All orders are placed on Binance Futures Testnet. No real funds are involved.

Users are responsible for understanding futures trading risks before deploying similar functionality in a live environment.
