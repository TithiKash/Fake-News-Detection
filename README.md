#  Fake News Detection System

An AI-powered fake news detection workflow built using 
n8n, Groq API, and a Structured Output Parser that 
automatically verifies news headlines and returns a 
verdict with confidence score and reasoning.

---

##  Tools & Technologies
- **n8n** — Visual workflow automation engine
- **Groq API (Groq Chat Model)** — LLM inference
- **JavaScript** — Custom logic nodes
- **Structured Output Parser** — Structured JSON response
- **Search Node** — Real-time web search for verification

---

##  Features
- Accepts any news headline as input
- Searches the web for supporting/contradicting evidence
- AI Agent analyzes credibility using Groq LLM
- Returns structured output:
  - ✅ `headline` — The news claim being checked
  - ✅ `verdict` — True or False
  - ✅ `confidence` — Confidence score (0–1)
  - ✅ `reason` — Explanation of the verdict
- Executes in under **4 seconds** per query
- Uses only **626 tokens** per execution (cost efficient)

---

##  Screenshots

### Full Workflow Diagram
![Workflow]<img width="1905" height="908" alt="Fake News Detection" src="https://github.com/user-attachments/assets/9e6a1296-76db-49e6-83a3-7ba3172e2489" />


### Sample Output
**Input headline:**
> "False Claim: NASA Confirms Humans Landed on Mars Yesterday"

**AI Output:**
```json
{
  "headline": "False Claim: NASA Confirms Humans Landed on Mars Yesterday",
  "verdict": false,
  "confidence": 0,
  "reason": "There is no credible evidence or official..."
}
```

---

##  How It Works
User Input (Headline)
↓
Edit Fields Node → Formats the input
↓
Search Node → Searches web for evidence
↓
Code in JavaScript → Processes search results
↓
AI Agent (Groq LLM) → Analyzes credibility
↓
Structured Output → Returns verdict + reason
Parser
↓
Code in JavaScript → Final formatting
↓
Output: verdict, confidence, reason


---

## 📊 Sample Results

| Headline | Verdict | Confidence |
|----------|---------|------------|
| NASA Confirms Humans Landed on Mars Yesterday | ❌ False | 0 |
| Earth revolves around the Sun | ✅ True | 1 |

---

## ⚙️ Workflow Nodes Explained

| Node | Purpose |
|------|---------|
| Execute Workflow | Manual trigger to start the pipeline |
| Edit Fields | Formats and prepares headline input |
| Search | Web search for real-time fact checking |
| Code in JavaScript | Processes and cleans search results |
| AI Agent + Groq | Core LLM analysis of the headline |
| Structured Output Parser | Forces JSON output format |
| Code in JavaScript | Final output formatting |

---

## 📝 What I Learned
- Building multi-node AI agent workflows in n8n
- Integrating Groq LLM API for fast AI inference
- Using Structured Output Parser for reliable JSON responses
- Combining web search with LLM reasoning for fact-checking
- Prompt engineering for consistent verdict generation
- Debugging and optimizing AI pipeline execution time

---

## 🚀 Performance
- ⚡ Execution time: ~4 seconds per query
- 🪙 Token usage: ~626 tokens per execution
- 🎯 AI Agent success rate: consistent structured output

---

## ⚠️ Note
This project was built using n8n cloud free tier 
during my AI Internship at Soft Spark Tech Studios.
Screenshots show the live workflow during active 
development and testing.




