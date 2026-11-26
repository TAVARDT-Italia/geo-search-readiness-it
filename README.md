<p align="center">
  <a href="https://ag.tavardt.com/it/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Auditor di Ottimizzazione per Motori Generativi (GEO)

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Ricerca%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/it/audit-visibilita-motori-ia/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Motore di verifica automatizzato per Generative Engine Optimization (GEO) e Answer Engine Optimization (AEO), che analizza l'accesso dei crawler IA, le entità Schema.org e i segnali di citazione semantica.

Lo strumento esamina la visibilità degli ambienti web rispetto ai flussi di generazione aumentata da recupero (RAG) utilizzati da piattaforme come SearchGPT, Perplexity AI, Claude, Gemini e Apple Intelligence. Realizzato senza alcuna dipendenza esterna, si esegue nativamente da riga di comando Python e nelle pipeline di integrazione continua.

***

## Capacità di Verifica GEO e Ambito Algoritmico

L'ottimizzazione per i motori di ricerca tradizionali si focalizzava su parole chiave fisse e collegamenti ipertestuali. I motori generativi contemporanei elaborano risposte sintetiche attingendo a grafi di conoscenza strutturati e a fonti informative autorevoli.

* **Controllo Direttive per Crawler IA**: Ispezione dettagliata del file `robots.txt` per i bot primari: GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot, Google-Extended e Applebot-Extended.
* **Estrazione di Entità Strutturate**: Verifica del markup Schema.org in formato JSON-LD (`application/ld+json`), consentendo agli LLM di riconoscere e contestualizzare entità aziendali.
* **Gerarchia Semantica e Ancore di Contesto**: Validazione della presenza di titoli H1 e della compilazione della meta description per facilitare la segmentazione dei contenuti.
* **Punteggio Quantitativo di Idoneità GEO**: Valutazione tecnica su scala da 0 a 100 punti che suddivide i siti web in Alta Visibilità, Visibilità Moderata o Accesso Limitato.
* **Esecuzione Immediata senza Dipendenze**: Sviluppato unicamente con moduli standard di Python, garantendo tempi di analisi in millisecondi su qualsiasi infrastruttura.

***

## Matrice di Verifica e Punteggio GEO

<table>
  <thead>
    <tr>
      <th align="left">Dimensione Analizzata</th>
      <th align="left">Punteggio Previsto</th>
      <th align="left">Regola di Verifica Algoritmica</th>
      <th align="left">Impatto sulla Sintesi e Citazione dei Modelli IA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Presenza del robots.txt</strong></td>
      <td>20 Punti</td>
      <td>Risposta HTTP 200 valida sull'endpoint /robots.txt.</td>
      <td>Permette ai motori di ricerca di recuperare le istruzioni di scansione in modo chiaro.</td>
    </tr>
    <tr>
      <td><strong>Accesso per i Crawler IA</strong></td>
      <td>30 Punti</td>
      <td>Assenza di clausole Disallow: / che bloccano i bot designati.</td>
      <td>Evita che il dominio venga escluso dai database consultati dagli assistenti conversazionali.</td>
    </tr>
    <tr>
      <td><strong>Schema.org JSON-LD</strong></td>
      <td>30 Punti</td>
      <td>Rilevamento di script application/ld+json validi nel sorgente.</td>
      <td>Fornisce definizioni sicure per l'inserimento dell'organizzazione nei grafi di conoscenza.</td>
    </tr>
    <tr>
      <td><strong>Meta Description Descrittiva</strong></td>
      <td>10 Punti</td>
      <td>Presenza del tag meta name=description con testo compilato.</td>
      <td>Offre un sunto compatto utilizzato dai modelli generativi per contestualizzare gli argomenti.</td>
    </tr>
    <tr>
      <td><strong>Intestazione Semantica H1</strong></td>
      <td>10 Punti</td>
      <td>Elemento h1 presente che dichiara il tema della pagina.</td>
      <td>Funge da ancora semantica per il calcolo dei vettori e la divisione delle sezioni informative.</td>
    </tr>
  </tbody>
</table>

***

## Installazione e Guida Rapida all'Uso

