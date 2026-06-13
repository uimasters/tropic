# 📚 TROPICO API Documentation

## Base URL
```
http://localhost:5000/api
```

## Authentication
All endpoints require a valid JWT token in the `Authorization` header:
```
Authorization: Bearer <your_jwt_token>
```

---

## 🔐 Authentication Endpoints

### Register
```http
POST /auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "secure_password",
  "name": "John Doe"
}
```

**Response:**
```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "user-123",
    "email": "user@example.com",
    "name": "John Doe"
  }
}
```

### Login
```http
POST /auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "secure_password"
}
```

**Response:**
```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "user-123",
    "email": "user@example.com",
    "name": "John Doe"
  }
}
```

---

## 🏢 Business Endpoints

### Create Business
```http
POST /businesses
Content-Type: application/json
Authorization: Bearer <token>

{
  "name": "My E-Commerce Store",
  "niche": "E-commerce",
  "targetAudience": "Millennials interested in sustainable fashion",
  "budget": 500,
  "goals": ["increase_sales", "build_brand"],
  "socialMedia": ["instagram", "tiktok"]
}
```

**Response:**
```json
{
  "success": true,
  "business": {
    "id": "biz-123",
    "name": "My E-Commerce Store",
    "niche": "E-commerce",
    "targetAudience": "Millennials interested in sustainable fashion",
    "budget": 500,
    "status": "created",
    "createdAt": "2026-06-13T14:58:37Z",
    "updatedAt": "2026-06-13T14:58:37Z"
  }
}
```

