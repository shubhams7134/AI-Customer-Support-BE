# AI Customer Support Backend

Backend API for AI-powered ticket management system with automatic categorization, priority assignment, and smart moderator matching.

## 🚀 Tech Stack

- **Node.js** + **Express.js** - RESTful API
- **MongoDB** + **Mongoose** - Database
- **JWT** - Authentication
- **Inngest** - Background job processing
- **Google Gemini AI** - Ticket analysis
- **Nodemailer** - Email notifications

## 📋 Features

- ✅ User authentication with JWT
- ✅ Role-based access control (User, Moderator, Admin)
- ✅ AI-powered ticket categorization
- ✅ Automatic priority assignment
- ✅ Skill-based moderator matching
- ✅ Background job processing
- ✅ Email notifications

## ⚙️ Setup

### 1. Install Dependencies

```bash
npm install
```

### 2. Environment Variables

Copy `.env.sample` to `.env` and fill in your values:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_min_32_chars
GEMINI_API_KEY=your_google_gemini_api_key
MAILTRAP_SMTP_HOST=smtp_host
MAILTRAP_SMTP_PORT=smtp_port
MAILTRAP_SMTP_USER=smtp_user
MAILTRAP_SMTP_PASS=smtp_password
APP_URL=http://localhost:3000
PORT=3000
```

### 3. Run Development Server

```bash
npm run dev
```

Server starts at: http://localhost:3000

### 4. Run Inngest Dev Server (separate terminal)

```bash
npm run inngest-dev
```

Inngest UI: http://localhost:8288

## 📡 API Endpoints

### Authentication
- `POST /api/auth/signup` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/users` - Get all users (Admin only)
- `POST /api/auth/update-user` - Update user role/skills (Admin only)

### Tickets
- `POST /api/tickets` - Create ticket
- `GET /api/tickets` - Get all tickets
- `GET /api/tickets/:id` - Get ticket by ID

### Inngest
- `GET /api/inngest` - Inngest webhook endpoint

## 🚀 Deployment

### Deploy to Render

1. Push code to GitHub
2. Go to [Render Dashboard](https://dashboard.render.com)
3. Create new Web Service
4. Connect your repository
5. Set environment variables
6. Deploy!

**Build Command:** `npm install`  
**Start Command:** `node index.js`

### Configure Inngest (Production)

1. Go to [Inngest Dashboard](https://app.inngest.com)
2. Add sync URL: `https://your-backend.onrender.com/api/inngest`
3. Copy Event Key and Signing Key
4. Add to environment variables:
   - `INNGEST_EVENT_KEY`
   - `INNGEST_SIGNING_KEY`

## 📦 Scripts

- `npm run dev` - Start development server with nodemon
- `npm run inngest-dev` - Start Inngest dev server (local only)

## 🔧 Project Structure

```
ai-ticket-assistant/
├── controllers/      # Request handlers
├── models/          # Database schemas
├── routes/          # API routes
├── middlewares/     # Auth & validation
├── inngest/         # Background jobs
│   ├── client.js
│   └── functions/
├── utils/           # AI & email utilities
├── index.js         # App entry point
└── package.json
```

## 🛠️ Seed Data (Optional)

Populate database with sample data:

```bash
node seed-ecommerce-data.js
```

## 📝 License

MIT

