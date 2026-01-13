# GigFlow – Mini Freelance Marketplace Platform

GigFlow is a MERN stack mini freelance marketplace built as part of the Full Stack Development Internship assignment at ServiceHive.

The platform allows clients to post gigs, freelancers to bid on them, and clients to hire one freelancer per gig with proper status handling.

---

## 🚀 Tech Stack

### Frontend
- React
- React Router
- Axios
- Inline CSS styling

### Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcryptjs

---

## 🔐 Authentication & Roles

- Users can register and login securely.
- Two roles are supported:
  - **Client**
  - **Freelancer**
- Role-based redirection after login:
  - Client → Client Dashboard
  - Freelancer → Freelancer Dashboard
- JWT token stored in localStorage.
- Logout clears authentication data.

---

## 🧾 Features Implemented

### 👤 Client Features
- Register & login as Client
- Create new gigs with:
  - Title
  - Description
  - Budget
- View all gigs created by the client
- View bids for a specific gig
- Hire one freelancer for a gig
- Gig status changes from `open` → `assigned`

### 🧑‍💻 Freelancer Features
- Register & login as Freelancer
- View all **open** gigs
- Place bids on gigs with:
  - Price
  - Message
- See bid status (`pending`, `hired`, `rejected`)
- Cannot bid on already assigned gigs

---

## 💼 Bidding & Hiring Logic (Core Requirement)

- Multiple freelancers can place bids on a gig.
- Client can hire **only one** freelancer per gig.
- When a freelancer is hired:
  - Selected bid → `hired`
  - All other bids → `rejected`
  - Gig status → `assigned`
- Assigned gigs no longer appear in freelancer dashboard.
- Re-hiring or multiple hiring is prevented.

---

## 🏆 Bonus 

- Secure hiring logic that prevents multiple hires for the same gig.
- Business-rule–based race-condition prevention using gig status checks.


---

## 📡 API Endpoints

### Auth
- `POST /api/auth/register`
- `POST /api/auth/login`

### Gigs
- `POST /api/gigs`
- `GET /api/gigs`

### Bids
- `POST /api/bids`
- `GET /api/bids/:gigId`
- `PATCH /api/bids/:bidId/hire`

---

## 🛠️ Setup Instructions

### 1. Clone the Repository
```bash
git clone 
cd gigflow
