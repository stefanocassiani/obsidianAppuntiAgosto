1   https://chromewebstore.google.com/detail/claude-usage-tracker/knemcdpkggnbhpoaaagmjiigenifejfo

2

https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor



3 CHAT gpt

CLICCAQUI SOTTO
[[CHATGPTPy]]

Per ChatGPT, esistono script Python creati dalla community che permettono di monitorare il consumo di token nelle chiamate API, e puoi implementare notifiche personalizzate quando raggiungi un limite da te scelto.

Ecco cosa puoi fare:

- Usare la libreria ufficiale OpenAI Python SDK, che fornisce nella risposta API un campo `usage` con i token utilizzati nel prompt, nella risposta e totali.
    
- Con Python puoi sommare questi token consumati per tracciare il tuo utilizzo totale.
    
- Puoi scrivere uno script semplice che invia richieste a ChatGPT, conta i token consumati e ti notifica (via email, popup, console) quando superi il limite impostato.
    

Un esempio base di funzione Python per contare token da messaggi (usando la libreria tiktoken) è:

python

import tiktoken

def num_tokens_from_messages(messages, model="gpt-3.5-turbo-0301"):
    try:
        encoding = tiktoken.encoding_for_model(model)
    except KeyError:
        encoding = tiktoken.get_encoding("cl100k_base")
    tokens_per_message = 4
    tokens_per_name = -1
    num_tokens = 0
    for message in messages:
        num_tokens += tokens_per_message
        for key, value in message.items():
            num_tokens += len(encoding.encode(value))
            if key == "name":
                num_tokens += tokens_per_name
    num_tokens += 3
    return num_tokens


Puoi integrare questo conteggio nei tuoi script per monitorare il numero di token consumati.

Per esempi più completi, monitoraggio e notifiche personalizzate puoi vedere questo progetto Python molto utile:

- GitHub: [https://github.com/levysoft/chatgpt-token-cost-analysis](https://github.com/levysoft/chatgpt-token-cost-analysis)  
    Questo progetto estrae messaggi da esportazioni ChatGPT, calcola i token usati e stima i costi mensili.
    

Inoltre, molti user implementano script Python personalizzati per inviare notifiche email o messenger quando l'uso si avvicina a un limite definito.

Se vuoi, posso aiutarti a scrivere uno script base per monitorare token e inviarti avvisi personalizzati secondo un limite da te scelto. Vuoi che proceda?


5


Ecco uno script Python base per monitorare il consumo di token su ChatGPT usando l’API OpenAI e inviarti una notifica in console quando superi un limite da te impostato. Puoi integrare questo script con notifiche email o altre forme di alert se vuoi.

pythonimport openai
import tiktoken

# Imposta la tua API Key OpenAI
openai.api_key = "LA_TUA_API_KEY"

# Definisci il modello da usare
model = "gpt-4"

# Limite di token da non superare
token_limit = 10000

# Funzione per contare token da messaggi
def count_tokens(messages, model=model):
    try:
        encoding = tiktoken.encoding_for_model(model)
    except KeyError:
        encoding = tiktoken.get_encoding("cl100k_base")
    tokens_per_message = 4
    tokens_per_name = -1
    num_tokens = 0
    for message in messages:
        num_tokens += tokens_per_message
        for key, value in message.items():
            num_tokens += len(encoding.encode(value))
            if key == "name":
                num_tokens += tokens_per_name
    num_tokens += 3
    return num_tokens

# Funzione per inviare richiesta a ChatGPT e monitorare token
def ask_chatgpt(messages, total_tokens_used=0):
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages
    )
    usage = response["usage"]
    prompt_tokens = usage["prompt_tokens"]
    completion_tokens = usage["completion_tokens"]
    total_tokens = usage["total_tokens"]

    total_tokens_used += total_tokens

    print(f"Token usati in questa richiesta: {total_tokens}")
    print(f"Token totali usati finora: {total_tokens_used}")

    if total_tokens_used >= token_limit:
        print(f"ATTENZIONE: limite token di {token_limit} superato!")

    return response.choices[0].message["content"], total_tokens_used


# Esempio di uso
if __name__ == "__main__":
    total_tokens_used = 0
    messages = [
        {"role": "system", "content": "Sei un assistente utile."},
        {"role": "user", "content": "Riassumi questo testo per favore."}
    ]

    risposta, total_tokens_used = ask_chatgpt(messages, total_tokens_used)
    print("Risposta ChatGPT:", risposta)

Come funziona:

- Conta i token consumati per ogni chiamata a ChatGPT tramite il campo `usage`.
    
- Somma i token usati fino a quel momento.
    
- Avvisa in console quando supera il limite definito (qui 10.000 token, modificabile).
    
- Puoi espandere il sistema di notifiche per inviare email, messaggi, ecc.
    

Se vuoi, posso aiutarti a implementare un sistema di notifica via email o un’interfaccia grafica personalizzata. Fammi sapere!