# 📋 Guida Configurazione Registro Assenze Online

## 🎯 Panoramica
Il registro assenze ora salva i dati online, permettendoti di accedervi da qualsiasi dispositivo. Questa guida ti aiuterà a configurare il salvataggio cloud in pochi minuti.

---

## 🚀 Configurazione Passo-Passo

### **PASSO 1: Registrazione su JSONBin.io**

1. Apri il browser e vai su: **https://jsonbin.io**
2. Clicca su **"Sign Up"** (Registrati) in alto a destra
3. Inserisci la tua email e crea una password
4. Oppure usa il login rapido con Google/GitHub
5. Conferma la registrazione via email se richiesto
6. Fai login al tuo account

---

### **PASSO 2: Creazione del Bin (Contenitore Dati)**

1. Dopo il login, clicca su **"Create Bin"** o **"New Bin"**
2. Nel campo di testo, inserisci questo contenuto iniziale:
   ```json
   {
     "assenze": [],
     "lastUpdate": ""
   }
   ```
3. Clicca su **"Create"** o **"Save"**
4. Il bin è stato creato!

---

### **PASSO 3: Recupera le Credenziali**

Ora devi copiare due informazioni importanti:

#### **A) BIN ID (ID del contenitore)**
- Dopo aver creato il bin, vedrai l'URL nella barra degli indirizzi tipo:
  ```
  https://jsonbin.io/app/bins/6583a1b2e41b4d34e4a12345
  ```
- Il **BIN_ID** è la parte finale dopo `/bins/`: `6583a1b2e41b4d34e4a12345`
- Oppure cerca "Bin ID" nella pagina, dovrebbe essere visibile
- **COPIA questo codice** (sarà simile a: `6583a1b2e41b4d34e4a12345`)

#### **B) API KEY (Chiave di accesso)**
1. Clicca sull'icona del tuo profilo in alto a destra
2. Seleziona **"API Keys"** o **"Access Keys"**
3. Se non hai una chiave, clicca **"Create Access Key"**
4. Dai un nome alla chiave (es: "Registro Assenze")
5. **COPIA la chiave** generata (inizia con `$2a$10$...`)
   - Esempio: `$2a$10$abcdefghijklmnopqrstuvwxyz1234567890`
   - ⚠️ **ATTENZIONE**: Questa chiave viene mostrata UNA SOLA VOLTA! Salvala!

---

### **PASSO 4: Configura il File HTML**

1. Apri il file **index.html** con un editor di testo (Visual Studio Code, Notepad++, ecc.)

2. Cerca queste righe (circa righe 35-37):
   ```javascript
   const CONFIG = {
     BIN_ID: 'TUO_BIN_ID_QUI', // Inserisci qui il tuo Bin ID
     API_KEY: '$2a$10$TUA_API_KEY_QUI', // Inserisci qui la tua API key
     API_URL: 'https://api.jsonbin.io/v3/b/'
   };
   ```

3. Sostituisci i valori:
   - Incolla il **BIN_ID** al posto di `TUO_BIN_ID_QUI`
   - Incolla la **API_KEY** al posto di `$2a$10$TUA_API_KEY_QUI`
   
   **Esempio finale:**
   ```javascript
   const CONFIG = {
     BIN_ID: '6583a1b2e41b4d34e4a12345',
     API_KEY: '$2a$10$abcdefghijklmnopqrstuvwxyz1234567890',
     API_URL: 'https://api.jsonbin.io/v3/b/'
   };
   ```

4. **Salva il file** (Ctrl+S)

---

### **PASSO 5: Testa il Funzionamento**

1. Apri il file **index.html** nel browser (doppio click o trascina nel browser)
2. Vedrai un messaggio di stato in alto:
   - ✅ **Verde**: "Dati caricati dal server" = Tutto OK!
   - ⚠️ **Rosso**: "Salvato solo localmente" = Controlla configurazione
3. Prova ad aggiungere un'assenza
4. Se vedi "✓ Dati salvati online con successo" = **PERFETTO!**

---

## ✅ Verifica Salvataggio

Per controllare se i dati sono davvero online:

1. Vai su https://jsonbin.io e fai login
2. Clicca sul tuo bin
3. Dovresti vedere i dati delle assenze salvate
4. Oppure apri il registro su un altro computer: i dati dovrebbero apparire!

---

## 🔧 Risoluzione Problemi

### ❌ "Salvato solo localmente"
**Cause possibili:**
- BIN_ID o API_KEY errati → Controlla di averli copiati correttamente
- Mancano gli apici `'` attorno ai valori → Devono essere tra apici singoli
- Connessione internet assente → Verifica la connessione

### ❌ "Errore nel caricamento"
- Il bin potrebbe essere stato eliminato
- La API_KEY potrebbe essere scaduta
- Crea un nuovo bin e aggiorna le credenziali

### ❌ I dati non si caricano
- Controlla che il bin contenga i dati nel formato corretto
- Prova a svuotare la cache del browser (Ctrl+F5)

---

## 🔒 Sicurezza e Privacy

- ✅ **API_KEY privata**: Non condividere la tua API key con nessuno
- ✅ **Backup locale**: I dati sono sempre salvati anche nel browser (localStorage)
- ✅ **Gratuito**: JSONBin.io offre piano gratuito fino a 10.000 richieste/mese
- ⚠️ **Dati pubblici**: Se usi il piano gratuito, chiunque con il BIN_ID può vedere i dati
  - Per dati privati, considera l'upgrade al piano a pagamento

---

## 📊 Alternative a JSONBin.io

Se preferisci altri servizi simili:

1. **Pastebin.com** - Più semplice ma meno sicuro
2. **Firebase Realtime Database** - Google, più complesso ma potente
3. **Supabase** - Database PostgreSQL gratuito
4. **MongoDB Atlas** - Database professionale con piano gratuito

---

## 💡 Funzionalità Extra

Il registro ora include:

- 📡 **Sincronizzazione automatica**: Salva ad ogni aggiunta
- 💾 **Backup locale**: Funziona anche offline
- 🔄 **Caricamento automatico**: Recupera dati all'apertura
- ✅ **Notifiche**: Messaggi di conferma visivi
- 🔍 **Ricerca migliorata**: Filtra per nome/cognome
- 📈 **Conteggi automatici**: Totali assenze sempre aggiornati

---

## 📞 Supporto

Se hai problemi:
1. Rileggi attentamente i passaggi
2. Controlla la console del browser (F12) per errori
3. Verifica che BIN_ID e API_KEY siano corretti
4. Assicurati di avere connessione internet

---

## 🎓 Esempio Completo

**Prima (non configurato):**
```javascript
const CONFIG = {
  BIN_ID: 'TUO_BIN_ID_QUI',
  API_KEY: '$2a$10$TUA_API_KEY_QUI',
  API_URL: 'https://api.jsonbin.io/v3/b/'
};
```

**Dopo (configurato):**
```javascript
const CONFIG = {
  BIN_ID: '6583a1b2e41b4d34e4a12345',
  API_KEY: '$2a$10$Xy9kL3mN2pQ5rS8tU1vW4xY6zA2bC4dE5fG7hI9jK0lM',
  API_URL: 'https://api.jsonbin.io/v3/b/'
};
```

---

**Buon lavoro! 🚀**
