# Auditor di Ricerca IA e GEO

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Ricerca%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/it/audit-motori-ricerca-ia/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Auditor CLI di Generative Engine Optimization (GEO) per la verifica delle autorizzazioni dei crawler IA, dati strutturati Schema.org e chiarezza semantica.

Sviluppato e gestito dalla divisione di ingegneria semantica e visibilita digitale di **TAVARDT Italia**.

***

## Funzionalita di Audit GEO

* **Accessibilita per Crawler IA**: Ispezione delle direttive in `robots.txt` per bot quali GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot e Google-Extended.
* **Estrazione di Entita Semantiche**: Rilevamento della presenza di marcatura strutturata Schema.org in formato JSON-LD.
* **Segnali Semantici Chiave**: Verifica della gerarchia dei tag H1 e completezza delle meta description per l indicizzazione da parte degli LLM.
* **Punteggio di Prontezza**: Diagnosi tecnica da 0 a 100 punti con raccomandazioni pratiche.

***

## Installazione e Utilizzo

Richiede esclusivamente Python 3.8 o superiore senza dipendenze terze.

```bash
git clone https://github.com/TAVARDT-Italia/geo-search-readiness-it.git
cd geo-search-readiness-it
python geo_auditor.py azienda.it
```

Per ottenere l output in formato JSON:

```bash
python geo_auditor.py azienda.it -json
```

***

## Diagnosi Online su Web

Per analisi continue e verifiche di conformita su interfaccia grafica, consultare lo strumento ufficiale:

* **Auditor di Ricerca IA e GEO**
* **[Portale Aziendale TAVARDT Italia](https://ag.tavardt.com/it/)**

***

## Consulenza in Semantica e Motori IA

Per l ottimizzazione della visibilita semantica nei modelli generativi in Italia, contattare gli specialisti di **TAVARDT Italia**.

***

© 2026 TAVARDT. Tutti i diritti riservati.