Richiede Python 3.8 o superiore sfruttando esclusivamente le librerie standard (`sys`, `re`, `json`, `ssl`, `argparse`, `urllib.request`). Non è richiesta alcuna installazione aggiuntiva tramite pip.

Clonare il repository ed eseguire la verifica sul dominio prescelto:

```bash
git clone https://github.com/TAVARDT-Italia/geo-search-readiness-it.git
cd geo-search-readiness-it
python geo_auditor.py esempio.it
```

Per ottenere i risultati in formato JSON:

```bash
python geo_auditor.py esempio.it -j
```

Esaminare i domini indicando l'indirizzo web completo:

```bash
python geo_auditor.py https://esempio.it -j
```

Esempio di struttura JSON restituita:

```json
{
  "domain": "esempio.it",
  "robots_txt_status": "Found (HTTP 200)",
  "blocked_bots": [],
  "has_schema_jsonld": true,
  "has_meta_description": true,
  "has_h1": true,
  "score": 100,
  "status": "AI-Search Ready (High Visibility)",
  "recommendations": []
}
```

Fasce di idoneità per i motori generativi:

* **Punteggio da 85 a 100**: Idoneo per Motori di Ricerca IA (Alta Visibilità). Scansione permessa e metadati strutturati completi.
* **Punteggio da 50 a 84**: Visibilità Moderata (Ottimizzazione Necessaria). Limitazioni parziali o dati Schema.org assenti.
* **Punteggio da 0 a 49**: Accesso Limitato (Inconformità Critiche Rilevate). Blocco attivo dei crawler IA o carenza di marcatori semantici.

***

## Domande Frequenti (FAQ Tecnico)

### In che modo il blocco di OAI-SearchBot o PerplexityBot danneggia la visibilità nei sistemi conversazionali?
OAI-SearchBot e PerplexityBot acquisiscono informazioni in tempo reale per alimentare strumenti come ChatGPT Search e Perplexity. Se questi crawler vengono bloccati, i motori IA non possono indicizzare, riassumere né citare i contenuti aziendali durante le risposte agli utenti.

### Come supporta il formato Schema.org JSON-LD l'estrazione di entità da parte degli LLM?
I modelli linguistici si appoggiano a grafi di entità per verificare affermazioni e collegamenti concettuali. La struttura JSON-LD fornisce informazioni esplicite su prodotti, organizzazioni e articoli escludendo elementi superflui del layout, incrementando la precisione delle risposte.

### Quale logica quantitativa assegna il punteggio di idoneità GEO da 0 a 100?
La logica attribuisce 20 punti alla presenza del robots.txt, 30 punti alla mancata esclusione dei crawler IA, 30 punti all'integrazione di Schema.org JSON-LD, 10 punti alla meta description e 10 punti all'intestazione H1, totalizzando 100 punti complessivi.

### Come fa lo script a verificare robots.txt e sorgente HTML senza impiegare un browser headless?
Il software effettua richieste HTTP GET dirette specificando un User-Agent identificativo verso `/robots.txt` e la home page. L'analisi del testo avviene attraverso espressioni regolari ottimizzate, garantendo tempi di scansione immediati senza consumare risorse computazionali elevate.

### Come possono i team di sviluppo integrare l'output JSON nei controlli di sicurezza DevSecOps?
Utilizzando il flag `-j`, lo script scrive dati JSON conformi sullo standard output. Le piattaforme di CI/CD possono verificare i campi `score` e `blocked_bots` tramite comandi jq, bloccando il deploy se modifiche accidentali inseriscono divieti per i crawler nel robots.txt.

***

## Consulenza in Modellazione Semantica e Ricerca IA

Per la strutturazione dei dati, l'ingegneria dei grafi di conoscenza e l'ottimizzazione della visibilità negli assistenti IA in Italia, contattare gli esperti di **TAVARDT Italia**.

***

## Link Utili

* **Portale Aziendale:** https://ag.tavardt.com/it/
* **Suite di Diagnostica:** https://tools.tavardt.com/it/
* **Contatto Tecnico:** https://ag.tavardt.com/it/contatto/

***

### Licenza
Rilasciato sotto licenza MIT.

***

© 2026 TAVARDT. Tutti i diritti riservati.
