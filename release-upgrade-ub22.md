# 🔄 Upgrade da Ubuntu 22.04 LTS a 24.04 LTS

Questa guida spiega come eseguire l'aggiornamento da **Ubuntu 22.04 LTS (Jammy Jellyfish)** a **Ubuntu 24.04 LTS (Noble Numbat)** in modo sicuro, seguendo i passaggi ufficiali consigliati da Canonical.

## 📋 Requisiti

- Sistema attuale: Ubuntu 22.04 LTS
- Accesso come utente con privilegi sudo
- Backup completo del sistema
- Connessione Internet stabile

---

## 🛠️ Step 1 - Aggiornamento del sistema

```bash
sudo apt update && sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt autoremove --purge -y
```

> Assicurati che il sistema sia completamente aggiornato prima di procedere con l’upgrade.

---

## 🧪 Step 2 - Abilitare aggiornamenti LTS

Modifica il file `/etc/update-manager/release-upgrades`:

```ini
Prompt=lts
```

---

## 🚀 Step 3 - Avviare l'upgrade

Quando Ubuntu 24.04 sarà ufficialmente disponibile come LTS, potrai eseguire:

```bash
sudo do-release-upgrade
```

Se il comando non trova aggiornamenti disponibili, usa:

```bash
sudo do-release-upgrade -d
```

> ⚠️ L'opzione `-d` forza l'aggiornamento a una versione ancora in fase di sviluppo/staging. Usare solo se consapevoli dei rischi.

---

## 💡 Suggerimenti post-upgrade

- Riavviare il sistema:
  ```bash
  sudo reboot
  ```
- Verificare la versione:
  ```bash
  lsb_release -a
  ```
- Controllare i servizi attivi e la configurazione di rete
- Analizzare eventuali pacchetti rimossi o non più supportati

---

## 🧯 Ritorno indietro?

Ubuntu **non supporta il downgrade**. Se l’upgrade causa problemi critici, l’unica soluzione è ripristinare da backup.

---

## 📌 Note importanti

- Effettuare sempre l'upgrade in ambienti di test prima di passare alla produzione
- Alcuni PPA o driver personalizzati potrebbero non essere compatibili con la nuova release
- Verifica la compatibilità del kernel, applicazioni e librerie

---

## 📚 Riferimenti

- [Guida ufficiale Ubuntu](https://help.ubuntu.com/community/UpgradeNotes)
- `man do-release-upgrade`

---

Se vuoi, posso anche esportare questa pagina in formato `.md` o `.pdf`. Fammi sapere!
