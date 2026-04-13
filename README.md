# 🧠 PersonaForge- A Multi-Agent LLM System for Intelligent Interaction

PersonaForge is a multi-agent AI system that acts as a **digital persona of Nikith Gokul**, intelligently answering questions based on real-world experience, skills, education, and projects.

It combines **LLM generation + evaluation + refinement** to produce high-quality, professional, and context-aware responses.
---
## 📸 Screenshots
![WhatsApp Image 2026-04-13 at 16 34 04](https://github.com/user-attachments/assets/ff42e1bd-cabf-488f-a9fe-b1659d7832e8)

---

## 🚀 Features

* 🤖 **Persona-based AI Assistant**
  Responds in first-person as *Nikith Gokul* using real data (resume + LinkedIn)

* 🧩 **Multi-Agent Architecture**

  * Generator Agent → creates response
  * Evaluator Agent → critiques response
  * Decision Layer → improves or approves output

* 🧠 **Context-Aware Conversations**
  Maintains chat history for coherent interactions

* 📄 **Knowledge Ingestion**

  * PDF parsing (LinkedIn profile)
  * Text-based summary

* 🔁 **Self-Improving Responses**
  Uses evaluator feedback to refine answers automatically

* 🚨 **Out-of-Scope Detection + Alerts (Pushover Integration)**

  * Detects when a query is outside persona knowledge
  * Responds gracefully: *"I currently don’t have the information regarding your query"*
  * Sends a **real-time notification to Nikith Gokul** with the user query via Pushover

* 📢 **Pushover Notifications Integration**
  Send real-time alerts for important events and edge cases

* 🌐 **Interactive UI with Gradio**
  Clean and simple chat interface with shareable public link

---

## 🏗️ Architecture

```
User Input
   ↓
Generator Agent (Gemini)
   ↓
Evaluator Agent (Gemini)
   ↓
Decision Logic (Improve / Approve)
   ↓
Final Response
```

---

## 🛠️ Tech Stack

* **LLM**: Google Gemini (gemini-flash)
* **Languages**: Python 3.12
* **Frameworks/Libraries**:

  * Gradio
  * Requests
  * PyPDF
  * python-dotenv
* **Notifications**: Pushover API

---

## 📂 Project Structure

```
PersonaForge/
│
├── Experiments/
│   ├── trails_Llama3.2_phi3.ipynb      # LLaMA 3.2 & Phi-3 experiments
│   ├── trials_llama3.2_GradioUI.ipynb  # Gradio UI experiments
│
├── me/
│   ├── Profile.pdf                    # LinkedIn export
│   └── summary.txt                    # Professional summary
│
├── Project_gemini_flash_Gradio_Pushover.ipynb  # Main implementation (Gradio launched here)
├── requirements.txt
├── README.md
└── LICENSE
```

PersonaForge/
│
├── me/
│   ├── Profile.pdf          # LinkedIn export
│   └── summary.txt          # Professional summary
│
├── experiments/             # Experimental models
│   ├── llama3.2/            # Trials using LLaMA 3.2
│   └── phi3/                # Trials using Phi-3
│
├── app.py / notebook        # Main implementation
├── .env                     # API keys
└── README.md

````

---

## ⚙️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/PersonaForge-A-Multi-Agent-LLM-System-for-Intelligent-Interaction.git
cd PersonaForge-A-Multi-Agent-LLM-System-for-Intelligent-Interaction
````

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file:

```
GOOGLE_API_KEY=your_gemini_api_key
PUSHOVER_API_TOKEN=your_token
PUSHOVER_USER_KEY=your_user_key
```

### 5. Run the Application

Since this project is implemented in a Jupyter Notebook, you can launch the app directly from the final cell.

```bash
jupyter notebook
```

* Open `code.ipynb`
* Run all cells
* The final cell launches a **Gradio interface**
* A **public shareable link** will be generated automatically

Example output:

```
Running on local URL:  http://127.0.0.1:7863
Running on public URL: https://xxxxx.gradio.live
```

You can use the public URL to access and share your AI persona.

```bash
python app.py
```

---

## 🧠 How It Works

1. **Generator Agent** creates a response based on:

   * System prompt (persona definition)
   * Resume + LinkedIn data
   * Chat history

2. **Evaluator Agent** analyzes:

   * Clarity
   * Correctness
   * Professionalism
   * Scope relevance

3. **Out-of-Scope Detection**:

   * If query is outside persona knowledge:

     * Chatbot responds the information requested is out of the context and a pushover notification will be sent to Nikith Gokul
     * Trigger **Pushover notification** with user query

4. **Decision Engine**:

   * Accepts response OR
   * Replaces with improved version

5. **Response Cleaning** removes duplicates

---

## 🧪 Experiments

The `experiments/` folder contains trials with alternative LLMs:

* **LLaMA 3.2** → for local / open-source experimentation
* **Phi-3** → for lightweight inference testing

These experiments were conducted to compare:

* Response quality
* Latency
* Cost efficiency
* Local vs API-based performance

---

## 🎯 Use Case

PersonaForge acts as a **personal AI representative**, capable of:

* Answering interview questions
* Explaining projects and experience
* Showcasing technical expertise
* Acting as a portfolio chatbot
* Escalating unknown queries to the real user via notifications

---

## 🔮 Future Improvements

* Add memory persistence (vector DB)
* Deploy on cloud (AWS / Hugging Face Spaces)
* Add voice interface
* Fine-tune evaluator scoring
* Multi-persona support

---

## 👨‍💻 Author

**Nikith Gokul**
AI & Cloud Engineer

---

## ⭐ Contribute / Support

If you found this project useful:

* ⭐ Star the repo
* 🍴 Fork and experiment
* 🧠 Share feedback

---

## 📜 License

This project is open-source and available under the MIT License.
