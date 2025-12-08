---
title: Contract Playbook AI
---

# Contract Playbook AI

A client-side, AI-powered contract review application. Analyze contracts, generate playbooks, and redline documents natively in Microsoft Word–compatible format—all from your browser. True docx Track Changes—no HTML/Markdown wrappers, fully client-side, nothing like this open source today.

[![Watch the Demo](https://img.youtube.com/vi/JCCNyjN34EE/0.jpg)](https://www.youtube.com/watch?v=JCCNyjN34EE)

---

## 🚀 Key Features

- **Playbook Generation** – Extract negotiation rules, risk positions, and preferred clauses from existing contracts.  
- **Automated Contract Review** – Identify risks (Red/Yellow/Green) against a defined playbook.  
- **Interactive Redlining** – Apply AI-suggested changes directly in a rich-text editor.  
- **Microsoft Word Compatibility** – Parse `.docx` in-browser and export with formatting preserved.

---

## 📁 Why `.docx` Matters

Microsoft Word `.docx` is the de facto standard for contracts and legal documents. Lawyers, corporate legal teams, and courts rely on it for everything from clause numbering and cross-references to styles, footnotes, and Track Changes. Even small formatting or version errors can change the meaning of a contract, so preserving fidelity is critical.

Many tech solutions assume Markdown, HTML, or JSON is enough—but these formats break essential legal workflows. Without true `.docx` support, you lose Track Changes, precise paragraph structure, numbering, and metadata, making redlines unreliable and collaboration error-prone.

`.docx` also enables seamless collaboration across multiple parties, with consistent formatting and audit trails. Any tool that ignores it risks disrupting real-world legal workflows, which is why native `.docx` editing is indispensable.

---

## 🌟 Vision

This project is an experimental frontend proof-of-concept. Currently, it leverages [Superdoc](https://github.com/Harbour-Enterprises/SuperDoc) for client-side `.docx` parsing and editing, allowing rapid experimentation with AI-assisted contract review and playbook generation.  

The long-term vision is to build a **fully open-source library** that enables **programmatic, full-document editing and diff at the Word level**, without relying on third-party parsing frameworks. This will start with a **native Microsoft Word JavaScript API** that performs word-level diffing and precise Track Changes management, bringing the capabilities of our AI-assisted playbook engine directly into Word itself.  

I’ve already prototyped this approach—check out the proof-of-concept in this demo:  
[![YouTube Demo: MS Word Add-In for Diff](https://img.youtube.com/vi/0Oa05jk3wrU/0.jpg)](https://youtu.be/0Oa05jk3wrU?si=nbhoEMUjY41wxgOx)

The ultimate goal is to **phase out Superdoc**, providing developers and organizations with a fully open, extensible, and secure solution for AI-assisted contract automation, workflow integration, and robust document diffing. Contributions that advance either the frontend proof-of-concept, the AI playbook logic, or the eventual library are highly welcome.

---

## 🔗 Demo & Repo

You can test the full Contract Playbook AI workflow — playbook extraction, review, and Word-compatible redlining — directly in your browser using your own Google AI Studio free tier.

[▶️ Try the Live Demo (Runs in Your Google AI Studio Account)](https://aistudio.google.com/app/prompts?state=%7B%22ids%22:%5B%221XR53uQDCxbtkL0RnFgpY3ZxL_A1WhvVe%22%5D,%22action%22:%22open%22,%22userId%22:%22107041048597162520663%22,%22resourceKeys%22:%7B%7D%7D&usp=sharing)

After clicking the link:

1. Allow access to Google Drive to load this prompt.  
2. Agree to the Google AI Studio terms and conditions.  
3. Click "Continue to the app" on the "This app is from another developer" screen. 
4. Open Preview screen and run the app.  

> That’s it — the entire app runs client-side, using your own Gemini API allowance.
No installs, no backend, no API key setup. 
> ⚠️ Google AI Studio’s free tier may change or disappear in the future, so make hay while the sun shines.  
> For best performance, use contracts under ~10 pages as sequential LLM calls are used.

- [GitHub Repository](https://github.com/yuch85/contract-playbook-ai)

---

## ⚡ Behind the Scenes: AI Playbook Engineering

The client-side contract playbook engine is designed for speed, reliability, and real-world contracts:

- **Canonical + Extensible Taxonomy** – Starts with common categories (LIABILITY, INDEMNITY, CONFIDENTIALITY, etc.) but lets the LLM propose domain-specific ones.  
- **Smart Rule Normalization** – Fuzzy category matching, auto-generated IDs, and auto-synonyms ensure consistent, semantic rules.  
- **Fast Local Classification** – Clauses are classified in-browser to pre-filter relevant rules before LLM calls, cutting token usage by 80–95%.  
- **Chunking** – Segments contracts to prevent attention dilution, keeping LLM analysis accurate on long documents.  
- **Human-Readable Intermediate Representation** – Avoids long JSON parsing errors by translating rules into natural language IR.  

All of this is aimed at making AI-assisted contract review faster, more reliable, and developer-friendly—without sacrificing token efficiency or context fidelity.

---

## 📝 Native .docx Editing & Track Changes

This app works directly with Microsoft Word `.docx` files—no intermediate formats, no HTML wrappers, no lossy conversions. It currently leverages **Superdoc** for client-side parsing and editing, but the architecture, AI integration, and granular Track Changes mapping are custom.  

- **Shadow Document Architecture** – The `.docx` is parsed in-browser into a lightweight JSON representation, preserving paragraphs, numbering, and metadata while remaining fully editable.  
- **Node-Level Change Isolation** – Edits are mapped to individual paragraph or node positions, allowing AI-generated suggestions to integrate as granular insertions and deletions.  
- **Track Changes Compatibility** – Every AI-suggested modification respects Word’s native Track Changes format, so lawyers and contract teams see real redlines exactly as if they were editing in Word.  
- **Browser-First Implementation** – All parsing, mapping, and AI-assisted editing happen client-side, keeping your documents private and secure.

---

## 🤝 Contributing

Want to help push this further? Check out [CONTRIBUTING.md](https://github.com/yuch85/contract-playbook-ai/blob/main/CONTRIBUTING.md). We're especially looking for developers interested in:  

- Frontend improvements and UX  
- AI playbook logic refinement  
- Advanced docx manipulation (future library work)  


## ⚠️ Notes

- Current project uses **Superdoc** for native docx editing in-browser.  
- Requires a Google AI Studio account for Gemini API access.  
- Experimental: not yet enterprise-deployable, but intended as a foundation for robust tools.
