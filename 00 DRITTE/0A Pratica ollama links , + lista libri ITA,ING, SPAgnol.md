

dritte 1:
- **"AI this, AI that" → È tutta una bolla**  
    Ci sono troppe startup e progetti che infilano l’etichetta “AI” nei loro prodotti anche quando non c’è un vero collegamento con l’intelligenza artificiale. Lo fanno solo per attirare l’attenzione degli investitori (VC — venture capital).
    
- **Attenzione alle “false competenze”**  
    Limitarsi a usare modelli AI già pronti (esposti come API o libreria) o a scrivere prompt ben fatti non è sufficiente per diventare un esperto o essere competitivo in questo settore. È un approccio superficiale.
    
- **Il vero lavoro di AI richiede basi solide**  
    Se vuoi davvero fare AI in modo serio e a lungo termine, dovresti studiare:
    
    - **Statistica applicata ai prodotti**
        
    - **PLM** (Product Lifecycle Management — gestione del ciclo di vita di un prodotto, anche in ottica dati/AI)
        
    - **Quant** (Quantitative analysis — l’analisi quantitativa è il “prossimo grande trend”)
        
- **Le fondamenta non passeranno di moda**  
    Le discipline “storiche” dell’AI — **Machine Learning (ML)**, **Deep Learning (DL)** e **Data Science (DS)** — continueranno a rimanere centrali e rilevanti.  
    Al contrario, certe mode recenti (come il feticismo per LLM e prompt engineering spacciati come “rivoluzione totale”) rischiano di essere temporanee.

dritta 2:
Non cercare di fare machine learning pesante. Imparare tutto questo richiederà anni e un sacco di sforzo. E dovrai competere con persone che hanno esperienza reale nel ML.

Invece, costruisci qualche app GPT/Stable Diffusion/<inserisci altro modello open source o API> e mettile in produzione. Imparerai moltissimo.

Se ti intervistassi e dimostrassi (1) solide competenze di ingegneria del software, (2) qualche prodotto AI in cui dimostri chiaramente di saper pensare al prodotto e non solo all’ingegneria, e (3) tanta determinazione, ti assumerei in un secondo.

Stiamo testando un programma di formazione per far crescere ingegneri del software in ingegneri AI e questo è il nostro programma di studi come riferimento:

- Generazione di immagini  
    Modelli open source e closed source, migliori prodotti generativi di immagini, Stable Diffusion, Controlnet, Roop, Guardrails, deployment serverless, Replicate, trucchi e consigli per la produzione
    
- Ingegneria del software assistita da AI  
    Copilot, Cursor, Coderabbit, Aider
    
- LLMs  
    API GPT, embeddings, RAG, database vettoriali, valutazioni, monitoraggio, sicurezza, war stories


https://www.freecodecamp.org/news/tag/ollama/

https://www.freecodecamp.org/news/tag/ollama/

https://www.reddit.com/r/ollama/comments/1ibhxvm/guide_to_installing_and_locally_running_ollama/?tl=it

https://www.reddit.com/r/ollama/search/?q=Ollama+UIs&cId=db9cec72-08df-4653-9f90-75fef40719ad&iId=7c1b71c8-8ec9-4a48-a355-360ba7efe6cf

https://www.reddit.com/r/ollama/comments/1ki7x1s/new_very_simple_ui_for_ollama/



chrome extensio per ollama ui
https://chromewebstore.google.com/detail/page-assist-a-web-ui-for/jfgfiigpkhlkbnfnbobbkinehhfdhndo
repo:
https://github.com/n4ze3m/page-assist

LISTA DI TUTORIAL
https://www.reddit.com/r/ollama/search/?q=tutorial&cId=36c190ee-041c-4f59-a4ad-cac57aea6bb9&iId=fb0a2b43-3aa2-4e7a-80ab-575906ee5456


Ecco una lista completa con le descrizioni di Ollama dedicate agli sviluppatori software, affiancate dai link diretti alle risorse più utili per approfondire e iniziare a usare la piattaforma:

