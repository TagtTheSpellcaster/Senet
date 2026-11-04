# Senet

[![Versione](https://img.shields.io/badge/versione-1.1-blue)](#versioni)
[![Licenza: AGPL v3](https://img.shields.io/badge/licenza-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-222?logo=github)](#pubblicazione-su-github-pages)
[![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2020-F7DF1E?logo=javascript&logoColor=black)](index.html)
[![Three.js](https://img.shields.io/badge/Three.js-r128-000?logo=threedotjs&logoColor=white)](https://threejs.org/)
[![Lingua](https://img.shields.io/badge/lingua-italiano%20%7C%20inglese-green)](#)

Versione per browser del Senet, il gioco da tavolo dell'Antico Egitto. È una singola pagina HTML, senza build e senza installazione. Condivide l'architettura del [Gioco Reale di Ur](https://github.com/): motore di gioco separato dall'interfaccia, dadi in 3D, animazioni, audio sintetizzato, storia e regole illustrate.

## Caratteristiche

- **Due set di regole**, tenuti distinti perché le fonti non coincidono:
  - *CEMEA*: quattro legnetti, sette pedine a testa;
  - *Kendall e Bell*: dado a sei facce con la X, cinque pedine a testa, uscita dalla casella 30 a inizio turno.
- **Pedine a testa**: 5 o 7, indipendentemente dal set di regole.
- **Avversario**: computer o due giocatori sullo stesso schermo.
- **Tavoliere** a faience azzurra con i glifi delle case speciali (ankh, acqua, III, occhio di Horus, disco solare) e un vassoio dell'aldilà per ciascun giocatore.
- **Legnetti e dado in 3D** (Three.js). Senza WebGL o Three.js si usa una versione 2D.
- **Animazioni** passo per passo, con scambio di posto negli attacchi e ritorno in casa 15 dalla malasorte. Con «riduci movimento» attivo nel sistema operativo le animazioni sono disattivate.
- **Audio** sintetizzato con Web Audio: effetti sonori (attivi di default) e colonna sonora di ispirazione egizia (disattivata di default), con scala doppia armonica, arpa, flauto, darbuka e sistro. La scelta è salvata nel browser.
- **Regole illustrate**: un tutorial animato per ciascun set di regole (19 e 20 passi).
- **Storia**: sequenza a titoli cinematografici tratta dalla voce «Senet» di Wikipedia.
- **Italiano e inglese**: selettore IT/EN nell'intestazione; la scelta è salvata nel browser e, in mancanza, si usa la lingua del browser. Cambia anche a partita in corso, nelle regole illustrate e nella storia (le voci già scritte nella cronaca restano nella lingua originale).
- Tema chiaro e scuro automatico, layout adattabile a schermi piccoli.

## Regole in breve

Il percorso ha 30 caselle in tre file da 10, lette a serpentina. Si avanza esattamente del punteggio ottenuto; con 1, 4 e 6 (legnetti) o 1, 4 e 5 (dado) si rilancia, con 2 e 3 si passa la mano. Chi termina su una pedina avversaria scambia di posto con essa. Due pedine contigue formano un muro che non si attacca ma si supera; tre formano un muro invalicabile. Le case 15, 26, 28, 29 e 30 proteggono le pedine; la 27 riporta in 15. Si esce dalla 28 con 3, dalla 29 con 2, dalla 30 con 1. Vince chi porta fuori per primo tutte le pedine.

Il dettaglio è nel pannello «Regole, interpretazioni e fonti» della pagina.

## Interpretazioni e limiti

Le regole originali sono sconosciute e le fonti lasciano alcuni punti aperti. Scelte adottate:

- **Salto della malasorte**: «con un 1 si può saltare la casa della malasorte» è interpretato come passaggio diretto dalla 26 alla 28.
- **Malasorte con la 15 occupata**: da una pedina propria, la pedina riparte dalla prima casella libera; dall'avversario, resta in 27 e il giocatore è bloccato finché non ottiene 4.
- **Uscita con il 4**: la pedina bloccata esce dal tavoliere e conta come pedina in salvo, come previsto dalla regola CEMEA.
- **Retrocessione** (tiro nullo): solo su caselle libere. Le pedine in 28-30 lasciano la casella solo con il punteggio esatto.
- **Non implementato**: la regola antica per cui entrambi i giocatori concludevano la partita.
- La datazione «V–IV millennio a.C.» riportata dal testo di partenza per l'uso del gioco da parte dei faraoni non è ripresa nella storia, perché non verificata.

Il motore è stato verificato con simulazioni di partite complete (8 combinazioni di regole, pedine e giocatori) e con 33 scenari su attacchi, muri, case speciali e uscite.

## Avvio

Apri `index.html` in un browser moderno. La pagina carica da CDN, se raggiungibili, Three.js r128 (`cdnjs.cloudflare.com`) e i caratteri Google Fonts; senza, usa dadi 2D e caratteri di sistema.

## Pubblicazione su GitHub Pages

1. Copia `index.html` nella radice del repository.
2. In *Settings → Pages* scegli il branch (ad esempio `main`) e la cartella `/ (root)`.
3. La pagina sarà all'indirizzo `https://<utente>.github.io/<repository>/`.

## Versioni

| Versione | Contenuto |
|---|---|
| 1.1 | Interfaccia in italiano e inglese con selettore della lingua. |
| 1.0 | Gioco completo con regole CEMEA e Kendall e Bell, animazioni, audio, storia e regole illustrate. |

## Fonti

- Voce «Senet», Wikipedia, che riporta le regole del gruppo di ricerca sul gioco dei CEMEA (set *CEMEA*).
- Regole di Timothy Kendall e R.C. Bell, nell'adattamento UniNerd (PDF) (set *Kendall e Bell*).

## Licenza

Copyright © 2026 Alessandro Valli.

Questo programma è software libero: puoi ridistribuirlo e modificarlo secondo i termini della GNU Affero General Public License, versione 3 o successiva. Se fornisci una versione modificata come servizio in rete, devi renderne disponibile il codice sorgente agli utenti. Il programma è distribuito senza alcuna garanzia. Testo completo: [LICENSE](LICENSE) e <https://www.gnu.org/licenses/agpl-3.0.html>.

Three.js è distribuito con licenza MIT.
