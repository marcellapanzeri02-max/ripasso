# Ripasso: app installabile (PWA)

Ripasso raccoglie i panieri delle tue materie e ti fa le domande finché non le sai. Funziona come un'app sul telefono e anche offline.

## Cosa puoi fare

- **Materie**: ogni materia può contenere più panieri e lezioni. Quando apri una materia, «Aggiungi materiale» aggiunge altri file a quella materia.
- **Panieri**: carica un PDF o un file di testo, oppure incolla le domande.
  - *Senza IA* (gratis, senza chiave): riconosce domande numerate con opzioni A), B), C)… La risposta giusta può essere indicata con «Risposta: B», con un asterisco, con «(corretta)» o in grassetto nel PDF.
  - *Con l'IA* (serve la chiave API): legge anche i PDF disordinati.
- **Risposte**: se le risposte giuste sono in un file a parte, caricalo insieme al paniere oppure dopo, con «Carica le risposte». Funziona con le griglie («1-B, 2-C…») e con i file che riportano le domande con la soluzione. Ogni risposta viene abbinata alla sua domanda per testo o per numero.
- **Domande scritte a mano**: dalla pagina della materia puoi scrivere domande nuove e modificare o eliminare quelle esistenti.
- **Quiz**: ripasso intelligente, simulazione d'esame, solo errori, tutte in ordine, oppure «Quiz su misura» (scegli fonte, numero e tipo di domande, e se correggere subito o alla fine).
- **Lezioni** (serve la chiave API): l'IA crea domande a partire dal testo della lezione.

## 1. Mettila online

Una PWA deve stare su un sito HTTPS: aprire `index.html` dal computer con un doppio clic non basta per installarla.

**Il modo più rapido (Netlify Drop, gratis)**
1. Vai su https://app.netlify.com/drop
2. Trascina dentro la cartella `ripasso-pwa` intera (non lo zip).
3. Ti dà un indirizzo tipo `https://nome-a-caso.netlify.app`. Puoi crearti un account gratuito per tenerlo e rinominarlo.

**In alternativa: GitHub Pages**
1. Crea un repository e carica i file della cartella.
2. Settings → Pages → scegli il branch `main` e salva.

## 2. Installala sul telefono

- **Android (Chrome)**: apri l'indirizzo, poi menu ⋮ → «Installa app». Oppure dalle Impostazioni dell'app.
- **iPhone (Safari)**: apri l'indirizzo, tocca Condividi → «Aggiungi alla schermata Home».

## 3. Chiave API (facoltativa)

Senza chiave puoi usare i panieri ordinati, caricare le risposte e fare tutti i quiz. La chiave serve per leggere i PDF disordinati, creare domande dalle lezioni, correggere le risposte aperte e spiegare le risposte («Perché?»).
1. Crea una chiave su https://console.anthropic.com (sezione API Keys) e aggiungi del credito.
2. Nell'app: Impostazioni → incolla la chiave → «Salva e prova».

La chiave resta salvata solo sul tuo dispositivo e viene inviata solo ad Anthropic. L'API si paga a consumo, separatamente dall'abbonamento a Claude.

Attenzione: non pubblicare la chiave dentro i file e non condividere l'indirizzo con la tua chiave già inserita su un dispositivo altrui.

## Dati e backup

Materie e progressi sono salvati nel browser del dispositivo. Se cancelli i dati del browser o disinstalli l'app, si perdono: usa Impostazioni → «Esporta backup» ogni tanto. Con «Importa backup» li sposti su un altro dispositivo.

## Se modifichi l'app

Dopo aver cambiato `index.html`, apri `sw.js` e aumenta la versione (es. `ripasso-v7` → `ripasso-v8`), altrimenti i telefoni continuano a mostrare la versione vecchia salvata.

I modelli usati sono indicati in cima allo script in `index.html` (costante `MODELS`): se Anthropic li ritira, sostituisci i nomi con quelli attuali indicati su https://docs.claude.com.
