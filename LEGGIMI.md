# Verifica moto uniforme — versione mobile (PWA)

App installabile su iPhone e Android come icona sulla home, a tutto schermo, funzionante offline. È una **Progressive Web App**: stessa tecnologia di Twitter, Spotify Lite, Starbucks, Pinterest mobile.

## File inclusi

| File | A cosa serve |
|------|--------------|
| `index.html` | l'app vera e propria |
| `manifest.webmanifest` | dice al telefono "io sono un'app installabile" |
| `sw.js` | service worker per il funzionamento offline |
| `icon-192.png` `icon-512.png` `icon-512-maskable.png` | icone per Android |
| `apple-touch-icon.png` | icona per iPhone |
| `favicon-32.png` | icona per la scheda del browser |

I file devono restare insieme nella stessa cartella per funzionare.

## Come pubblicarla (5 minuti, gratuito)

Per installarla sul telefono come app a tutti gli effetti serve un URL https. Tre opzioni semplici, dal più rapido:

### 1. Netlify Drop (raccomandato, senza account)

1. Vai su <https://app.netlify.com/drop>
2. Trascina la cartella con tutti i file dentro la finestra
3. Aspetta 20 secondi — ottieni un URL tipo `https://nome-casuale-123.netlify.app`

Quell'URL è la tua app online, accessibile da qualsiasi telefono.

### 2. Vercel Drop

Analogo a Netlify ma con `https://vercel.com/new`. Stesso risultato.

### 3. GitHub Pages (se hai un account GitHub)

1. Crea una repo pubblica nuova
2. Carica tutti i file in radice
3. Settings → Pages → Source: `main` → `/ (root)` → Save
4. URL disponibile a `https://utente.github.io/nome-repo/`

## Come installarla sul telefono

Aperto l'URL pubblico dal telefono:

### iPhone (Safari)
1. Tap sul pulsante **Condividi** (quadrato con freccia in alto, in fondo)
2. Scorri e tocca **"Aggiungi alla schermata Home"**
3. Conferma il nome → tocca **Aggiungi**

Ora hai l'icona sulla home. Aprendola si lancia a schermo intero, senza barra Safari, esattamente come un'app App Store.

### Android (Chrome)
1. Chrome dovrebbe mostrare una notifica **"Installa app"** in basso → tocca e conferma
2. In alternativa: menu (⋮) → **"Installa app"** o **"Aggiungi a schermata Home"**

L'icona compare nel drawer delle app, lanciandola si apre a schermo intero. Su Android la PWA installata è di fatto indistinguibile da un'app Play Store.

## Funzionamento offline

Al primo avvio il service worker scarica e mette in cache tutti i file. **Da quel momento l'app funziona anche senza connessione** — utile in cantiere, in galleria, dove la copertura cellulare è ballerina. Si aggiorna in automatico quando torni online.

## Se vuoi un APK firmato per il Play Store

Una volta pubblicata la PWA (passi sopra), Microsoft mette a disposizione un servizio gratuito che la incapsula in un APK Android pronto per Google Play:

1. Vai su <https://www.pwabuilder.com>
2. Incolla l'URL della tua PWA
3. Genera l'APK / AAB Android (e, con dei costi aggiuntivi, anche IPA iOS)

Tieni presente che per pubblicare su Play Store serve un account Google Play Developer (una tantum 25 €). Per uso interno aziendale puoi distribuire l'APK direttamente senza store.

## Per modificare l'app

Apri `index.html` con qualsiasi editor di testo (Notepad++, VS Code, Sublime). Tutto — HTML, CSS, JavaScript, materiali, diametri normati — è in quel singolo file. Dopo le modifiche ricarica la pagina sul telefono (tira giù per refreshare) per vedere i cambiamenti. Cambia anche il numero di versione in `sw.js` (`CACHE_NAME`) se vuoi forzare l'aggiornamento della cache.

---

*Versione 1.0 · Strumento di pre-dimensionamento idraulico, non sostituisce una verifica progettuale completa.*
