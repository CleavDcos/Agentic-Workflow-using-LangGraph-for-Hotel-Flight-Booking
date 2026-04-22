# ✈️ AI Travel Agent using LangGraph

This project demonstrates how to build an **agentic workflow** using LangGraph to handle **flight and hotel booking queries** with web search capabilities.

---

## 🧠 Overview

The system is designed as an **AI-powered travel assistant** that can:

* 🔍 Search the web for travel-related information (via Tavily)
* ✈️ Find flights
* 🏨 Suggest hotels
* 🤖 Use an agentic workflow to decide which tool to call

The workflow is built using **LangGraph**, which enables structured decision-making between multiple tools.

---

## ⚙️ Architecture

```
User Input
   ↓
LangGraph Agent
   ↓
Decision Node (LLM reasoning)
   ↓
---------------------------------
|       |           |            |
Web     Flights     Hotels       Fallback
Search  Tool        Tool         Response
(Tavily)
---------------------------------
   ↓
Final Response to User
```

---

## 🔧 Tools Used

### 🌐 Web Search Tool

* Powered by Tavily
* Used for:

  * Travel recommendations
  * Destination info
  * General queries

---

### ✈️ Flight & 🏨 Hotel Tools

Originally, this project used the Amadeus IT Group API:

* Flight search
* Hotel search
* Structured travel data

⚠️ **Important Update:**
Amadeus has **discontinued its self-service APIs**, and new developers cannot access them anymore.

---

## 🚨 Current Limitation

Since Amadeus self-service APIs are no longer available:

* ❌ Cannot generate new API keys
* ❌ Cannot use free developer access
* ❌ Existing workflows depending on Amadeus may break

---

## 🔄 Recommended Alternatives

To continue development, replace Amadeus with:

* Duffel (Flights)
* Travelpayouts (Flights + Hotels)
* Expedia Group (Hotels API)

👉 Choose based on:

* Ease of access
* API availability
* Project requirements

---

## 🧩 How LangGraph is Used

LangGraph enables:

1. **State Management**

   * Tracks user intent (flight, hotel, or info)

2. **Decision Making**

   * LLM decides which tool to call

3. **Tool Invocation**

   * Calls appropriate function:

     * `search_web()`
     * `search_flights()`
     * `search_hotels()`

4. **Response Aggregation**

   * Combines results into a final answer

---

## 🧪 Example Flow

**User Query:**

> “Find flights from Goa to Delhi and suggest hotels”

**Agent Steps:**

1. Detects intent → Flights + Hotels
2. Calls:

   * Flight API
   * Hotel API
3. Optionally uses Tavily for extra info
4. Returns structured recommendations

---

## 🚀 Getting Started

1. Install dependencies
2. Set environment variables:

```bash
TAVILY_API_KEY=your_key
FLIGHT_API_KEY=your_key
HOTEL_API_KEY=your_key
```

3. Run the LangGraph workflow
4. Interact with the agent

---

## 🧠 Key Insight

This project focuses on:

> Building **intelligent agent workflows**, not just API integrations.

APIs may change or shut down (like Amadeus), but a well-designed agent system can **adapt by swapping tools easily**.

---

## 📌 Future Improvements

* Add multiple API fallbacks
* Improve ranking (cheapest / fastest / best-rated)
* Integrate real booking systems
* Enhance conversational memory

---

## ⚠️ Note

This project is intended for **learning and prototyping purposes**.
Production systems require:

* API agreements
* Payment integration
* Compliance with travel regulations

---

## 💡 Final Thought

LangGraph allows you to move from:

> “Calling APIs manually”
> ➡️ to
> “Building intelligent, decision-making AI systems”

---
