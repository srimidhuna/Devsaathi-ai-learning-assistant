<div align="center">

# DevSaathi

### AI-Powered Learning Assistant for Indian Developers

<br/>

DevSaathi is an AI-driven learning assistant designed to help Indian developers—especially students and beginners—identify skill gaps, follow clear learning roadmaps, and understand code in their preferred language (English or Hindi).

*Empowering developers with AI for Bharat* 🇮🇳

<br/>

---

</div>

<br/>

## Overview

DevSaathi addresses critical challenges faced by aspiring developers in India—particularly those in tier-2 and tier-3 cities—by providing accessible, AI-powered learning tools that break language barriers and offer structured guidance.

<br/>

## The Problem

Many aspiring developers in India face significant barriers that hinder their learning journey:

| Challenge | Description |
|-----------|-------------|
| **Language Barrier** | Most technical content is available only in English, creating accessibility issues for non-native speakers |
| **Unclear Learning Paths** | Students struggle to identify what skills to learn for specific job roles |
| **Academic-Industry Gap** | Significant disconnect between what is taught in colleges and what the industry actually requires |

<br/>

## Our Solution

DevSaathi bridges these gaps by providing:

- **Intelligent Skill Assessment** — Evaluate your current abilities against industry requirements
- **Personalized Learning Roadmaps** — Get AI-generated paths tailored to your goals
- **Multilingual Code Explanations** — Understand code in English or Hindi

<br/>

---

<br/>

## Features

### 1. Skill Gap Identification

Evaluate your current skill set against industry requirements for your target role. Users select a target role and answer simple yes/no questions about their current knowledge.

**How it works:**
- Select your target role: Frontend Developer, Backend Developer, or Full Stack Developer
- Answer 5 skill-based questions about your current knowledge
- Receive a prioritized list of 3-5 skills you need to learn
- Get AI-assisted priority ordering based on industry requirements

<br/>

### 2. AI-Generated Learning Roadmap

Based on your identified skill gaps, DevSaathi generates a structured learning path to help you acquire the necessary skills efficiently.

**What you get:**
- 5-7 topics arranged in optimal learning order
- Estimated time required for each topic
- Curated free resources including YouTube tutorials and official documentation
- Clear progression from fundamentals to advanced concepts

<br/>

### 3. Multilingual Code Explanation

Paste any code snippet and receive clear, easy-to-understand explanations in your preferred language. This feature is designed to help beginners understand complex code without language being a barrier.

**Capabilities:**
- Support for code snippets up to 50 lines
- Explanations available in English and Hindi
- Breaks down what the code does in simple terms
- Identifies and explains key programming concepts used

<br/>

---

<br/>

## Target Users

DevSaathi is built for:

| User Type | Description |
|-----------|-------------|
| **CS/IT Students** | Computer science and IT students preparing for their first developer job |
| **Self-Taught Developers** | Anyone learning to code independently without formal education |
| **Career Switchers** | Professionals transitioning into software development roles |
| **Beginners** | Those targeting frontend, backend, or full-stack developer positions |

<br/>

---

<br/>

## Technology Stack

### Frontend
- React.js for building interactive user interfaces
- TypeScript for type-safe development
- CSS3 for styling and responsive design

### Backend
- Node.js runtime environment
- Express.js web application framework
- RESTful API architecture

### Database & Services
- MongoDB Atlas for data persistence
- Large Language Model API for AI-powered features
- Translation API for multilingual support

### Deployment
- Vercel for frontend hosting
- Render for backend services
- MongoDB Atlas free tier for database

<br/>

---

<br/>

## System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                              │
│                                                                  │
│    ┌──────────────────────────────────────────────────────┐     │
│    │              React.js + TypeScript                    │     │
│    │   ┌─────────────┬─────────────┬─────────────────┐    │     │
│    │   │   Skill     │  Roadmap    │     Code        │    │     │
│    │   │ Assessment  │  Display    │   Explainer     │    │     │
│    │   └─────────────┴─────────────┴─────────────────┘    │     │
│    └──────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────┘
                              │
                              │ REST API
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                       SERVICE LAYER                              │
│                                                                  │
│    ┌──────────────────────────────────────────────────────┐     │
│    │              Node.js + Express.js                     │     │
│    │   ┌─────────────┬─────────────┬─────────────────┐    │     │
│    │   │ Assessment  │  Roadmap    │   Explanation   │    │     │
│    │   │   Routes    │   Routes    │     Routes      │    │     │
│    │   └─────────────┴─────────────┴─────────────────┘    │     │
│    └──────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                        DATA LAYER                                │
│                                                                  │
│    ┌────────────────┐  ┌────────────────┐  ┌────────────────┐   │
│    │                │  │                │  │                │   │
│    │    MongoDB     │  │    LLM API     │  │  Translation   │   │
│    │    Atlas       │  │   Integration  │  │    Service     │   │
│    │                │  │                │  │                │   │
│    └────────────────┘  └────────────────┘  └────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

<br/>

---

<br/>

## Project Structure

```
devsaathi/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── SkillAssessment.tsx    # Skill gap identification UI
│   │   │   ├── Roadmap.tsx            # Learning roadmap display
│   │   │   └── CodeExplainer.tsx      # Code explanation interface
│   │   ├── services/
│   │   │   └── api.ts                 # API communication layer
│   │   ├── styles/
│   │   │   └── index.css              # Application styles
│   │   └── App.tsx                    # Main application component
│   ├── package.json
│   └── tsconfig.json
│
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── assessment.js          # Skill assessment endpoints
│   │   │   ├── roadmap.js             # Roadmap generation endpoints
│   │   │   └── explain.js             # Code explanation endpoints
│   │   ├── services/
│   │   │   ├── ai.js                  # LLM integration service
│   │   │   └── translation.js         # Translation service
│   │   ├── models/
│   │   │   └── User.js                # User data model
│   │   └── server.js                  # Express server setup
│   ├── package.json
│   └── .env.example
│
├── docs/
│   ├── design.md                      # System design documentation
│   └── requirements.md                # Project requirements
│
└── README.md
```

<br/>

---

<br/>

## AI for Bharat Alignment

DevSaathi is committed to making technical education accessible across India by:

| Initiative | Impact |
|------------|--------|
| **Language Accessibility** | Technical explanations available in Hindi, breaking the English-only barrier |
| **Structured Guidance** | AI-driven personalized roadmaps eliminate confusion about what to learn |
| **Free Resources** | Curated content from free platforms reduces dependency on expensive courses |
| **Inclusive Design** | Built with tier-2 and tier-3 city developers in mind |

<br/>

---

<br/>

## Future Enhancements

DevSaathi will continue to evolve with planned features including:

- **User Authentication** — Personal accounts to save progress and preferences
- **Progress Tracking** — Monitor your learning journey over time
- **Additional Languages** — Support for more Indian languages beyond Hindi
- **Advanced Assessments** — More detailed skill evaluations with practical tests
- **Interview Preparation** — Practice questions and mock interview features
- **Mobile Application** — Native apps for learning on the go
- **Community Features** — Connect with other learners and mentors

<br/>

---

<br/>

<div align="center">

**DevSaathi** — Empowering Indian Developers through AI

</div>
