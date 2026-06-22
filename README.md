# Sito Eco Edil Progetti — versione indipendente da Mobirise

Questo sito era stato esportato da Mobirise. Sono state rimosse tutte le
dipendenze "vive" dai server di Mobirise, in modo che funzioni come sito
statico puro (es. su GitHub Pages), senza bisogno di licenze o servizi
esterni di Mobirise.

## Cosa è stato modificato

In tutte le 12 pagine HTML (`index.html`, `page1.html` ... `page12.html`):

1. Rimosso il commento e il meta tag `generator` che dichiaravano "Site made
   with Mobirise".
2. Rimossa la sezione "badge" a fondo pagina con i link a `mobiri.se` e
   `mobirise.com` (la pubblicità/credito del builder).
3. Rimosso lo script `assets/formoid/formoid.min.js`: invia sempre i dati a
   `formoid.net`, indipendentemente dall'azione del form, e funziona solo con
   un abbonamento Mobirise attivo. Senza questo intervento, il modulo di
   contatto non avrebbe mai funzionato fuori da Mobirise.
4. Il modulo di contatto (presente in `page1.html` e `page3.html`) ora invia
   le richieste a **FormSubmit** (https://formsubmit.co), un servizio
   gratuito di backend per form statici, configurato per inviare le email a
   `ecoedilprogettisrls@gmail.com` (indirizzo già presente nel sito).

Tutto il resto (Bootstrap, font icone, jarallax, embla, immagini, PDF, Google
Maps, Google Fonts) era già self-hosted o puntava a servizi di terze parti
indipendenti da Mobirise (Google), quindi non è stato toccato.

## Cosa devi fare tu, una sola volta

La prima volta che qualcuno invia il modulo di contatto, FormSubmit manderà
una mail di conferma a `ecoedilprogettisrls@gmail.com`: bisogna cliccare il
link di attivazione contenuto in quella mail, altrimenti i messaggi successivi
non verranno consegnati. Da quel momento il modulo funzionerà stabilmente.

Per evitare lo step "clicca per confermare l'invio" mostrato da FormSubmit a
ogni invio (protezione anti-spam), o per reindirizzare l'utente a una pagina
di ringraziamento personalizzata dopo l'invio, si può aggiungere dentro al
tag `<form>` un campo come:

```html
<input type="hidden" name="_next" value="https://TUO-DOMINIO/grazie.html">
```

(va inserito l'URL assoluto finale del sito, una volta pubblicato).

## Pubblicazione su GitHub Pages

1. Crea un repository su GitHub e carica il contenuto di questa cartella
   nella root (oppure in una cartella `docs/`, configurabile nelle
   impostazioni Pages).
2. Vai su *Settings → Pages*, seleziona il branch e la cartella, salva.
3. Il file `project.mobirise` è il progetto sorgente dell'editor desktop
   Mobirise: non serve al sito pubblicato (il browser non lo usa), puoi
   tenerlo come backup per modifiche future nell'editor oppure escluderlo dal
   repository.
