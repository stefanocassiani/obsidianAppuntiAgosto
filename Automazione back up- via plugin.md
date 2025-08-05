
---

## 🔄 2. Automazione via plugin **Obsidian Git**

Il plugin **Obsidian Git** consente commit e push automatici **dentro Obsidian**, anche ogni X minuti o all’uscita.

### 🔧 Come attivarlo

1. Vai in **Settings → Obsidian Git**
    
2. Imposta:
    

#### ⏱ Auto-commit:

- **Enable auto-commit** → ✅
    
- **Commit message** →  
    `Auto commit - {{date}} {{time}}`
    
- **Auto-commit interval** → es. `60` (minuti)
    

#### ☁ Auto-push:

- **Auto-push after commit** → ✅
    

#### 🏁 All’uscita:

- **Pull changes on vault open** → ✅
    
- **Push on vault close** → ✅
    

### 🧠 Comandi utili

- `Git: Commit all changes`
    
- `Git: Push`
    
- `Git: Pull`
    

Puoi anche assegnarli a **hotkeys**!

---

### 💡 Quale usare?

|Opzione|Quando usarla|
|---|---|
|`.bat` file|Se vuoi controllo esterno da Windows o usi Notepad++ / terminale|
|Plugin Obsidian Git|Se lavori tutto da Obsidian e vuoi automazione nativa|

Vuoi anche un `README.md` Git-style da mettere nel Vault come progetto documentato?



## 🔄 Come attivare e configurare il plugin **Obsidian Git**

### 1. Installa il plugin

- Apri Obsidian
    
- Vai su **Settings (Impostazioni) → Community plugins**
    
- Cerca **Obsidian Git**
    
- Clicca su **Install** e poi su **Enable**
    

---

### 2. Configura il plugin

Vai su **Settings → Plugin options → Obsidian Git** e imposta i seguenti parametri:

|Impostazione|Valore consigliato|Descrizione|
|---|---|---|
|**Enable auto-commit**|✅ attivato|Attiva i commit automatici|
|**Commit message**|`Auto commit - {{date}} {{time}}`|Messaggio per i commit automatici|
|**Auto-commit interval**|`60` (minuti)|Ogni quanto tempo eseguire il commit automatico|
|**Auto-push after commit**|✅ attivato|Esegue automaticamente il push dopo commit|
|**Pull changes on vault open**|✅ attivato|Fa pull dei cambi remoti all’apertura vault|
|**Push on vault close**|✅ attivato|Fa push dei cambi remoti alla chiusura vault|

---

### 3. Usa i comandi Git da Obsidian

Dal **Command Palette** (Ctrl+P o Cmd+P) puoi cercare e usare comandi come:

- `Git: Commit all changes`
    
- `Git: Push`
    
- `Git: Pull`
    

---

### 4. (Opzionale) Assegna hotkeys ai comandi Git

- Vai in **Settings → Hotkeys**
    
- Cerca i comandi Git (es. `Git: Commit all changes`)
    
- Assegna scorciatoie da tastiera personalizzate
    

---

## 💡 Quale metodo scegliere?

| Metodo              | Quando usarlo                                                     |
| ------------------- | ----------------------------------------------------------------- |
| `.bat` file         | Se preferisci eseguire Git da Windows esternamente o da terminale |
| Plugin Obsidian Git | Se lavori principalmente dentro Obsidian e vuoi tutto automatico  |