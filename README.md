# 🩺 AI Health Bot

> An intelligent conversational health assistant powered by AI — providing symptom analysis, health guidance, and wellness support through a clean, Flask-based web interface.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.x-000000?style=flat-square&logo=flask&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37726?style=flat-square&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [How It Works](#-how-it-works)
- [Usage](#-usage)
- [Configuration](#-configuration)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)
- [Author](#-author)
- [License](#-license)

---

## 🌟 Overview

**AI Health Bot** is a web-based conversational assistant designed to make basic health guidance more accessible. Users can describe symptoms, ask wellness questions, and receive informational responses powered by an AI model — all through a simple, intuitive chat interface.

This project is built with **Python** and **Flask** on the backend, with a lightweight frontend served directly by the web server. The AI model is developed and experimented with using **Jupyter Notebooks**, making it easy to iterate on and improve the model over time.

> ⚠️ **Important:** This bot is for informational purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider for medical concerns.

---

## ✨ Features

- 💬 **Conversational Interface** — Chat naturally with the bot to describe symptoms or ask health questions
- 🔍 **Symptom Analysis** — Understands natural language descriptions and provides relevant health information
- 🌐 **Web-Based** — Accessible from any browser, no installation required for end users
- 📓 **Notebook-Driven Model** — AI model developed and documented in Jupyter Notebooks for full transparency
- 🗄️ **Session Storage** — Conversation history stored locally using SQLite via the `instance/` directory
- 🛡️ **Safety-First Design** — Always reminds users to consult professionals for real medical concerns
- ⚡ **Lightweight & Fast** — Minimal dependencies, quick to set up and run locally

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.9+, Flask |
| AI / ML | Python (scikit-learn / NLP), Jupyter Notebook |
| Database | SQLite (via Flask's `instance/` folder) |
| Frontend | HTML, CSS |
| Low-level Extensions | C, Cython (compiled components) |

---

## 📁 Project Structure

```
AI-Health-Bot/
│
├── flask/                  # Core Flask web application
│   ├── app.py              # Main application entry point
│   ├── routes/             # URL routing and request handlers
│   ├── templates/          # HTML templates for the chat UI
│   ├── static/             # CSS, JS, and other static assets
│   └── model/              # AI model integration and inference logic
│
├── instance/               # Instance-specific config and SQLite database
│   └── health_bot.db       # Local SQLite database (auto-generated)
│
├── *.ipynb                 # Jupyter Notebooks for model development & training
│
└── README.md               # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed on your machine:

- **Python 3.9+** — [Download here](https://www.python.org/downloads/)
- **pip** — comes bundled with Python
- **Git** — [Download here](https://git-scm.com/)

Optionally, for exploring the notebooks:
- **Jupyter Notebook** or **JupyterLab**

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/Shakyadeep-Panda/AI-Health-Bot.git
cd AI-Health-Bot
```

**2. Create and activate a virtual environment** (recommended)

```bash
# Create virtual environment
python -m venv venv

# Activate — macOS/Linux
source venv/bin/activate

# Activate — Windows
venv\Scripts\activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

> If a `requirements.txt` is not yet present, install the core packages manually:
> ```bash
> pip install flask
> ```

### Running the App

```bash
cd flask
python app.py
```

Then open your browser and navigate to:

```
http://localhost:5000
```

You should see the AI Health Bot chat interface ready to use.

---

## 🧠 How It Works

```
User Input (Browser)
       │
       ▼
Flask Web Server (app.py)
       │
       ├── Processes the text input
       ├── Passes query to the AI model
       │
       ▼
AI / NLP Model
       │
       ├── Tokenizes and classifies the input
       ├── Matches against health intents/entities
       │
       ▼
Response Generation
       │
       ├── Returns informational health response
       ├── Appends safety disclaimer when appropriate
       │
       ▼
Chat UI (Browser) ← Rendered response displayed to user
```

The model is trained and documented inside Jupyter Notebooks. The trained model artifacts are loaded by the Flask app at startup and used for real-time inference during conversations.

---

## 💡 Usage

Once the app is running, you can interact with the bot by typing messages like:

- `"I have a headache and feel tired — what could this be?"`
- `"What are the symptoms of the flu?"`
- `"How much water should I drink per day?"`
- `"I have a sore throat and mild fever since yesterday"`

The bot will respond with relevant health information and, where appropriate, advise consulting a healthcare professional.

---

## ⚙️ Configuration

The `instance/` folder holds Flask's instance configuration and the local SQLite database. You can customize app behavior by modifying the Flask config inside `app.py`:

```python
app.config['SECRET_KEY'] = 'your-secret-key-here'
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///health_bot.db'
app.config['DEBUG'] = True  # Set to False in production
```

---

## 🗺️ Roadmap

- [x] Basic conversational interface
- [x] Symptom-based response system
- [x] Flask web app with SQLite storage
- [ ] Improve NLP model accuracy with larger training dataset
- [ ] Add multi-turn conversation memory
- [ ] Deploy to cloud (Render / Railway / Heroku)
- [ ] Add user authentication and chat history
- [ ] Mobile-responsive UI improvements
- [ ] REST API endpoint for third-party integrations
- [ ] Add support for regional languages (e.g., Odia, Hindi)

---

## 🤝 Contributing

Contributions are welcome! Here's how to get involved:

1. **Fork** the repository
2. **Create** a new branch: `git checkout -b feature/your-feature-name`
3. **Make** your changes and commit: `git commit -m "Add: your feature description"`
4. **Push** to your branch: `git push origin feature/your-feature-name`
5. **Open** a Pull Request

Please make sure your code follows consistent style and includes comments where necessary.

---

## ⚠️ Disclaimer

This project is intended **for educational and informational purposes only**.

The AI Health Bot does **not** provide medical diagnoses, prescriptions, or professional medical advice. The information provided should **never** replace consultation with a licensed medical professional. If you are experiencing a medical emergency, please call your local emergency services immediately.

---

## 👤 Author

**Shakyadeep Panda**

- GitHub: [@Shakyadeep-Panda](https://github.com/Shakyadeep-Panda)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">
  <sub>Built with ❤️ by Shakyadeep Panda</sub>
</div>
