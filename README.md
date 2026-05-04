# AI SEO Content Generator

A SaaS platform that automates the generation of SEO-optimized blog posts using the Gemini API.

## ✨ Features

- **Keyword-to-Article:** Generate full articles from a single keyword
- **Tone Customization:** Professional, Conversational, Friendly, or Technical tones
- **SEO Ready:** Automatically generates H1, H2, meta descriptions, and CTAs
- **Length Control:** Adjustable word count (100-5000 words)
- **FastAPI Backend:** High-performance API with automatic validation
- **Modern Frontend:** Built with Next.js 14, Tailwind CSS, and TypeScript

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm
- Python 3.9+
- [Google Gemini API Key](https://aistudio.google.com/app/apikey)

### Backend Setup (Python)

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # Mac/Linux
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.env` file based on `.env.example`:
   ```bash
   cp .env.example .env
   ```

5. Add your Gemini API key to `.env`:
   ```
   GEMINI_API_KEY=your_actual_api_key_here
   ```

6. Run the server:
   ```bash
   python main.py
   ```

   The API will be available at `http://localhost:8000`

### Frontend Setup (Next.js)

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## 📡 API Documentation

### GET /

Health check endpoint.

**Response:**
```json
{
  "status": "online",
  "message": "AI SEO Content Generator API is running."
}
```

### POST /generate

Generate SEO-optimized blog content based on keyword and parameters.

**Request:**
- Method: `POST`
- Content-Type: `application/json`
- Body:
  ```json
  {
    "keyword": "digital marketing",
    "tone": "professional",
    "length": 1000
  }
  ```

**Request Schema:**
```typescript
{
  keyword: string;      // 2-200 characters, target SEO keyword
  tone?: string;        // Content tone (default: "professional")
  length?: number;      // Target word count 100-5000 (default: 1000)
}
```

**Response:**
```json
{
  "keyword": "digital marketing",
  "content": "# Digital Marketing Guide\n\n## Introduction\n...",
  "metadata": {
    "tone": "professional",
    "length": 1000
  },
  "status": "success"
}
```

## 📁 Project Structure

```
ai-seo-content-generator/
├── backend/
│   ├── main.py           # FastAPI application with validation
│   ├── requirements.txt  # Python dependencies
│   └── .env.example      # Environment variables template
├── frontend/
│   ├── app/             # Next.js App Router pages
│   ├── components/      # Reusable React components
│   └── package.json
├── LICENSE
└── README.md
```