### Get Business
```http
GET /businesses/:businessId
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "business": {
    "id": "biz-123",
    "name": "My E-Commerce Store",
    "niche": "E-commerce",
    "status": "completed",
    "website": { ... },
    "emailSequences": [ ... ],
    "socialMedia": [ ... ],
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

### List Businesses
```http
GET /businesses?page=1&limit=10&status=completed
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "businesses": [ ... ],
  "pagination": {
    "total": 25,
    "page": 1,
    "limit": 10,
    "pages": 3
  }
}
```

### Delete Business
```http
DELETE /businesses/:businessId
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "message": "Business deleted successfully"
}
```

---

## 🌐 Website Generator Endpoints

### Generate Website
```http
POST /skills/website-generator
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "businessName": "My E-Commerce Store",
  "businessType": "e-commerce",
  "targetAudience": "Millennials",
  "theme": "modern",
  "features": ["products", "cart", "checkout", "reviews"]
}
```

**Response:**
```json
{
  "success": true,
  "website": {
    "id": "web-123",
    "businessId": "biz-123",
    "html": "<html>...</html>",
    "css": "body { ... }",
    "components": [ ... ],
    "seoData": {
      "title": "My E-Commerce Store",
      "metaDescription": "...",
      "keywords": ["fashion", "sustainable", "online store"]
    },
    "previewUrl": "http://localhost:5000/preview/web-123",
    "downloadUrl": "http://localhost:5000/download/web-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

### Get Website
```http
GET /websites/:websiteId
Authorization: Bearer <token>
```

---

## 📧 Email Automation Endpoints

### Generate Email Sequences
```http
POST /skills/email-automation
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "sequenceType": "onboarding",
  "duration": 7,
  "customerType": "new_customers",
  "tone": "friendly"
}
```

**Response:**
```json
{
  "success": true,
  "emailSequence": {
    "id": "email-seq-123",
    "businessId": "biz-123",
    "type": "onboarding",
    "emails": [
      {
        "day": 1,
        "subject": "Welcome to My Store!",
        "preheader": "Get 10% off your first purchase",
        "html": "<html>...</html>",
        "plainText": "...",
        "variables": ["first_name", "discount_code"]
      },
      {
        "day": 3,
        "subject": "Here's what our customers love",
        "html": "..."
      }
    ],
    "downloadUrl": "http://localhost:5000/download/email-seq-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

### Update Email Sequence
```http
PATCH /email-sequences/:sequenceId
Content-Type: application/json
Authorization: Bearer <token>

{
  "emails": [
    {
      "day": 1,
      "subject": "Updated Subject"
    }
  ]
}
```

---

## 📱 Social Media Endpoints

### Generate Social Media Calendar
```http
POST /skills/marketing-engine
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "platforms": ["instagram", "tiktok", "facebook"],
  "duration": 30,
  "tone": "casual",
  "contentTypes": ["promotional", "educational", "entertaining"]
}
```

**Response:**
```json
{
  "success": true,
  "socialMediaCalendar": {
    "id": "social-123",
    "businessId": "biz-123",
    "platforms": ["instagram", "tiktok", "facebook"],
    "posts": [
      {
        "date": "2026-06-13",
        "platform": "instagram",
        "content": "Check out our latest collection! 🎨",
        "image": "data:image/png;base64,...",
        "hashtags": ["fashion", "sustainable", "eco"],
        "bestTime": "18:00",
        "callToAction": "Link in bio"
      }
    ],
    "downloadUrl": "http://localhost:5000/download/social-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

---

## 🎯 Ad Campaign Endpoints

### Generate Ad Campaign
```http
POST /skills/ad-generator
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "platforms": ["google", "facebook", "tiktok"],
  "budget": 500,
  "targetAudience": {
    "age": [25, 40],
    "interests": ["fashion", "sustainability"],
    "locations": ["US", "UK", "CA"]
  },
  "duration": 30
}
```

**Response:**
```json
{
  "success": true,
  "adCampaign": {
    "id": "ad-camp-123",
    "businessId": "biz-123",
    "platforms": ["google", "facebook", "tiktok"],
    "campaigns": [
      {
        "platform": "google",
        "headlines": [
          "Sustainable Fashion for Everyone",
          "Eco-Friendly Styles"
        ],
        "descriptions": [
          "Shop our collection of sustainable fashion...",
          "Wear fashion that cares..."
        ],
        "images": ["url1", "url2"],
        "budget": 200
      }
    ],
    "downloadUrl": "http://localhost:5000/download/ad-camp-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

---

## 🔄 Content Cloner Endpoints

### Analyze Competitor
```http
POST /skills/content-cloner
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "competitorUrl": "https://www.competitor-site.com",
  "analysisType": ["structure", "copy", "design", "marketing"],
  "generateVariations": true
}
```

**Response:**
```json
{
  "success": true,
  "analysis": {
    "id": "analysis-123",
    "businessId": "biz-123",
    "competitorUrl": "https://www.competitor-site.com",
    "findings": {
      "structure": {
        "hero": "Full-width image with CTA",
        "features": "3-column grid"
      },
      "copy": {
        "tone": "professional and friendly",
        "keyMessages": ["quality", "sustainability", "affordability"]
      }
    },
    "uniqueVariations": [
      {
        "section": "Hero",
        "original": "...",
        "variation": "..."
      }
    ],
    "downloadUrl": "http://localhost:5000/download/analysis-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

---

## 🎨 Brand Identity Endpoints

### Generate Brand Identity
```http
POST /skills/brand-identity
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "businessName": "My E-Commerce Store",
  "industry": "Fashion",
  "values": ["sustainability", "quality", "affordability"],
  "targetAudience": "Millennials"
}
```

**Response:**
```json
{
  "success": true,
  "brandIdentity": {
    "id": "brand-123",
    "businessId": "biz-123",
    "logo": "data:image/svg+xml;base64,...",
    "colors": {
      "primary": "#2E7D32",
      "secondary": "#FFA500",
      "accent": "#FF6B6B",
      "neutral": ["#FFFFFF", "#F5F5F5", "#333333"]
    },
    "typography": {
      "heading": {
        "name": "Montserrat",
        "weights": [600, 700, 800]
      },
      "body": {
        "name": "Open Sans",
        "weights": [400, 500]
      }
    },
    "voiceAndTone": {
      "description": "Friendly, approachable, and inspiring",
      "examples": ["We're passionate about sustainability", "Join our movement"],
      "doList": ["Be authentic", "Inspire action"],
      "dontList": ["Use jargon", "Be preachy"]
    },
    "story": "Founded in 2026...",
    "downloadUrl": "http://localhost:5000/download/brand-123.zip",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

---

## 💼 Business Plan Endpoints

### Generate Business Plan
```http
POST /skills/business-plan
Content-Type: application/json
Authorization: Bearer <token>

{
  "businessId": "biz-123",
  "businessName": "My E-Commerce Store",
  "industry": "Fashion E-commerce",
  "targetMarket": "Millennials interested in sustainable fashion",
  "fundingNeeded": 50000
}
```

**Response:**
```json
{
  "success": true,
  "businessPlan": {
    "id": "plan-123",
    "businessId": "biz-123",
    "executiveSummary": "...",
    "problemStatement": "...",
    "solution": "...",
    "marketAnalysis": {
      "marketSize": "$50B globally",
      "growthRate": "15% YoY",
      "trends": ["Sustainability", "Online shopping", "Direct-to-consumer"]
    },
    "revenueModel": {
      "type": "e-commerce",
      "pricing": [
        {
          "name": "Standard",
          "price": 50,
          "margin": "40%"
        }
      ]
    },
    "kpis": [
      {
        "name": "Customer Acquisition Cost",
        "target": 25,
        "metric": "$ per customer",
        "timeline": "6 months"
      }
    ],
    "downloadUrl": "http://localhost:5000/download/plan-123.pdf",
    "createdAt": "2026-06-13T14:58:37Z"
  }
}
```

---

## 📊 Analytics Endpoints

### Get Business Analytics
```http
GET /analytics/businesses/:businessId?period=30days
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "analytics": {
    "businessId": "biz-123",
    "period": "30 days",
    "metrics": {
      "websiteViews": 1250,
      "emailOpens": 356,
      "emailClicks": 89,
      "socialImpressions": 5620,
      "adClicks": 245,
      "conversions": 12
    },
    "trends": {
      "websiteViews": "+15%",
      "conversions": "+8%"
    }
  }
}
```

---

## 📥 Download Endpoints

### Download Business Package
```http
GET /download/businesses/:businessId
Authorization: Bearer <token>
```

Downloads a ZIP file containing all generated assets.

### Download Specific Asset
```http
GET /download/:assetType/:assetId
Authorization: Bearer <token>
```

---

## ⚙️ Job Queue Endpoints

### Get Job Status
```http
GET /jobs/:jobId
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "job": {
    "id": "job-123",
    "type": "website-generator",
    "status": "completed",
    "progress": 100,
    "result": { ... },
    "createdAt": "2026-06-13T14:58:37Z",
    "completedAt": "2026-06-13T15:05:12Z"
  }
}
```

---

## 🔄 WebSocket Events

Connect to WebSocket for real-time updates:

```javascript
const ws = new WebSocket('ws://localhost:5000/socket?token=<token>');

// Listen for job progress
ws.addEventListener('message', (event) => {
  const data = JSON.parse(event.data);
  
  if (data.type === 'job_progress') {
    console.log(`Job ${data.jobId}: ${data.progress}%`);
  }
  
  if (data.type === 'job_completed') {
    console.log('Job completed!', data.result);
  }
});
```

---

## 🚨 Error Handling

All errors follow this format:

```json
{
  "success": false,
  "error": {
    "code": "INVALID_REQUEST",
    "message": "Business not found",
    "details": { ... }
  }
}
```

### Common Error Codes

| Code | Status | Message |
|------|--------|---------|
| INVALID_REQUEST | 400 | Invalid request parameters |
| UNAUTHORIZED | 401 | Missing or invalid token |
| FORBIDDEN | 403 | You don't have permission |
| NOT_FOUND | 404 | Resource not found |
| RATE_LIMITED | 429 | Too many requests |
| SERVER_ERROR | 500 | Internal server error |

---

## 📋 Rate Limiting

- **Free tier:** 100 requests/hour
- **Pro tier:** 1000 requests/hour
- **Agency tier:** Unlimited

Rate limit headers:
```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 45
X-RateLimit-Reset: 1623625200
```

---

## 🔗 Webhook Events

Configure webhooks in your dashboard. We'll POST these events:

```json
{
  "event": "business.completed",
  "businessId": "biz-123",
  "timestamp": "2026-06-13T15:05:12Z",
  "data": { ... }
}
```

---

## 📖 Pagination

List endpoints support pagination:

```
GET /businesses?page=2&limit=25&sort=createdAt&order=desc
```

**Response:**
```json
{
  "success": true,
  "data": [ ... ],
  "pagination": {
    "total": 100,
    "page": 2,
    "limit": 25,
    "pages": 4,
    "hasNext": true,
    "hasPrev": true
  }
}
```

---

## 🧪 Testing

### cURL Example
```bash
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "password": "password123"
  }'
```

### JavaScript/Node.js Example
```javascript
const response = await fetch('http://localhost:5000/api/businesses', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer ' + token
  },
  body: JSON.stringify({
    name: 'My Store',
    niche: 'E-commerce',
    targetAudience: 'Millennials'
  })
});

const data = await response.json();
console.log(data);
```

---

## 📞 Support

- Email: support@lkll.neocities.org
- Issues: https://github.com/uimasters/tropic/issues
- Docs: lkll.neocities.org/docs
