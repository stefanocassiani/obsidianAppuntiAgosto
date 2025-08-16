# 🤖 Custom Chatbot Platform

## 🚀 Panoramica
**Custom Chatbot Platform** è un'applicazione SaaS che consente agli utenti di:
- Creare e personalizzare chatbot basati su AI
- Integrare chatbot in siti web e app
- Gestire conversazioni e analytics
- Collegare modelli AI esterni (OpenAI, Hugging Face, ecc.)

---

## 🏗 Stack Tecnologico

| Componente        | Tecnologia |
|-------------------|------------|
| **Frontend**      | Next.js (React) + Tailwind CSS |
| **Backend/API**   | API Routes Next.js (serverless su Vercel) |
| **AI Engine**     | OpenAI GPT-4 / Hugging Face Transformers |
| **Database**      | Supabase (PostgreSQL) |
| **File Storage**  | Supabase Storage / AWS S3 |
| **Autenticazione**| Clerk / Supabase Auth |
| **Pagamenti**     | Stripe |
| **Hosting**       | Vercel |

---

## 📂 Struttura del Progetto

```
/project-root
│── /pages
│   ├── index.tsx               # Landing page
│   ├── dashboard.tsx           # Dashboard utente
│   ├── chatbot-builder.tsx     # Pagina creazione chatbot
│   └── api/
│       ├── createBot.ts        # Endpoint creazione bot
│       ├── getBot.ts           # Endpoint recupero bot
│       ├── chat.ts             # Endpoint conversazioni
│
│── /components
│   ├── Navbar.tsx
│   ├── ChatbotPreview.tsx
│   ├── ChatInterface.tsx
│   └── AnalyticsDashboard.tsx
│
│── /lib
│   ├── openai.ts               # Funzioni per chiamate AI
│   ├── db.ts                   # Connessione Supabase
│   └── analytics.ts            # Gestione dati di utilizzo
│
│── /styles
│   └── globals.css
│
│── package.json
│── README.md
```

---

## 🔑 Funzionalità

- **Registrazione/Login**
- **Creazione chatbot personalizzati**
- **Integrazione con siti web tramite iframe/script**
- **Supporto a più modelli AI**
- **Analytics delle conversazioni**
- **Esportazione conversazioni**
- **Piani di abbonamento** (Stripe)

---

## ⚙️ Setup e Deploy

### 1. Clona il repository
```bash
git clone https://github.com/tuo-utente/custom-chatbot-platform.git
cd custom-chatbot-platform
```

### 2. Installa le dipendenze
```bash
npm install
```

### 3. Configura variabili ambiente (`.env.local`)
```env
OPENAI_API_KEY=your_openai_api_key
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_key
STRIPE_SECRET_KEY=your_stripe_secret
```

### 4. Avvia in locale
```bash
npm run dev
```

### 5. Deploy su Vercel
- Collega il repo a Vercel
- Imposta le variabili ambiente
- Deploy automatico ad ogni push

---

## 📌 Roadmap
- [ ] MVP con creazione e chat funzionante
- [ ] Integrazione modelli multipli
- [ ] Dashboard analytics avanzata
- [ ] Esportazione e importazione bot
- [ ] Marketplace di chatbot

---

## 📄 Licenza
MIT License
