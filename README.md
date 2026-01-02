# Devanagari Syllabifier

A web application to segment Devanagari (Hindi) words into syllables using a BiLSTM+CRF model.

## Features

- Segment Devanagari words into syllables
- Transliteration: Type in English (e.g., "bharat") → auto-converts to Devanagari (भारत)
- Real-time preview as you type
- Clean neobrutalist UI

## Project Structure

```
hyphenification-and-syllabification-of-indian-scripts/
├── frontend/          # React + Vite (Vercel)
│   ├── src/
│   │   ├── App.jsx
│   │   └── App.css
│   └── package.json
│
├── server/            # FastAPI (Render)
│   ├── app.py         # API endpoints
│   ├── src/           # ML inference code
│   ├── models/        # Trained BiLSTM+CRF model
│   └── requirements.txt
│
├── .env.example       # Environment variables
└── README.md
```

## API Usage

```bash
curl -X POST https://devanagari-syllabifier-api.onrender.com/segment \
  -H "Content-Type: application/json" \
  -d '{"word": "भारत"}'
```

Response:
```json
{
  "word": "भारत",
  "syllables": ["भा", "रत"],
  "hyphenated": "भा-रत",
  "count": 2
}
```
## Tech Stack

- **Frontend**: React, Vite, CSS
- **Backend**: FastAPI, Uvicorn
- **ML**: PyTorch, scikit-learn, BiLSTM+CRF