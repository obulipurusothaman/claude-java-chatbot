# Claude AI CLI Chatbot — Java

A simple, open source end-to-end Java project that connects to the **Anthropic Claude API** and lets you have a multi-turn conversation in your terminal.

---

## 📁 Project Structure

```
claude-java-chatbot/
├── pom.xml                          # Maven build file
└── src/
    ├── main/java/com/claudeai/
    │   ├── config/
    │   │   └── ClaudeConfig.java    # API key, model, system prompt
    │   ├── model/
    │   │   ├── Message.java         # Single chat message (role + content)
    │   │   └── Conversation.java    # Multi-turn history manager
    │   ├── service/
    │   │   └── ClaudeApiService.java # HTTP client — calls Anthropic API
    │   └── cli/
    │       └── ChatbotApp.java      # Main entry point / REPL loop
    └── test/java/com/claudeai/
        └── model/
            └── ConversationTest.java
```

---

## ✅ Prerequisites

- Java 17+
- Maven 3.8+
- An Anthropic API key → https://console.anthropic.com/

---

## ⚙️ Setup

### 1. Clone the repo
```bash
git clone https://github.com/your-username/claude-java-chatbot.git
cd claude-java-chatbot
```

### 2. Set your API key
```bash
# Linux / macOS
export ANTHROPIC_API_KEY=sk-ant-...

# Windows
set ANTHROPIC_API_KEY=sk-ant-...
```

### 3. Build
```bash
mvn clean package -q
```

### 4. Run
```bash
java -jar target/claude-chatbot.jar
```

---

## 💬 Usage

```
╔══════════════════════════════════════════════╗
║       Claude AI CLI Chatbot  (Java)          ║
║       Powered by Anthropic API               ║
╚══════════════════════════════════════════════╝

You: What is the capital of France?
Claude: The capital of France is Paris.

You: And what's the population?
Claude: Paris has a population of about 2.1 million in the city...
```

### Commands
| Command    | Description                      |
|------------|----------------------------------|
| `/history` | Print full conversation history  |
| `/clear`   | Start a new conversation         |
| `/help`    | Show available commands          |
| `/quit`    | Exit the chatbot                 |

---

## 🔧 Configuration

Edit `ClaudeConfig.java` to change:

| Setting            | Default                       | Description              |
|--------------------|-------------------------------|--------------------------|
| `DEFAULT_MODEL`    | `claude-sonnet-4-20250514`    | Claude model to use      |
| `DEFAULT_MAX_TOKENS` | `1024`                      | Max response length      |
| `SYSTEM_PROMPT`    | "helpful friendly assistant"  | Claude's behaviour       |

---

## 📦 Dependencies

| Library   | Version  | Purpose           |
|-----------|----------|-------------------|
| OkHttp    | 4.12.0   | HTTP client       |
| Gson      | 2.10.1   | JSON parsing      |
| SLF4J     | 2.0.9    | Logging           |
| JUnit 5   | 5.10.0   | Unit tests        |

---

## 🧪 Run Tests
```bash
mvn test
```

---

## 📚 API Reference
- Anthropic Messages API: https://docs.anthropic.com/en/api/messages
- Claude Models: https://docs.anthropic.com/en/docs/about-claude/models/overview

---

## 📄 License
MIT License — free to use, modify, and distribute.

