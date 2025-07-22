
# Gemini Chatbot using LangChain

This is a simple terminal-based chatbot that uses **LangChain** and **Gemini Pro 2.5** from Google AI. It allows users to interact with a powerful LLM through the command line.

## 💡 Features

- Built using [LangChain](https://python.langchain.com/)
- Uses [Gemini 2.5 Pro](https://ai.google.dev/)
- Simple CLI interface
- Graceful exit using `exit` or `quit`

---

## 🚀 Installation

1. **Clone this repository** (or create a new Python file and copy the code).
2. **Install dependencies:**

```bash
pip install -qU langchain langchain-google-genai
```

---

## 🔑 Setup API Key

You'll need a Google API key with access to Gemini:

1. Visit: [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Generate your API key.
3. When you run the script, paste your key when prompted.

---

## 🧠 Usage

Run the Python script:

```bash
python chatbot.py
```

Example terminal interaction:

```plaintext
Enter your Google Gemini API key: **************
Chatbot ready! Type your message below. Type 'exit' or 'quit' to stop.

You: Hello!
Bot: Hi there! How can I assist you today?

You: exit
Goodbye!
```

---

## 🧩 Code Overview

```python
import os
import getpass
from langchain_google_genai import ChatGoogleGenerativeAI

os.environ["GOOGLE_API_KEY"] = getpass.getpass("Enter your Google Gemini API key: ")

llm = ChatGoogleGenerativeAI(model="gemini-2.5-pro", temperature=0.3)

print("\nChatbot ready! Type your message below. Type 'exit' or 'quit' to stop.\n")

while True:
    user_input = input("You: ").strip()
    if user_input.lower() in {"exit", "quit"}:
        print("Goodbye!")
        break
    try:
        response = llm.invoke(user_input)
        print("Bot:", response.content.strip())
    except Exception as e:
        print("Error while communicating with Gemini:", str(e))
        break
```

---

## 📄 License

This project is licensed under the MIT License. Feel free to use, modify, and share.

---

## ✨ Author

Developed by [YourName]  
GitHub: [https://github.com/Kartiksharma1234](https://github.com/Kartiksharma1234)
