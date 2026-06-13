# 🌴 TROPICO Quick Start Guide

## 5-Minute Setup

### Step 1: Clone & Install
```bash
git clone https://github.com/uimasters/tropic.git
cd tropic
npm install
```

### Step 2: Configure Environment
```bash
cp .env.example .env
# Edit .env with your API keys:
# OPENAI_API_KEY=sk-...
# ANTHROPIC_API_KEY=sk-ant-...
```

### Step 3: Start Services
```bash
# Terminal 1: Start database
docker-compose up postgres redis

# Terminal 2: Run migrations
npm run db:migrate

# Terminal 3: Start API
npm run server

# Terminal 4: Start dashboard
cd apps/dashboard && npm run dev
```

### Step 4: Open Dashboard
Visit http://localhost:3000 and start generating businesses! 🚀

---

## Try CLI (No Setup Needed)
```bash
npm run tropico:cli

# Answer the prompts:
# 1. Business type?
# 2. Target audience?
# 3. Budget?

# 📥 Get your generated business as ZIP file
```

---

## API Quick Example

```bash
curl -X POST http://localhost:5000/api/generate \
  -H "Content-Type: application/json" \
  -d '{
    "business": "E-commerce store",
    "audience": "Millennials",
    "budget": 500
  }'
```

Response: `{ success: true, businessId: "...", downloadUrl: "..." }`

---

Need help? Check out [README.md](../README.md) for detailed documentation!
