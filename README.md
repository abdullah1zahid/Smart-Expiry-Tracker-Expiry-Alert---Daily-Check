# Smart Expiry Tracker + Expiry Alert

An AI-powered automation system built with **n8n** and **OpenAI Vision** to track and manage expiry dates of medicines and household items automatically. No manual data entry is required—just take a photo, and the system handles the rest.

## 📺 Demo Video
Watch the system in action here:  
[Watch the Demo Video](https://drive.google.com/file/d/1-LFLjEAXywSUzd0Fh4q5QVqrSOm1JJfj/view?usp=drive_link)

## 📸 Workflow Architecture
![Workflow Image](Smart%20Expiry%20Tracker%20+%20Expiry%20Alert%20-%20Daily%20Check.PNG)

## 🚀 Features
* **AI Data Entry:** Extracts product names and expiry dates from photos using OpenAI's Vision model.
* **Automated Database:** Automatically logs entries into a Google Sheet.
* **Smart Filtering:** Validates data and identifies expiring or expired items.
* **Daily Monitoring:** A scheduled cron job scans the inventory every morning.
* **Instant Telegram Alerts:** Sends real-time notifications to your mobile phone with status labels (EXPIRED / EXPIRING SOON).

## 🛠️ Technical Stack
* **n8n:** Workflow automation platform self-hosted on a Hostinger VPS.
* **OpenAI Vision:** For image analysis and data extraction.
* **Google Sheets:** Used as a lightweight database.
* **Telegram Bot API:** For receiving images and sending alerts.
* **JavaScript:** Used in Code nodes for image formatting (Base64) and conditional messaging.

## ⚙️ How It Works

### 1. Inventory Entry System
* The **Telegram Bot** receives a photo.
* The system downloads the image and converts it to **Base64** format via a custom Code node.
* **OpenAI Vision** processes the image to extract the `item_name` and `expiry_date`.
* Data is saved to the **Google Sheet** inventory.

### 2. Daily Alert System
* A **Schedule Trigger** runs every morning at a set time.
* The system fetches all items from the database.
* A **Filter Node** compares the `expiry_date` with the current date.
* A **Telegram Alert** is sent with a professional status report.

## 📝 Configuration
To use this workflow, ensure you have:
1.  An **n8n** instance.
2.  An **OpenAI API Key**.
3.  A **Telegram Bot Token** and your `chat_id`.
4.  A **Google Cloud Console** project for Sheets API access.

---

**Developer:** Abdullah Zahid  
