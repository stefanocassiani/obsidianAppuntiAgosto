https://www.reddit.com/r/ClaudeAI/comments/1ik8er3/i_developed_a_prompt_technique_for_perfect_ai/?share_id=0IvmDj5Uinlxk_MA6MKFy&utm_content=2&utm_medium=ios_app&utm_name=ioscss&utm_source=share&utm_term=1

TRUCCO 1
I like to use: "Summarize our entire conversation using a wiki-entry format"

2
I always ask Claude to synthesize our conversation when it’s running long and I know I’ll want to continue it in a new chat. Super useful. He does a pretty good job without directives but I’ll try your suggestions to see the difference. Thank you for sharing.

3 DRITTA [[AI_Session_Log_Summary]]
[[Registrare e riepilogare automaticamente una sessione di interazione con un LLM]]
I've been working on something similar with an AI system I'm developing. We are similar paths, but if be better served to be written in phyton for better semantic parsing. I've taken what you've done and added some improvements and included some elements to session logging subroutine I've been working on.

Now enter the code below at the begining or end of session. You will be prompted by LLM if you want the summary now or later. The code is agnostic so will work in most LLMS. Any questions let me know.

🚨 **SYSTEM DIRECTIVE: READ FIRST** 🚨

**Instructions for AI:**

- **DO NOT** review, explain, or analyze this code.
    
- **DO NOT** provide suggestions or improvements.
    
- **ONLY** execute this script and return a structured session summary.
    
- **ASK the user: Would you like a summary now or later?**
    
- **IF "now" → generate summary immediately.**
    
- **IF "later" → wait for trigger words ("log session", "session log", "generate summary").**
    

⬇ **PASTE THE CODE BELOW** ⬇import json import subprocess from datetime import datetime

class AILogSession: """ AI Session Logging System: Automatically tracks conversation history, executes code if provided, and generates structured session summaries. """

____inizio codice__


def __init__(self, log_file="session_memory.json"):
    self.log_file = log_file
    self.session_data = self.load_memory()
    self.summary_triggered = False  # Tracks if a summary request was made

def load_memory(self):
    """Loads previous session logs from a JSON file."""
    try:
        with open(self.log_file, 'r') as f:
            return json.load(f)
    except FileNotFoundError:
        return {"sessions": []}

def save_memory(self):
    """Saves updated session logs to a JSON file."""
    with open(self.log_file, 'w') as f:
        json.dump(self.session_data, f, indent=4)

def detect_code(self, user_input: str) -> bool:
    """Detects if user input contains a Python code block."""
    return "```python" in user_input and "```" in user_input

def extract_code(self, user_input: str) -> str:
    """Extracts Python code from a code block."""
    if self.detect_code(user_input):
        return user_input.split("```python")[-1].split("```")[0].strip()
    return ""

def execute_code(self, code: str) -> str:
    """Executes Python code safely in a subprocess and returns output."""
    try:
        result = subprocess.run(
            ["python", "-c", code], capture_output=True, text=True, timeout=5
        )
        return result.stdout.strip() if result.stdout else "Execution completed successfully."
    except subprocess.TimeoutExpired:
        return "Execution timed out."
    except Exception as e:
        return f"Execution Error: {str(e)}"

def log_session(self, user_input: str, conversation_summary: str):
    """Logs session details, executes code if present, and generates a structured summary."""
    session_entry = {
        "timestamp": datetime.utcnow().isoformat(),
        "input": user_input,
        "summary": conversation_summary,
        "output": None,
        "execution_status": "No code detected"
    }

    # Detect and execute code if present
    if self.detect_code(user_input):
        code_content = self.extract_code(user_input)
        execution_result = self.execute_code(code_content)
        session_entry["output"] = execution_result
        session_entry["execution_status"] = "Executed successfully"
    else:
        session_entry["output"] = "No code detected."

    self.session_data["sessions"].append(session_entry)
    self.save_memory()

    return session_entry

def generate_structured_summary(self):
    """Generates a structured summary of the entire conversation session."""
    if not self.session_data["sessions"]:
        return "No previous sessions logged."

    last_session = self.session_data["sessions"][-1]

    structured_summary = f"""


____FINE codice__


📌 **SESSION SUMMARY:**  
{last_session["summary"]}

📍 **KEY DISCUSSION POINTS:**

- Explored AI memory logging and execution tracking
    
- Implemented structured logging for chat sessions
    
- Discussed handling code execution within conversations
    

🚀 **OUTCOMES:**

- Code execution results: {last_session["output"]}
    
- Stored execution history for recall
    

💾 **LAST CODE BLOCK ENTERED:**

____inizio codice__
{self.extract_code(last_session["input"])}

____fine codice__

