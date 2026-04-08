# SafeStay 🏠
### Trusted Student Housing & Storage Platform

> *Price-verified listings. Community trust scores. Built for students, by students.*

**Live Demo:** [https://safehost.onrender.com](https://safehost.onrender.com)  
**GitHub:** [https://github.com/AbhimanyuSingh-beep/safehost](https://github.com/AbhimanyuSingh-beep/safehost)

---

## The Problem

Students relocating near colleges face a broken system:

- Landlords charge **30–40% above market rates** with no accountability
- **No way to verify** if a listing is fairly priced
- **Zero transparency** on owner reputation or past complaints
- Fake listings with no community reviews or ratings

---

## Our Solution

SafeStay is a full-stack web platform that brings **transparency and trust** to student rentals through automated price verification and community-driven trust scores.

---

## Key Features

### Price Verification Engine
Listings priced **more than 15% above the market average** are automatically flagged. No manual reporting needed — the system catches it instantly on submission.

### Owner Trust Score
Every owner gets a dynamic trust score calculated as:

```
Trust Score = 50 (base)
            + (Average Rating × 10)
            + (Total Reviews × 5)
            − (Price Flags × 10)
```

A score above 70 = trustworthy. Below 40 = flagged owner.

### Community Reviews
Students can rate and review any listing from 1–5 stars with comments. Reviews are permanent and publicly visible.

### Housing & Storage
Covers both rental types — PG rooms, flats, and storage units — all in one place.

---

## Tech Stack

| Layer | Technology | Why |
|---|---|---|
| Frontend | HTML, CSS, JavaScript | Simple, runs in any browser |
| Backend | Node.js + Express | Lightweight, fast API server |
| Database | Neon PostgreSQL | Free cloud database, persistent |
| Hosting | Render | Auto-deploys from GitHub, free tier |
| Version Control | GitHub | Code storage and CI/CD trigger |

---

## Architecture

```
Browser (index.html)
      │
      │  HTTP requests
      ▼
Render Server (server.js / Express)
      │
      │  SQL queries
      ▼
Neon PostgreSQL Database
(owners, listings, reviews, price_flags)
```

---

## Database Schema

```sql
owners        → id, name, email
listings      → id, owner_id, type, title, price, market_average, price_flagged
reviews       → id, listing_id, owner_id, rating, comment
price_flags   → id, owner_id, listing_title
```

---

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | /api/owners | Fetch all owners |
| GET | /api/listings | Fetch all listings |
| POST | /api/listings | Add new listing (auto price-check) |
| GET | /api/reviews | Fetch all reviews |
| POST | /api/reviews | Submit a review |
| GET | /api/price_flags | Fetch all flagged listings |

---

## How to Run Locally

```bash
# Clone the repo
git clone https://github.com/AbhimanyuSingh-beep/safehost.git
cd safehost

# Install dependencies
npm install

# Add your Neon database URL
export DATABASE_URL="postgresql://user:password@..."

# Start the server
node server.js
```

Then open `http://localhost:3000` in your browser.

---

## Impact

- Protects students from predatory pricing
- Builds a verified community reputation system
- Works without login — completely open and accessible
- Scalable to any college campus in India

---

## Team

Built with ❤️ for students, at a hackathon.

---

*SafeStay — Because every student deserves a safe and fair home.*
