# 🧠 Chatbot Response Evaluator using OpenAI Chat Completions---->>>>

This project evaluates the quality of chatbot responses using OpenAI's **Chat Completions API**, focusing on two lightweight models — `gpt-4.1-nano` and `gpt-4.1-mini`. It systematically scores each response based on contextual accuracy, factual correctness, tone, and citation usage.

---

## 🚀 Features

- ✅ **Automated evaluation of chatbot responses**
- 🔍 **Model comparison** between `gpt-4.1-nano` and `gpt-4.1-mini`
- 📊 **Multi-dimensional evaluation** based on:
  - **Relevance** – How closely the response aligns with the context.
  - **Hallucination** – Whether the response includes unsupported or made-up content.
  - **Sentiment** – The emotional tone (Positive, Neutral, or Negative).
  - **Citation** – Whether source references or links are included.
- ⏱️ **Timing analysis** for each model evaluation
- 📁 **CSV output** with full evaluation data

---

## 📂 Dataset & Files

| File | Description |
|------|-------------|
| `asu_prod_conversations.json` | Contains user-bot chat sessions to evaluate |
| `query_to_chunks.json` | Maps user queries to relevant context chunks |
| `evaluation_results.csv` | Output file with evaluations per query |

---

## 🛠️ Tech Stack

- Python
- OpenAI Chat Completions API (`gpt-4.1-nano` and `gpt-4.1-mini`)
- Pydantic for schema enforcement
- JSON and CSV for data processing
- Time module for benchmarking

---

## 📈 Example Output (CSV Columns)

| Query | Bot_answer | Model_output | Time_taken (s) |
|-------|------------|--------------|----------------|
| "What is ASU GPA requirement?" | "The GPA required is 3.0." | {... full evaluation JSON ...} | 1.42 |

Each row contains:
- The user’s query
- The bot’s response
- A structured evaluation (as JSON)
- Time taken for the model to respond and be evaluated

---

## 📊 Sample Evaluation Output (JSON)

```json
{
  "relevance": "High",
  "relevance_justification": "The answer exactly matches the requirement stated in the context.",
  "hallucination": false,
  "hallucination_reason": "All information was present in the given context.",
  "sentiment": "Neutral",
  "sentiment_reason": "The bot provides a factual answer without emotional tone.",
  "citation": false,
  "citation_justification": "No links or sources were mentioned in the answer."
}

