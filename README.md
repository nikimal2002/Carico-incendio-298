# Carico Incendio Ed. 298

App web per smartphone per registrare le entrate e le uscite di materiale nei sei locali dell'Edificio 298 e controllare in tempo reale che il carico d'incendio resti entro il limite ammesso dalla relazione antincendio (q<sub>f,d</sub> ≤ 300 MJ/m², struttura in acciaio R15).

> **Versione dimostrativa.** Pubblicata su GitHub Pages, l'app salva i dati solo nel browser del telefono che la usa. Serve a far provare il funzionamento ai colleghi. Nella versione operativa il registro è condiviso tra tutti gli operatori.

## Cosa fa

1. L'operatore sceglie il **locale**, **Entrata** o **Uscita**, il **materiale** dal menu a tendina e la **quantità**.
2. Mentre inserisce i dati, l'app mostra subito l'esito:
   - **verde**: ingresso ammesso;
   - **giallo** (con vibrazione): oltre la soglia di attenzione, avvisare il coordinatore antincendio;
   - **rosso** (con vibrazione): limite superato. La registrazione viene bloccata e l'app indica quante unità possono ancora entrare.
3. **Locali** mostra la situazione dei sei locali; **Storico** gli ultimi movimenti con l'operatore; **Impostazioni** permette di cambiare limiti, carichi iniziali e catalogo materiali.
4. **Scarica registro Excel** produce un file con i fogli *Situazione*, *Movimenti* e *Materiali*, con la stessa struttura di `Registro_carico_Ed298_semplice.xlsx`.

## Contenuto della cartella

| File | Descrizione |
|---|---|
| `index.html` | L'app (un solo file, nessuna installazione) |
| `manifest.webmanifest`, `icon*.png`, `icon.svg` | Permettono di aggiungere l'app alla schermata Home del telefono |
| `Registro_carico_Ed298_semplice.xlsx` | Registro Excel con semaforo per locale |
| `.nojekyll` | Fa servire i file a GitHub Pages così come sono |

## Pubblicare su GitHub Pages

1. Su GitHub crea un nuovo repository (es. `ed298-carico-incendio`).
2. **Add file → Upload files**: trascina tutti i file di questa cartella (incluso `.nojekyll`) e conferma con **Commit changes**.
3. **Settings → Pages**: in *Source* scegli **Deploy from a branch**, branch `main`, cartella `/ (root)`, poi **Save**.
4. Dopo uno o due minuti l'app è online all'indirizzo `https://<tuo-utente>.github.io/ed298-carico-incendio/`.

Sul telefono: apri il link e scegli **Aggiungi a schermata Home** (Safari: tasto Condividi; Chrome: menu ⋮).

## Dati e ipotesi

- **Limiti per locale**: valore più restrittivo tra la tabella del §5.2 della relazione e il ricalcolo con q<sub>f,d</sub> ≤ 300 MJ/m². Da confermare con il progettista.
- **Carichi iniziali**: scenario del cap. 3 della relazione. Ex loc. tecnico 3-4 e Capannetta 4 partono da zero in attesa di inventario.
- **MJ per unità**: i materiali `P-SCAF`, `P-PES`, `TUBI` vengono dalla relazione; i materiali `ASC-…` sono stime da verificare con la ditta.

Riferimento: Relazione antincendio 1440-D-R-00.01-1, rev. 05/02/2025.
