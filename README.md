# AI Personal Agent Documentation

A pattern model for creating deeply personalized AI agents using personal context data.

## Overview

This repository provides a systematic approach to building AI agents with specific information about your life, enabling deeply personalized inference and interactions. By capturing, processing, and structuring personal context data, you can create AI assistants that truly understand your preferences, constraints, and goals.

## The Pattern

### 1. Voice Recording
Capture personal context through natural voice recordings discussing your preferences, experiences, goals, and any other relevant information.

### 2. Transcription
Use a **transcription cleanup agent** to convert speech-to-text output into clean, readable text. This agent:
- Removes filler words and false starts
- Adds paragraph breaks for readability
- Fixes obvious transcription errors
- Makes NO substantive edits to preserve original meaning

### 3. Chunking
Apply a **context chunking agent** to break the cleaned transcript into smaller, focused markdown files. Each file covers a specific theme or aspect of your context:
- Preferences
- Constraints
- Goals
- Technical requirements
- Budgetary parameters
- And more...

### 4. Implementation
Connect the individual markdown context files to your preferred AI platform:
- **Custom GPTs** (OpenAI)
- **Gems** (Google)
- **Claude Projects** (Anthropic)
- **OpenAI Assistants API**
- Any platform supporting lightweight RAG (Retrieval-Augmented Generation)

## Repository Map

```
├── agent-model/
│   ├── agents/
│   │   ├── transcription-cleanup-agent.md    # System prompt for transcript cleanup
│   │   └── context-chunking-agent.md         # System prompt for context chunking
│   ├── context-data/
│   │   └── chunked/                          # Example chunked context files
│   │       ├── budget-cost-considerations.md
│   │       ├── destinations-loved.md
│   │       ├── food-dietary-requirements.md
│   │       └── ...                           # Additional context files
│   └── system-prompt/
│       ├── general.md                        # Main system prompt
│       └── subagents/                        # Specialized sub-agent prompts
│           ├── destination-researcher.md
│           ├── budget-optimizer.md
│           └── ...
├── CLAUDE.md                                 # Agent configuration (chunking process)
└── README.md                                 # This file
```

### Key Files

- **[`/agent-model/agents/transcription-cleanup-agent.md`](agent-model/agents/transcription-cleanup-agent.md)** - Complete system prompt for the transcription cleanup agent
- **[`/agent-model/agents/context-chunking-agent.md`](agent-model/agents/context-chunking-agent.md)** - Complete system prompt for the context chunking agent
- **[`/agent-model/context-data/chunked/`](agent-model/context-data/chunked/)** - Example of chunked context files organized by theme
- **[`CLAUDE.md`](CLAUDE.md)** - Working agent configuration used for chunking

## Benefits

- **Deep Personalization**: AI agents understand your specific context and preferences
- **Scalable**: Add new context files as your needs evolve
- **Flexible**: Works with multiple AI platforms
- **Maintainable**: Organized context in discrete, themed files
- **Natural Input**: Capture context through conversational voice recordings

## Getting Started

1. Record a voice memo discussing your context (preferences, goals, constraints, etc.)
2. Use a speech-to-text service to generate a raw transcript
3. Apply the transcription cleanup agent to clean the transcript
4. Run the chunking agent to generate individual context files
5. Upload the context files to your AI platform of choice
6. Interact with a deeply personalized AI agent that knows your context

## Use Cases

- Personal assistants with knowledge of your preferences
- Travel planning agents aware of your budget and interests
- Career coaching with understanding of your goals and experience
- Technical consultants familiar with your stack and constraints
- Any domain where personalized context improves AI assistance

 
