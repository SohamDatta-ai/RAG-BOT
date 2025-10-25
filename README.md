# RAG BOTS

Create and deploy intelligent AI chatbots from your documents using RAG (Retrieval Augmented Generation) technology.

## Features

- 📄 **Document Upload**: Support for PDF, DOCX, and TXT files
- 🤖 **AI Training**: Automatic document processing and vectorization
- 💬 **Smart Chat**: Intelligent responses based on your content
- 🌐 **Easy Embed**: One-line script to embed on any website
- 📊 **Analytics**: Track usage and performance
- 🔒 **Secure**: User isolation and data privacy

## Tech Stack

- **Frontend**: Next.js 14, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express, TypeScript
- **Database**: MongoDB (user data), PineCone (vector database)
- **Queue**: Redis + BullMQ
- **AI**: OpenAI API (GPT models + embeddings)
- **Deployment**: Docker Compose

## Quick Start

### Prerequisites

- Docker and Docker Compose
- OpenAI API key
- Node.js 18+ (for development)

### 1. Clone and Setup

```bash
git clone <repository-url>
cd AI-chatbot-generator
```

### 2. Environment Configuration

```bash
cp env.example .env
```

Edit `.env` and add your OpenAI API key:
```env
OPENAI_API_KEY=your_openai_api_key_here
JWT_SECRET=your_jwt_secret_here
```

### 3. Start the Application

```bash
docker compose up --build
```

This will start:
- Frontend: http://localhost:3000
- Backend API: http://localhost:8000
- MongoDB: localhost:27017
- Redis: localhost:6379

### 4. Access the Application

Open http://localhost:3000 in your browser to start creating AI agents!

## Usage Guide

### Creating an AI Agent

1. **Create Agent**: Click "Create New AI Agent" and configure:
   - Agent name and personality
   - AI model (GPT-3.5, GPT-4, etc.)
   - Temperature (creativity level)
   - System prompt

2. **Upload Documents**: 
   - Drag & drop PDF, DOCX, or TXT files
   - Maximum 10 files, 5MB each, 50MB total
   - Automatic validation and progress tracking

3. **Training**: 
   - Documents are automatically processed
   - Text is chunked and vectorized
   - Stored in Pinecone for fast retrieval

4. **Test in Playground**:
   - Chat with your AI agent
   - Test responses based on uploaded documents
   - Adjust settings in real-time

5. **Deploy**:
   - Generate embed code
   - Add to any website with one line
   - Track usage and conversations

### Embedding on Websites

1. Copy the generated script tag:
```html
<script src="http://localhost:8000/embed/agent_id.js"></script>
```

2. Add to your website's HTML

3. The chatbot will appear as a floating widget

## Development

### Frontend Development

```bash
cd frontend
npm install
npm run dev
```

### Backend Development

```bash
cd backend
npm install
npm run dev
```

### Database Access

- **MongoDB**: Use MongoDB Compass or mongo shell
- **Redis**: Use redis-cli or RedisInsight

## API Endpoints

### Agents
- `POST /api/agents` - Create agent
- `GET /api/agents` - List agents
- `GET /api/agents/:id` - Get agent details
- `PUT /api/agents/:id` - Update agent
- `DELETE /api/agents/:id` - Delete agent


## License

MIT

---
Built with ❤️ by Soham.
