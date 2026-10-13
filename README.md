# Personal Assistant Dashboard

Una piccola dashboard assistente personale con design Apple-inspired (sfondo bianco/grigio chiaro, testo nero, pulsanti blu).

## Funzionalità

- **Dashboard** – riepilogo rapido: mail non lette, eventi del giorno, saldo
- **Mail** – inbox mock + possibilità di segnare come lette
- **Calendario** – lista eventi, aggiunta ed eliminazione
- **Finanze** – entrate/uscite, saldo, storico movimenti
- **Ricerche & Riassunti** – note tematiche con riassunto automatico locale
- **Invia messaggio** – form per Email e Telegram (modalità demo/simulata)

Tutti i dati sono salvati in **localStorage** del browser. Nessun account, nessuna API key richiesta per far funzionare la demo.

## Design

- Sfondo bianco / grigio Apple (`#F5F5F7`)
- Testo nero (`#1D1D1F`)
- Pulsanti blu Apple (`#007AFF`)
- Card arrotondate, ombre leggere, tipografia system
- Completamente responsive

## Come avviarlo

### Opzione 1 – File singolo (più semplice)

Apri semplicemente il file `index.html` nel browser (doppio click o trascina nella finestra del browser).

### Opzione 2 – Server locale

```bash
# Con Python
python -m http.server 8000

# Oppure con Node
npx serve .
```

Poi apri http://localhost:8000

## Estendere con integrazioni reali

Questa è una versione **demo/frontend-only**. Per rendere reali le funzioni di invio:

### Telegram
1. Crea un bot con [@BotFather](https://t.me/BotFather)
2. Ottieni il token
3. Usa l’API `https://api.telegram.org/bot<TOKEN>/sendMessage`
4. Aggiungi un piccolo backend (es. Vercel Serverless / Cloudflare Worker) che riceve la richiesta dal frontend e chiama Telegram (non esporre mai il token nel frontend)

### Email
- Usa un servizio come Resend, SendGrid, Mailgun o SMTP (Gmail App Password)
- Stesso pattern: backend che riceve il form e invia la mail

### Calendario reale
- Google Calendar API + OAuth
- Oppure CalDAV

### Finanze reali
- Import CSV da banca
- Open Banking (PSD2) dove disponibile
- Oppure sincronizzazione con Google Sheets / Notion

### Riassunti AI
- Integra l’API di Grok / OpenAI / Claude per generare riassunti veri dal testo delle note o delle mail

## Struttura

```
.
├── index.html          # Tutta l’app (HTML + CSS Tailwind + JS)
└── README.md
```

## Tecnologie

- HTML5 + Vanilla JavaScript
- Tailwind CSS (via CDN)
- localStorage per persistenza
- Nessuna dipendenza di build

## Licenza

MIT – fai quello che vuoi.

---

Creato come MVP dimostrativo di dashboard assistente personale.
Per domande o miglioramenti apri una issue!