- **Ollama**: framework leggero per eseguire modelli di linguaggio locali di grandi dimensioni (LLM) come Llama 2, Code Llama, Mistral e altri.
    
    - Documentazione ufficiale principale: [https://ollama.com](https://ollama.com/)[](https://ollama.com/)
    - Docker https://hub.docker.com/r/ollama/ollama
        
- **Documentazione tecnica e guida rapida (Quickstart)**: istruzioni base su come scaricare, eseguire e personalizzare modelli con Ollama.
    
    - Quickstart ufficiale: [https://ollama.readthedocs.io/en/quickstart/](https://ollama.readthedocs.io/en/quickstart/)[](https://ollama.readthedocs.io/en/quickstart/)
        
- **API REST di Ollama**: endpoint per interagire programmaticamente con i modelli, tra cui generazione di completamenti, chat, gestione modelli e streaming delle risposte.
    
    - Documentazione API REST dettagliata: [https://ollama.readthedocs.io/en/api/](https://ollama.readthedocs.io/en/api/)[](https://ollama.readthedocs.io/en/api/)
        
    - API Postman: [https://www.postman.com/postman-student-programs/ollama-api/documentation/suc47x8/ollama-rest-api](https://www.postman.com/postman-student-programs/ollama-api/documentation/suc47x8/ollama-rest-api)[](https://www.postman.com/postman-student-programs/ollama-api/documentation/suc47x8/ollama-rest-api)
        
- **SDK Ollama per Python**: libreria Python per integrare facilmente Ollama con pochi comandi, supporta esecuzione di modelli, definizione di funzioni di supporto e altro.
    
    - Guida passo passo Python: [https://www.cohorte.co/blog/using-ollama-with-python-step-by-step-guide](https://www.cohorte.co/blog/using-ollama-with-python-step-by-step-guide)[](https://www.cohorte.co/blog/using-ollama-with-python-step-by-step-guide)
        
    - Repositry ufficiale e libreria Python: [https://github.com/ollama/ollama-python](https://github.com/ollama/ollama-python)[](https://github.com/ollama/ollama-python)
        
    - PyPI ollama-python package: [https://pypi.org/project/ollama-python/](https://pypi.org/project/ollama-python/)[](https://pypi.org/project/ollama-python/)
        
- **SDK Ollama per JavaScript**: libreria JS per accedere alle API Ollama da progetti JavaScript o Node.js, con esempi di uso e supporto per streaming delle risposte.
    
    - Repository ufficiale JS: [https://github.com/ollama/ollama-js](https://github.com/ollama/ollama-js)[](https://github.com/ollama/ollama-js)
        
    - Wrapper JS di terze parti: [https://github.com/dditlev/ollama-js-client](https://github.com/dditlev/ollama-js-client)[](https://github.com/dditlev/ollama-js-client)
        
- **CLI Ollama**: terminale e comando per gestire modelli, eseguire modelli, creare modelli personalizzati, scaricare modelli, avviare sessioni interattive.
    
    - Guida tutorial CLI: [https://www.hostinger.com/tutorials/ollama-cli-tutorial](https://www.hostinger.com/tutorials/ollama-cli-tutorial)[](https://www.hostinger.com/tutorials/ollama-cli-tutorial)
        
- **Supporto GPU e ottimizzazione**: guida e consigli su come usare GPU NVIDIA e AMD per migliorare prestazioni di Ollama in locale.
    
    - Guida supporto AMD GPU: [https://www.amd.com/en/developer/resources/technical-articles/running-llms-locally-on-amd-gpus-with-ollama.html](https://www.amd.com/en/developer/resources/technical-articles/running-llms-locally-on-amd-gpus-with-ollama.html)[](https://www.amd.com/en/developer/resources/technical-articles/running-llms-locally-on-amd-gpus-with-ollama.html)
        
    - Ottimizzazione Ubuntu per GPU non ufficialmente supportate: [https://www.conroyp.com/articles/running-ollama-ubuntu-unsupported-amd-gpu-performance-guide](https://www.conroyp.com/articles/running-ollama-ubuntu-unsupported-amd-gpu-performance-guide)[](https://www.conroyp.com/articles/running-ollama-ubuntu-unsupported-amd-gpu-performance-guide)
        
- **Output strutturati e supporto tool avanzati**: possibilità di definire output in schemi JSON e usare chiamate a funzioni esterne per potenziare i modelli.
    
    - Blog su output strutturati: [https://ollama.com/blog/structured-outputs](https://ollama.com/blog/structured-outputs)[](https://ollama.com/blog/structured-outputs)
        
    - Blog tool support: [https://ollama.com/blog/tool-support](https://ollama.com/blog/tool-support)[](https://ollama.com/blog/tool-support)
        
- **Documentazione generale dettagliata**: raccolta completa di guide, riferimento API, esempi, installazione e uso su diversi sistemi operativi.
    
    - Pagina docs principale: [https://ollama.readthedocs.io/en/](https://ollama.readthedocs.io/en/)[](https://ollama.readthedocs.io/en/)




lista libri:
## Libri in italiano su Ollama

- **Come usare LLM in locale con Ollama e Python** (articolo-guida approfondita)
    
    - Guida pratica per sviluppatori su come utilizzare Ollama, strumento open source per eseguire modelli linguistici (LLM) locali.
        
    - Spiega cosa è Ollama, come funziona da terminale, integrazione con Python e personalizzazioni di modelli.
        
    - Link utile: [https://www.diariodiunanalista.it/posts/llm-in-locale-usare-ollama-in-python/](https://www.diariodiunanalista.it/posts/llm-in-locale-usare-ollama-in-python/)
        
- **Eseguire un modello LLM in locale con Ollama - ClaudioBattaglino.it**
    
    - Panoramica su Ollama come motore multipiattaforma per eseguire LLM in locale, con esempi d’uso e confronto con strumenti simili.
        
    - Ideale per chi vuole iniziare a sperimentare senza GUI complesse, sfruttando API e CLI.
        
    - Link: [https://www.claudiobattaglino.it/eseguire-un-modello-llm-in-locale-con-ollama/](https://www.claudiobattaglino.it/eseguire-un-modello-llm-in-locale-con-ollama/)
        
- **DeepSeek R1: Guida Completa per Far Girare l'IA in Locale nel 2025**
    
    - Contiene sezioni introduttive su Ollama, utile per chi vuole capire rapidamente quanto Ollama semplifica l’uso di LLM in locale.
        
    - Descrive casi d’uso pratici come coding assistant, analisi testo e automazione.
        
    - Link: [https://mautoblog.com/posts/installare-deepseek-in-locale-con-ollama-guida-2025/](https://mautoblog.com/posts/installare-deepseek-in-locale-con-ollama-guida-2025/)
        

---

## Books in English about Ollama

1 

https://www.packtpub.com/en-us/product/harnessing-ollama-create-secure-local-llm-solutions-with-python-9781837020058


- **Ollama in Action: Building Safe, Private AI with Ollama** (Leanpub)
    
    - Libro completo che guida passo passo all’uso di Ollama per eseguire LLM sul proprio hardware, focalizzandosi sulla privacy e sicurezza.
        
    - Copre setup, uso CLI, Python SDK, creazione di agenti, valutazione automatica e casi d’uso avanzati.
        
    - Link: [https://leanpub.com/ollama/read](https://leanpub.com/ollama/read)
        
- **Ollama Fast Track: A Hands-On Guide to Building Local LLM Powered Applications** by Eric Chandler Jr
    
    - Manuale pratico veloce per sviluppatori interessati a sfruttare Ollama per applicazioni LLM locali.
        
    - Spiega come scaricare, gestire e personalizzare modelli, con esempi di codice.
        
    - Link: [https://bookshop.org/p/books/ollama-fast-track-a-hands-on-guide-to-building-local-llm-powered-applications-jr-eric-chandler/22516768](https://bookshop.org/p/books/ollama-fast-track-a-hands-on-guide-to-building-local-llm-powered-applications-jr-eric-chandler/22516768)
        
- **Harnessing Ollama - Create Secure Local LLM Solutions with Python**
    
    - Libro tecnico dedicato a sviluppatori Python per creare soluzioni sicure LLM con Ollama, puntando su privacy e controllo dei dati.
        
    - Ideale per approcci professionali e personalizzazione avanzata.
        
    - Link: [https://www.packtpub.com/en-us/product/harnessing-ollama-create-secure-local-llm-solutions-with-python-9781837020058](https://www.packtpub.com/en-us/product/harnessing-ollama-create-secure-local-llm-solutions-with-python-9781837020058)
        

---

## Libros en español sobre Ollama

- **¿Qué es Ollama? Principales características y modelos - Hostinger**
    
    - Guía detallada que explica qué es Ollama, cómo funciona, principales modelos y casos de uso como chatbots locales, investigación privada y personalización.
        
    - Enfocado en usuarios que buscan ejecutar LLM sin depender de la nube.
        
    - Link: [https://www.hostinger.com/es/tutoriales/que-es-ollama](https://www.hostinger.com/es/tutoriales/que-es-ollama)
        
- **Ollama, empezando con la IA local - Blog Bujarra.com**
    
    - Artículo introductorio en español que muestra cómo usar Ollama para correr modelos de lenguaje grandes localmente, con beneficios y casos prácticos.
        
    - Recomendado para desarrolladores y entusiastas de IA.
        
    - Link: [https://www.bujarra.com/ollama-empezando-con-la-ia-local/](https://www.bujarra.com/ollama-empezando-con-la-ia-local/)
        
- **Pequeña guía de uso y modelos importantes de Ollama (PDF)**
    
    - Documento en PDF con una guía rápida sobre uso básico de Ollama y los modelos más importantes compatibles.
        
    - Útil para empezar a manejar la plataforma con ejemplos concretos.
        
    - Link: [https://es.scribd.com/document/890290049/ollama](https://es.scribd.com/document/890290049/ollama)
        

---

Questi libri e risorse coprono aspetti fondamentali di Ollama come esecuzione di LLM in locale, personalizzazione tramite Modelfile, uso via CLI, API e SDK, oltre a casi d'uso pratici come chatbot, ricerca protetta e automazione.