# 🏗️ TROPICO Architecture

## System Overview

```
┌─────────────────────────────────────────┐
│         TROPICO DASHBOARD              │
│  (Next.js + React ShadcN/UI)           │
└──────────────────┬──────────────────────┘
                   │
        ┌──────────┼──────────┐
        │          │          │
    ┌───▼─┐   ┌───▼──┐  ┌───▼──┐
    │ CLI │   │ Web  │  │ API  │
    └─────┘   └──────┘  └──────┘
        │          │          │
        └──────────┼──────────┘
                   │
        ┌──────────▼──────────────┐
        │   AI Engine             │
        │ ┌─────────────────────┐ │
        │ │ Claude (planning)   │ │
        │ │ GPT-4 (content)     │ │
        │ │ DALL-E (visuals)    │ │
        │ │ Embeddings (clone)  │ │
        │ └─────────────────────┘ │
        └──────────┬───────────────┘
                   │
   ┌───────────────┼───────────────┐
   │               │               │
┌──▼──┐      ┌────▼────┐      ┌──▼──┐
│ DB  │      │ Storage  │      │Jobs │
│Supabase     │ AWS S3   │      │Queue
└─────┘      └──────────┘      └─────┘
```

## Components

### Frontend (Next.js Dashboard)
- User authentication
- Business creation wizard
- Real-time progress tracking
- Asset management
- Analytics dashboard

### API (Express.js)
- REST endpoints
- WebSocket for real-time updates
- Job queue management
- File upload/download

### AI Engine
- Claude API for planning & strategy
- GPT-4 for content generation
- DALL-E for images
- Embeddings for semantic analysis

### Database
- PostgreSQL for structured data
- Redis for caching & job queue
- S3 for file storage

## Data Flow

1. User creates business in dashboard
2. Request sent to API
3. API creates job in queue
4. Worker processes job
5. Calls AI APIs for content generation
6. Stores results in database
7. User notified via WebSocket
8. Assets available for download

## Scalability

- Horizontal scaling via job queue
- Multiple workers processing in parallel
- Redis caching to reduce API calls
- CDN for static assets
- Database replication for high availability
