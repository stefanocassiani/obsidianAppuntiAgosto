### ✅ **Da attivare**

1. **Debug USB**  
    📌 _Fondamentale._  
	    Permette la comunicazione tra il tuo dispositivo Android e il computer via ADB (Android Debug Bridge), necessario per eseguire e fare debug delle app.
    
2. **Visualizza tocchi / Posizione puntatore**  
    Utile per testare gesti touch e verificare il corretto riconoscimento nell'app.
    
3. **Limita processi in background → Nessun processo in background (facoltativo)**  
    Per testare come la tua app si comporta con poche risorse o quando viene sospesa.
    
4. **Non mantenere attività**  
    Questo forza la distruzione delle attività appena l'utente le lascia. Utile per trovare bug legati al ciclo di vita delle attività.
    
5. **Mostra aggiornamenti layout**  
    Evidenzia i cambiamenti nei layout della UI – utile per il debug grafico.
    
6. **Forza rendering GPU (se disponibile)**  
    Costringe il sistema a usare la GPU per il rendering, utile per test di performance grafica.
    
7. **Profilazione GPU (opzionale)**  
    Mostra grafici delle prestazioni del rendering sullo schermo. Utile per ottimizzare la UI.
    
8. **Velocità animazioni → Scala animazione finestra / transizione / durata animatore → 0.5x o Off**  
    Per velocizzare i test riducendo o eliminando le animazioni.