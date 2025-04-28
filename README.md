
# 📧 Smart Email Assistant with Spring Boot, Spring AI & Gemini

An AI-powered Smart Email Assistant that helps users manage their Gmail inbox intelligently. It reads email content via a Chrome Extension and uses Gemini (Google's LLM) via Spring AI to summarize, classify, and generate smart replies.
<img src="https://github.com/arjunraj79/AI-Email-Assistant/blob/main/spring.png">

---

## 🚀 Features

- 🧠 AI-generated summaries of Gmail threads
- ✍️ Context-aware reply suggestions using Gemini
- 📬 Chrome Extension to interact with Gmail content
- 🔌 REST API built with Spring Boot & Spring AI
  
---

## 🧰 Tech Stack

### Backend
- **Spring Boot**
- **Spring AI**
- **Gemini API** (via Spring AI)
- **REST APIs**
- **Spring Web + Optional Spring Security**

### Frontend / Extension
- **Chrome Extension**
- Interacts with Gmail DOM
- Sends email body data to backend via HTTP

---

## 🧠 Architecture Overview

```
Gmail Email ➝ Chrome Extension ➝ Spring Boot API ➝ Gemini via Spring AI ➝ Smart Response/Summary ➝ Back to Gmail UI
```

---

## 🧪 Example Use Cases

- ✨ Generate polite, professional, or casual responses automatically
- 🔍 Extract key information from email bodies

---

## 🛠 Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/arjunraj79/AI-Email-Assistant.git
cd AI-Email-Assistant
```

### 2. Backend Setup (Spring Boot)

#### Run the backend

```bash
./mvnw spring-boot:run
```

API will run at `http://localhost:8080`.

---

### 3. Chrome Extension Setup

- Navigate to `chrome-extension/` directory (if in your repo)
- Open Chrome and go to `chrome://extensions`
- Enable **Developer Mode**
- Click **Load Unpacked** and select the `chrome-extension/` folder - email-writer-ext
- The extension will now be visible in your toolbar

---

### 4. How It Works

- The extension reads the email body from Gmail’s DOM
- It sends the text to your Spring Boot backend
- Spring AI uses Gemini to process the input and return a result (summary/reply)
- The result is shown in the Gmail UI (via extension popup or injected UI)

---

## 🔁 Example API (Spring Boot)

- Configure the api key in postman and check the working
- Then you can run the backend and on postman configure the url to route to the backend and post a request.


### `POST  http://localhost:8080/api/email/generate`

```json
{
  "emailBody": "Hi John, just following up on our previous discussion..."
}
```

**Response:**

```json
{
  "summary": "Follow-up on previous discussion with John regarding..."
}
```

---

## 🙌 Acknowledgements

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring AI](https://docs.spring.io/spring-ai)
- [Gemini API](https://ai.google.dev/)
- [Google Chrome Extensions](https://developer.chrome.com/docs/extensions/)
