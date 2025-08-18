## **DIAGRAMMA ARCHITETTURALE - DESCRIZIONE VISIVA**

### **LIVELLO 1: PRESENTAZIONE (Frontend)**

```
┌─── VUE.JS APPLICATION ───┐
│  • Dashboard principale   │
│  • Moduli: Inventory,     │
│    Orders, CRM, Reports   │
│  • JWT Token storage     │
│  • API calls via Axios   │
└─────────────────────────┘
           ↕️ HTTPS/REST
```

### **LIVELLO 2: API GATEWAY & SECURITY**

```
┌─── ASP.NET CORE WEB API ───┐
│  🔐 JWT Authentication     │
│  🏢 Tenant Context Filter  │
│  📊 Request/Response Log    │
│  ⚡ Rate Limiting          │
└───────────────────────────┘
           ↕️ HTTP Pipeline
```

### **LIVELLO 3: BUSINESS LOGIC (Modular Monolith)**

```
┌─── CORE MODULES ───────────────────┐
│                                    │
│  📦 INVENTORY      👥 CRM          │
│   • Product CRUD    • Customers    │
│   • Stock levels    • Suppliers    │
│   • Categories      • Contacts     │
│                                    │
│  📋 ORDERS         📊 REPORTING    │
│   • Order cycle     • Dashboards   │
│   • Invoicing       • Analytics    │
│   • Payments        • Data Export  │
│                                    │
│  🔧 SHARED SERVICES ──────────────  │
│   • TenantService (Row-level)      │
│   • AuditService (Change tracking) │
│   • NotificationService            │
└────────────────────────────────────┘
           ↕️ Entity Framework Core
```

### **LIVELLO 4: DATA ACCESS**

```
┌─── REPOSITORY PATTERN ───┐
│  🏪 Generic Repository   │
│  📝 Unit of Work        │
│  🔍 Tenant-aware queries │
│  📊 CQRS Commands/Query  │
└─────────────────────────┘
           ↕️ SQL Queries
```

### **LIVELLO 5: DATABASE**

```
┌─── POSTGRESQL ────────────┐
│  📋 TABELLE PRINCIPALI:   │
│                           │
│  Users (TenantId)         │
│  Products (TenantId)      │
│  Orders (TenantId)        │
│  Customers (TenantId)     │
│  AuditLog (TenantId)      │
│                           │
│  🔒 ROW LEVEL SECURITY:   │
│  WHERE TenantId = @tenant │
└───────────────────────────┘
```

### **LIVELLO 6: AI/ML FOUNDATION (Future-ready)**

```
┌─── DATA PIPELINE (minimal) ───┐
│  📈 Business Metrics          │
│  📊 Sales Aggregations        │
│  🎯 Customer Behavior Log     │
│  ⚠️  Anomaly Detection Data   │
│                               │
│  🧠 AI EXTENSION POINTS:      │
│   • Sales Forecasting API    │
│   • Inventory Optimization   │
│   • Customer Insights        │
└───────────────────────────────┘
```

## **FLUSSO DATI OPERATIVO:**

**1. USER REQUEST:** `Vue.js → JWT Header → API Controller`

**2. SECURITY:** `JWT Validation → Tenant Context → Authorization`

**3. BUSINESS:** `MediatR Command → Business Logic → Repository`

**4. DATA:** `EF Core → SQL with TenantId Filter → PostgreSQL`

**5. RESPONSE:** `DTO Mapping → JSON → Vue.js Component Update`

## **VANTAGGI ARCHITETTURA SCELTA:**

✅ **Costi minimi**: Single database, row-level security ✅ **Scalabilità**: Modular monolith → microservices split possibile ✅ **Sviluppo rapido**: JWT semplice, PostgreSQL versatile  
✅ **AI-ready**: Data pipeline foundation integrata ✅ **Cloud-agnostic**: PostgreSQL + Docker compatibility