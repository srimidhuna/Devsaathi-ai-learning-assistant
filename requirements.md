# DevSaathi - AI-Powered Learning Assistant for Indian Developers

## Problem Statement

Indian developers, especially those in tier-2 and tier-3 cities, face significant barriers:

- **Language Barrier**: Many Indian developers struggle with English-only technical documentation
- **Unclear Learning Paths**: Students don't know what to learn for specific roles
- **Skill-Job Mismatch**: Large gap between academic curriculum and industry requirements

## Proposed Solution

DevSaathi is an AI-powered learning assistant that helps Indian developers identify skill gaps and get technical explanations in their preferred language.

## Target Users

- Computer science students preparing for their first developer job
- Self-taught developers learning to code

## Core Features (MVP)

### 1. Skill Gap Identification

Users select a target role and answer 5 simple questions about their current knowledge. The system uses AI to analyze responses and intelligently prioritize which skills to learn first based on the target role requirements.

**Input:**
- Target role (Frontend/Backend/Full Stack Developer)
- 5 yes/no questions about basic skills

**Output:**
- List of 3-5 skills to learn
- AI-assisted priority order

### 2. Basic Learning Roadmap

Based on skill gaps, generate a simple ordered list of topics with free resources.

**Output:**
- 5-7 topics in learning order
- 1-2 free resources per topic (YouTube links, documentation)
- Estimated time per topic

### 3. Multilingual Code Explanation

Users paste code and get explanations in English or Hindi.

**Input:**
- Code snippet (max 50 lines)
- Language preference (English/Hindi)

**Output:**
- Simple explanation of what the code does
- Key concepts identified

## Technical Stack

**Frontend:**
- React.js
- Basic CSS

**Backend:**
- Node.js + Express.js
- Simple REST API

**Database:**
- MongoDB (store user data and progress)

**AI:**
- A commercially available large language model API for code explanation and roadmap generation (e.g., GPT-3.5-class models)
- A lightweight translation layer with preserved technical terms (initially implemented using a standard translation API)


**Hosting:**
- Vercel (frontend)
- Render free tier (backend)
- MongoDB Atlas free tier

## Success Criteria

- Users can complete skill assessment in under 2 minutes
- Users receive a learning roadmap with 5-7 topics
- Users can paste code and get explanation in English or Hindi
- All responses within 10 seconds

## Development Timeline (2 Weeks)

**Week 1:**
- Day 1-2: Setup project, basic UI
- Day 3-4: Skill assessment form and logic
- Day 5-7: Code explanation feature with AI integration

**Week 2:**
- Day 8-9: Roadmap generation
- Day 10-11: Hindi translation integration
- Day 12-13: Testing and bug fixes
- Day 14: Demo preparation and documentation

## Future Enhancements

- Additional Indian languages
- More detailed skill assessments
- Progress tracking
- Job market insights
- Interview preparation
- Community features
- Mobile app

## Alignment with "AI for Bharat"

DevSaathi addresses learning barriers for Indian developers by:

1. **Language Accessibility**: Technical explanations in Hindi
2. **Structured Learning**: Clear guidance on what to learn
3. **AI-Powered**: Uses AI to personalize learning paths

This solution makes technical education more accessible to non-English speakers across India.
