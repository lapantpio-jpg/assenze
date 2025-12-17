# 🌐 Come Pubblicare il Registro Assenze Online

## 🎯 Obiettivo
Rendere il sito accessibile a tutti tramite un link pubblico (es: `https://tuo-registro-assenze.netlify.app`)

---

## ⚡ METODO 1: Netlify Drop (CONSIGLIATO - 2 MINUTI)

### ✅ Più veloce e semplice, NESSUNA registrazione richiesta!

### **Passaggi:**

1. **Vai su:** https://app.netlify.com/drop

2. **Prepara i file:**
   - Crea una **cartella** sul desktop chiamata "registro-assenze"
   - Metti dentro questi file:
     - `index.html`
     - `style.css` (se ce l'hai)
     - `ODQ3NjU5MTA4ODA4.png` (se ce l'hai)
   - **IMPORTANTE**: Prima di pubblicare, **configura le credenziali JSONBin** nel file index.html!

3. **Pubblica:**
   - Trascina la **cartella intera** nella pagina di Netlify Drop
   - Aspetta qualche secondo
   - 🎉 **FATTO!** Ti darà subito un link tipo:
     ```
     https://random-name-123456.netlify.app
     ```

4. **Personalizza il link (OPZIONALE):**
   - Clicca su **"Site settings"**
   - Vai su **"Change site name"**
   - Scegli un nome (es: `registro-assenze-scout`)
   - Il tuo link diventa: `https://registro-assenze-scout.netlify.app`

### 🔄 **Aggiornare il sito:**
- Modifica i file sul tuo computer
- Vai sul sito Netlify (nella sezione "Deploys")
- Trascina di nuovo la cartella aggiornata
- Il sito si aggiorna automaticamente!

---

## 🐙 METODO 2: GitHub Pages (GRATIS E PROFESSIONALE)

### ✅ Migliore per progetti a lungo termine

### **Requisiti:**
- Account GitHub (gratuito)
- Git installato (opzionale ma consigliato)

### **Passaggi:**

#### **A) Crea Repository GitHub:**

1. Vai su https://github.com e fai login (o registrati)
2. Clicca sul **"+"** in alto a destra → **"New repository"**
3. Nome repository: `registro-assenze`
4. Seleziona **"Public"**
5. Spunta **"Add a README file"**
6. Clicca **"Create repository"**

#### **B) Carica i file:**

**Metodo semplice (senza Git):**
1. Nel repository, clicca **"Add file"** → **"Upload files"**
2. Trascina tutti i tuoi file:
   - `index.html`
   - `style.css`
   - `ODQ3NjU5MTA4ODA4.png`
3. Scrivi un messaggio (es: "Primo upload")
4. Clicca **"Commit changes"**

**Metodo con Git (se lo hai installato):**
```powershell
# Apri PowerShell nella cartella del progetto
cd C:\Users\Anton\OneDrive\Desktop\Assenze_

# Inizializza Git
git init
git add .
git commit -m "Primo commit"

# Collega al repository (sostituisci TUO_USERNAME)
git remote add origin https://github.com/TUO_USERNAME/registro-assenze.git
git branch -M main
git push -u origin main
```

#### **C) Attiva GitHub Pages:**

1. Nel repository, vai su **"Settings"**
2. Clicca su **"Pages"** nel menu laterale
3. Sotto "Source", seleziona **"main"** branch
4. Clicca **"Save"**
5. Aspetta 1-2 minuti
6. 🎉 Il tuo sito sarà disponibile su:
   ```
   https://TUO_USERNAME.github.io/registro-assenze/
   ```

---

## 🚀 METODO 3: Vercel (VELOCE E POTENTE)

### **Passaggi:**

1. Vai su https://vercel.com
2. Clicca **"Sign Up"** (puoi usare GitHub)
3. Clicca **"Add New"** → **"Project"**
4. Trascina la cartella del progetto
5. Clicca **"Deploy"**
6. 🎉 Link pronto in 30 secondi!
   ```
   https://registro-assenze.vercel.app
   ```

---

## 🎨 METODO 4: Neocities (STILE RETRO)

### **Passaggi:**

1. Vai su https://neocities.org
2. Clicca **"Sign Up"** (è gratis)
3. Scegli un nome per il sito (es: `registro-assenze`)
4. Vai su **"Edit Site"**
5. Carica i file (drag & drop)
6. 🎉 Sito online su:
   ```
   https://registro-assenze.neocities.org
   ```

---

## ⚠️ IMPORTANTE: Configurazione Pre-Pubblicazione

### **PRIMA di pubblicare, assicurati di:**

1. ✅ **Configurare JSONBin.io** nel file index.html
   - Sostituisci `TUO_BIN_ID_QUI` con il tuo BIN ID
   - Sostituisci `$2a$10$TUA_API_KEY_QUI` con la tua API KEY

2. ✅ **Testare in locale** che tutto funzioni
   - Apri index.html nel browser
   - Aggiungi un'assenza di prova
   - Verifica che salvi online

3. ⚠️ **Attenzione alla sicurezza:**
   - La tua API_KEY sarà visibile nel codice
   - Chiunque può vedere e modificare i dati
   - Per maggiore sicurezza, considera:
     - Usare Firebase (con autenticazione)
     - Creare un backend con password

---

## 🔐 Opzione SICURA: Protezione con Password

Se vuoi che solo alcune persone possano accedere, aggiungi questa protezione semplice:

```html
<!-- Aggiungi questo all'inizio del <body> nel file index.html -->
<script>
  const PASSWORD = "tuapassword123"; // Cambia questa password
  const userPassword = prompt("Inserisci la password per accedere:");
  if (userPassword !== PASSWORD) {
    document.body.innerHTML = "<h1>Accesso Negato</h1>";
  }
</script>
```

⚠️ **Nota:** Questa è una protezione base, NON è sicura al 100%!

---

## 📊 Confronto Metodi

| Metodo | Velocità | Difficoltà | Personalizzazione | Dominio |
|--------|----------|------------|-------------------|---------|
| **Netlify Drop** | ⚡⚡⚡ | 🟢 Facile | 🟡 Media | .netlify.app |
| **GitHub Pages** | ⚡⚡ | 🟡 Media | 🟢 Alta | .github.io |
| **Vercel** | ⚡⚡⚡ | 🟢 Facile | 🟢 Alta | .vercel.app |
| **Neocities** | ⚡⚡ | 🟢 Facile | 🔴 Bassa | .neocities.org |

---

## 🎯 Consiglio Personale

### **Per iniziare subito:** Usa **Netlify Drop**
- Non serve registrazione
- 2 minuti per pubblicare
- Link immediato

### **Per progetto professionale:** Usa **GitHub Pages**
- Gratuito per sempre
- Versioning del codice
- Più controllo

### **Per massima velocità:** Usa **Vercel**
- Deploy automatico
- Performance ottimizzate
- Dashboard professionale

---

## 📱 Condividere il Link

Una volta pubblicato:

1. **Copia il link** (es: `https://tuo-sito.netlify.app`)
2. **Condividilo** con:
   - WhatsApp
   - Email
   - Telegram
   - Social media
3. Tutti potranno accedere da qualsiasi dispositivo!

---

## 🔄 Aggiornamenti Futuri

Quando modifichi il sito:

- **Netlify/Vercel:** Ricarica i file aggiornati
- **GitHub Pages:** Fai push delle modifiche
- Le modifiche saranno online in 1-2 minuti!

---

## 💡 Suggerimenti Extra

### **Domini personalizzati (es: www.registro-assenze.it):**
- Acquista dominio su Namecheap, GoDaddy (€10-15/anno)
- Collega a Netlify/Vercel/GitHub Pages (nelle impostazioni)

### **HTTPS automatico:**
- Tutti i servizi sopra offrono HTTPS gratuito
- I tuoi dati sono crittografati

### **Analytics:**
- Aggiungi Google Analytics per vedere quante persone visitano
- Completamente gratuito

---

## 🆘 Problemi Comuni

### ❌ "Il sito non si carica"
- Aspetta 2-3 minuti dopo la pubblicazione
- Svuota cache del browser (Ctrl+Shift+R)
- Controlla che tutti i file siano stati caricati

### ❌ "I dati non si salvano"
- Verifica configurazione JSONBin nel file index.html
- Controlla la console del browser (F12)

### ❌ "Il CSS non viene applicato"
- Controlla che il file style.css sia nella stessa cartella
- Verifica il nome del file nel tag `<link>`

---

## 🎓 Tutorial Video Consigliati

Cerca su YouTube:
- "Come pubblicare sito HTML su Netlify"
- "GitHub Pages tutorial italiano"
- "Deploy sito web gratis"

---

**Scegli il metodo che preferisci e in pochi minuti il tuo registro sarà online! 🚀**

*Domande? Dubbi? Chiedi pure!*
