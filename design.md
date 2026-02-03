# DevSaathi - System Design Document

## Architecture Overview

Simple three-tier architecture:

```
┌─────────────────────────────┐
│   Frontend (React.js)       │
│   - Skill Assessment Form   │
│   - Roadmap Display         │
│   - Code Input + Explanation│
└─────────────────────────────┘
            ↓ REST API
┌─────────────────────────────┐
│   Backend (Express.js)      │
│   - API Routes              │
│   - AI Integration          │
└─────────────────────────────┘
            ↓
    ┌───────────┬──────────┐
    ↓           ↓          ↓
┌────────┐ ┌────────┐ ┌────────┐
│MongoDB │ │OpenAI  │ │Translation│
│        │ │API     │ │Layer   │
└────────┘ └────────┘ └────────┘
```

## Component Structure

### Frontend
```
src/
├── components/
│   ├── SkillAssessment.tsx
│   ├── Roadmap.tsx
│   └── CodeExplainer.tsx
├── services/
│   └── api.ts
└── App.tsx
```

### Backend
```
src/
├── routes/
│   ├── assessment.js
│   ├── roadmap.js
│   └── explain.js
├── services/
│   └── ai.js
├── models/
│   └── User.js
└── server.js
```

## Data Models

The following schemas represent a minimal starting point and may evolve during development.

### User
```javascript
{
  _id: ObjectId,
  email: string,
  targetRole: string,
  skillGaps: [string],
  preferredLanguage: 'en' | 'hi'
}
```

### Roadmap
```javascript
{
  userId: ObjectId,
  topics: [
    {
      name: string,
      resources: [{ title: string, url: string }],
      estimatedHours: number
    }
  ]
}
```

## API Endpoints

### POST /api/assessment
- Input: `{ targetRole: string, answers: boolean[] }`
- Output: `{ skillGaps: string[] }`

### POST /api/roadmap
- Input: `{ userId: string, skillGaps: string[] }`
- Output: `{ topics: [...] }`

### POST /api/explain
- Input: `{ code: string, language: 'en' | 'hi' }`
- Output: `{ explanation: string }`

## AI Integration

### Code Explanation Prompt
```
Explain this code in simple terms:

{code}

Provide:
1. What it does (1-2 sentences)
2. Key concepts used
```

### Roadmap Generation Prompt
```
Create a learning roadmap for {targetRole}.
Skills to learn: {skillGaps}

Provide 5-7 topics in order with:
- Topic name
- Estimated hours
- One free resource (YouTube or documentation)

Format as JSON.
```

### Translation
- Generate explanation in English
- Use a lightweight translation layer with preserved technical terms (initially implemented using a standard translation API)
- Keep technical terms in English

## Implementation Details

### Skill Assessment Logic
```javascript
const roleSkills = {
  'Frontend Developer': ['HTML', 'CSS', 'JavaScript', 'React', 'Git'],
  'Backend Developer': ['Node.js', 'Database', 'API', 'Git', 'Authentication'],
  'Full Stack Developer': ['HTML', 'CSS', 'JavaScript', 'Node.js', 'Database', 'Git']
}

function identifyGaps(role, answers) {
  const required = roleSkills[role]
  return required.filter((skill, i) => !answers[i])
}
```

### Error Handling
- Validate all inputs
- Set 30-second timeout for AI calls
- Show user-friendly error messages
- Log errors to console

### Security
- Validate and sanitize code input
- Rate limit: 5 requests/minute per user
- Store API keys in environment variables
- Use HTTPS

## Proposed Deployment (Prototype)

**Frontend:**
- Suggested platform: Vercel
- Connect to GitHub repository
- Auto-deploy on push to main branch

**Backend:**
- Suggested platform: Render free tier
- Set environment variables (OpenAI key, MongoDB URI, translation API key)
- Use Node.js 18+

**Database:**
- Suggested platform: MongoDB Atlas free tier (512 MB)
- Single collection for users

## Testing

- Manual testing of all three features
- Test with 5-10 sample users
- Verify Hindi translations are readable
- Check response times

## Known Limitations

- Limited to 50 lines of code per explanation
- Only English and Hindi supported
- Basic skill assessment (5 questions only)
- No user authentication (optional for MVP)
- No progress tracking

## Future Improvements

- User authentication
- More detailed assessments
- Progress tracking
- Additional languages
- Code syntax highlighting
- Caching for faster responses
