# 📊 AI-Powered Data Insights

## 🚀 Panoramica
**AI-Powered Data Insights** è un'applicazione SaaS che consente agli utenti di:
- Caricare dataset in formato `.csv`
- Analizzare i dati tramite modelli di intelligenza artificiale
- Generare grafici interattivi e report testuali
- Esportare i risultati in PDF o Excel

---

## 🏗 Stack Tecnologico

| Componente        | Tecnologia |
|-------------------|------------|
| **Frontend**      | Next.js (React) + Tailwind CSS |
| **Backend/API**   | API Routes Next.js (serverless su Vercel) |
| **AI Engine**     | OpenAI GPT-4 / Hugging Face Transformers |
| **Data Processing** | Python (Pandas, NumPy) via API serverless |
| **Database**      | Supabase (PostgreSQL) |
| **File Storage**  | Supabase Storage o AWS S3 |
| **Grafici**       | Plotly.js / Chart.js |
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
│   ├── upload.tsx              # Pagina caricamento CSV
│   └── api/
│       ├── upload.ts           # Endpoint upload file
│       ├── analyze.ts          # Endpoint analisi AI
│       ├── charts.ts           # Endpoint generazione grafici
│
│── /components
│   ├── Navbar.tsx
│   ├── FileUploader.tsx
│   ├── ChartViewer.tsx
│   └── ReportViewer.tsx
│
│── /lib
│   ├── openai.ts               # Funzioni per chiamate OpenAI
│   ├── db.ts                   # Connessione Supabase
│   └── charts.ts               # Generazione grafici
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
- **Upload CSV** con validazione formato
- **Analisi AI**:
  - Statistiche base (conteggi, medie, deviazioni standard)
  - Insight avanzati (correlazioni, trend, anomalie)
  - Suggerimenti business e azioni consigliate
- **Visualizzazione grafica interattiva**
- **Esportazione report**
- **Piano free & premium** (Stripe per abbonamenti)

---

## ⚙️ Setup e Deploy

### 1. Clona il repository
```bash
git clone https://github.com/tuo-utente/ai-data-insights.git
cd ai-data-insights
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
- [ ] MVP con upload + insight AI
- [ ] Grafici interattivi
- [ ] Esportazione report PDF
- [ ] Piani di abbonamento
- [ ] Dashboard personalizzata per utente

---

## 📄 Licenza
MIT License
