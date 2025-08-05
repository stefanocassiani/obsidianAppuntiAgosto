# Gestione Git nel Vault Obsidian

Questo Vault è configurato per sincronizzare automaticamente le modifiche usando Git tramite il plugin **Obsidian Git**.

---

## Funzionalità attive

- **Commit automatici** ogni 60 minuti con messaggio:
-

  > Auto commit - {{date}} {{time}}

- **Push automatico** dopo ogni commit.

- **Pull automatico** all’apertura del Vault per sincronizzare eventuali aggiornamenti remoti.

- **Push automatico** alla chiusura del Vault.

---

## Comandi Git disponibili da Obsidian

Dal Command Palette (`Ctrl+P` o `Cmd+P`) puoi eseguire manualmente:

- `Git: Commit all changes`  
- `Git: Push`  
- `Git: Pull`

---

## Configurazione

- Il plugin **Obsidian Git** è installato e abilitato.  
- Per evitare richieste continue di login, è configurato il Credential Manager di Windows o SSH.

---

## Note utili

- Se si utilizza HTTPS per GitHub, è necessario un [Personal Access Token (PAT)](https://github.com/settings/tokens) configurato e memorizzato.  
- Per problemi di autenticazione o configurazioni avanzate, consultare la documentazione ufficiale del plugin e di GitHub.

---

## Contatti

Per dubbi o miglioramenti della configurazione, contattare Stefano Cassiani.

---

*Questo file è generato automaticamente per facilitare la gestione e manutenzione del Vault.*
