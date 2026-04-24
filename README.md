# Project's AI Applications

`pw-ai-apps` contains **use-case specific applications** built on top of shared capabilities.

Each application should be thin, focused, and composed using:
- `pw-ai-capabilities`
- `pw-ai-core`

---

## 🧠 Purpose

Deliver business value by:
- implementing workflows
- exposing APIs / interfaces
- orchestrating capabilities

---

## 🧱 Design Principle

> **Applications orchestrate. They do not reinvent.**

---

## 📦 What Belongs Here

- use-case specific workflows
- API endpoints (FastAPI, etc.)
- UI / integration layers
- prompt templates specific to the app
- application-level validation

---

## 🚫 What Does NOT Belong Here

- RAG pipelines
- model wrappers
- reusable prompt frameworks
- evaluation engines (core logic)

👉 These belong in `pw-ai-capabilities` or `pw-ai-core`

---


Each app should follow the standard template:
- workflows
- prompts
- evaluation
- app layer

---

## 🔁 Dependency Model
`Applicaiton` -> `pw-ai-capabilities` -> `pw-ai-core`


---

## 🧭 Example

```python
from pw_ai_capabilities.rag import retrieve_context
from pw_ai_capabilities.prompting import generate_response

def run_input_brief(user_input):
    context = retrieve_context(user_input)
    return generate_response(context, user_input)


## 📁 Structure (in progress)



