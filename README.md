
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

You: best football players of all time
Bot: Of course! This is one of the most passionate and enduring debates in all of sports. There is no single correct answer, as different eras, positions, and styles of play make direct comparisons difficult.

However, the conversation generally revolves around a few tiers of players. Here is a breakdown of the greatest football players of all time, organized to reflect the general consensus.

---

### The "Mount Rushmore": The Unquestionable Top Four

These four players are in a class of their own and are part of nearly every "greatest of all time" discussion. The order is hotly debated.

#### 1. Lionel Messi
*   **The Argument:** The most complete attacking player ever. Messi combines breathtaking dribbling, once-in-a-generation vision, and a goal-scoring record that rivals anyone in history. He is a master of the pass, the free-kick, and the solo run. His record **eight Ballon d'Or awards** are a testament to his sustained excellence. Finally winning the **FIFA World Cup** in 2022 cemented his legacy for many as the undisputed GOAT.
*   **Legacy:** Redefined what is possible for a forward, proving that intelligence and technical perfection can dominate over pure physical attributes.

#### 2. Pelé
*   **The Argument:** Football's first global superstar. Pelé was a phenomenal athlete with an incredible eye for goal, two strong feet, and surprising aerial ability. He is the only player in history to win **three FIFA World Cups**. His official goal tally is staggering, and his impact on popularizing the sport around the world is immeasurable.
*   **Legacy:** Known as "O Rei" (The King), he was the original benchmark for greatness.

#### 3. Diego Maradona
*   **The Argument:** The ultimate force of nature on a football pitch. Maradona's low center of gravity, combined with sublime dribbling, strength, and a magical left foot, made him virtually unstoppable. He single-handedly dragged an average Argentina team to **World Cup glory in 1986**, a feat many consider the greatest individual performance in tournament history. He also transformed Napoli from a provincial club into Italian champions.
*   **Legacy:** A flawed genius whose peak, though perhaps shorter than others, was arguably the highest the sport has ever seen.

#### 4. Cristiano Ronaldo
*   **The Argument:** The ultimate athlete and goal-scoring machine. Ronaldo transformed himself from a tricky winger into the most prolific forward in history. His dedication, aerial ability, ambidextrous shooting power, and knack for scoring in the biggest moments (especially in the Champions League) are legendary. He is the all-time leading goalscorer in men's international football and the UEFA Champions League.
*   **Legacy:** The model of professionalism and longevity, proving that relentless hard work can take a player to the absolute pinnacle of the sport.

---

### The "God Tier": Legends Who Challenge the Top Four

These players were so revolutionary and dominant that many fans argue they belong on the Mount Rushmore.

#### 5. Johan Cruyff
*   **The Argument:** The brain of "Total Football." Cruyff was not just a brilliant player known for his elegance, speed, and the iconic "Cruyff Turn," but he was also a tactical revolutionary. He saw the game in a way no one else did. His philosophy as a player and later as a manager laid the foundation for the modern game, most notably at Ajax and FC Barcelona.
*   **Legacy:** The most influential figure in football history; his ideas shaped generations of players and coaches.

#### 6. Franz Beckenbauer
*   **The Argument:** The greatest defender of all time. "Der Kaiser" (The Emperor) revolutionized the defender's role by inventing the modern *libero* (sweeper) position. He combined defensive intelligence and tackling with the grace and passing range of an elite midfielder, often striding out of defense to launch attacks. He won the World Cup as both a **player (1974)** and a **manager (1990)**.
*   **Legacy:** Proved that defenders could be the most elegant and influential players on the pitch.

#### 7. Zinedine Zidane
*   **The Argument:** The master of big games and pure elegance. "Zizou" was a midfield artist who played the game with a balletic grace. His first touch, vision, and control were unparalleled. He consistently delivered on the biggest stages, scoring two goals in the 1998 World Cup final and one of the greatest goals in history in the 2002 Champions League final.
*   **Legacy:** The symbol of class and clutch performance.

#### 8. Ronaldo Nazário
*   **The Argument:** The perfect striker. Before devastating knee injuries, "O Fenômeno" (The Phenomenon) was an unstoppable force of speed, power, and clinical finishing. He redefined the number 9 position. Even after his injuries, he reinvented himself to lead Brazil to a **World Cup victory in 2002**, winning the Golden Boot.
*   **Legacy:** At his peak, arguably the most explosive and terrifying forward the world has ever seen.

---

### The Pantheon of Greats (Honorable Mentions)

This is a list of other legends who are consistently ranked among the top 20-25 players ever.

*   **Alfredo Di Stéfano:** The engine of the legendary 1950s Real Madrid team that won five consecutive European Cups. A complete player who could defend, create, and score.
*   **Michel Platini:** A goal-scoring midfielder who won three consecutive Ballon d'Or awards in the 1980s.
*   **Garrincha:** The "Little Bird" whose mesmerizing dribbling skills helped Brazil win the 1958 and 1962 World Cups. Some in Brazil even rate him above Pelé.
*   **Paolo Maldini:** The ultimate one-club man and a defensive rock for AC Milan and Italy for over two decades. A model of consistency, longevity, and class.
*   **Xavi & Andrés Iniesta:** The midfield duo that defined Barcelona's and Spain's tiki-taka era, winning everything for club and country with their telepathic passing.
*   **Lev Yashin:** The "Black Spider," the only goalkeeper to ever win the Ballon d'Or. He was a revolutionary figure for his position.
*   **George Best:** A supremely talented and charismatic winger for Manchester United, often called "the fifth Beatle." A genius whose career was cut short by his off-field lifestyle.

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
