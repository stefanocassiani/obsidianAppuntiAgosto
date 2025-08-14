## 🌟 Community Plugins top-pick

1. **Dataview**
    
    - **Perché:** trasforma le note in un database interrogabile con query; perfetto per dashboard e report.
        
2. **Tasks**
    
    - **Perché:** gestisci to-do e scadenze con sintassi Markdown + filtri personalizzati.
        
3. **Periodic Notes**
    
    - **Perché:** crea automaticamente note giornaliere, settimanali, mensili; integrato con Calendar.
        
4. **Templater**
    
    - **Perché:** estende “Templates” con JavaScript e variabili dinamiche (date, conteggi, API esterne).



Ecco una dritta pratica per cominciare subito a sperimentare ciascuno di questi plugin:

---

### 1. Dataview

**Dritta:** Crea una tabella delle tue note con front-matter strutturato.

- **Step 1:** In ogni nota aggiungi in cima un blocco YAML, es.:
    
    yaml
    
    CopiaModifica
    
    `--- titolo: "Progetto AI" stato: "in corso" completato: false ---`
    
- **Step 2:** In una nota qualsiasi, inserisci questa query:
    
    markdown
    
    CopiaModifica
    
    ` ```dataview table titolo, stato from "" where completato = false sort stato asc `
    
    nginx
    
    CopiaModifica
    
    `Otterrai una tabella con tutte le note non completate.`  
    

---

### 2. Tasks

**Dritta:** Scrivi i task in Markdown e usane le query per filtrarli.

- **Step 1:** Nelle note aggiungi task così:
    
    markdown
    
    CopiaModifica
    
    `- [ ] Definire requisiti progetto - [x] Creare Vault Obsidian`
    
- **Step 2:** In una nota “Dashboard” crea una lista dinamica:
    
    markdown
    
    CopiaModifica
    
    ` ```tasks not done path includes "Progetti" `
    
    css
    
    CopiaModifica
    
    ``Vedrai solo i task non ancora fatti nelle note della cartella `Progetti`.``  
    

---

### 3. Periodic Notes

**Dritta:** Automatica creazione di note giornaliere tramite front-matter e comandi rapidi.

- **Step 1:** Configura in Settings → Periodic Notes:
    
    - Cartella “Daily notes”: `Daily`
        
    - Template file: `Templates/Daily.md`
        
- **Step 2:** Crea il template `Templates/Daily.md` con:
    
    markdown
    
    CopiaModifica
    
    `--- tags: [giornaliero] date: {{date:YYYY-MM-DD}} --- # Diario del {{date:DD/MM/YYYY}}`
    
- **Step 3:** Usa il comando (Command Palette → “Open daily note”) o la scorciatoia per generare la nota del giorno con il template precompilato.
    

---

### 4. Templater

**Dritta:** Usa variabili e snippet di JavaScript per contenuti dinamici.

- **Step 1:** Crea nella cartella `Templates` un file `ProjectTemplate.md`:
    
    markdown
    
    CopiaModifica
    
    `# Progetto: <% tp.file.title() %> **Creato il:** <% tp.date.now("YYYY-MM-DD", 0) %>`
    
- **Step 2:** In una nuova nota richiamalo con il comando “Insert template” → `ProjectTemplate`.
    
- **Step 3 (avanzato):** Aggiungi uno script JS personalizzato, es.:
    
    js
    
    CopiaModifica
    
    ``module.exports = async (tp) => {   const tasksLeft = await tp.user.run("countIncompleteTasks");   return `Ti rimangono **${tasksLeft}** task da completare`; };``
    
    e poi inseriscilo con `<% tp.user.countIncompleteTasks() %>`.
    

---

Con queste linee guida rapide inizierai a vedere subito i vantaggi di ciascun plugin. Buon divertimento con il tuo vault Obsidian!