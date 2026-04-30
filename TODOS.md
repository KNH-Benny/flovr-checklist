# Flovr — Setup TODOs

Alle offenen Punkte aus dem Flovr Master Guide.
Interaktive Version: **https://knh-benny.github.io/flovr-checklist/**

---

## A · Infrastruktur — VPS & Server-Setup

- [ ] **A-01** — VPS bestellen (netcup VPS 500 G12)
- [ ] **A-02** — Erster SSH-Login, Key-Auth, Root-Login deaktivieren, UFW einrichten
- [ ] **A-03** — fail2ban installieren + konfigurieren
- [ ] **A-04** — nginx + PHP 8.3 + MariaDB installieren (`server_install.sh`)
- [ ] **A-05** — nginx vHost-Configs aktivieren (api.flovr.de, app.flovr.de, flovr.de)
- [ ] **A-06** — SSL-Zertifikate: `certbot --nginx -d api.flovr.de -d app.flovr.de -d flovr.de`
- [ ] **A-07** — `/etc/flovr/.env` anlegen + befüllen (DB_PASS, JWT_SECRET, alle CHANGE_ME ersetzen)
- [ ] **A-08** — MariaDB einrichten: flovr_db anlegen, flovr_user erstellen, Rechte vergeben
- [ ] **A-09** — GitHub Actions CI/CD Pipeline testen: Push auf `main` → Deploy-Job prüfen
- [ ] **A-09** — `TODO C-01` in deploy.yml: Health-Check einkommentieren nach Backend-Setup
- [ ] **A-10** — Staging: `sudo bash backend/setup/staging_setup.sh` auf VPS ausführen
- [ ] **A-10** — Staging SSL: `certbot --nginx -d api-staging.flovr.de -d app-staging.flovr.de`
- [ ] **A-10** — GitHub Environment `production` mit Required Reviewer einrichten — erst relevant wenn zweiter Deployer/Entwickler dazu kommt (GitHub → Settings → Environments → production → Required reviewers)
- [ ] **A-11** — Block Storage: `/dev/vdb` formatieren, als `/mnt/backup` mounten, `/etc/fstab` eintragen
- [ ] **A-11** — Backup installieren: `git pull && bash backend/setup/backup/backup_install.sh`
- [ ] **A-11** — Backup testen: `bash /usr/local/bin/flovr-backup.sh` + `df -h /mnt/backup` prüfen

---

## B · Datenbank — Schema & Migration

- [ ] **B-01** — Vollständiges MariaDB-Schema ausführen (28 Tabellen, Multi-Tenant, utf8mb4)
- [ ] **B-02** — Seed-Daten einspielen: Rollen + Presets
- [ ] **B-03** — Migrations-System einrichten (inkrementelle SQL-Migrations)

---

## C · Backend — PHP Router & Auth

- [ ] **C-01** — Verzeichnis-Struktur + Router (`backend/public/index.php`, Middleware-Chain)
- [ ] **C-02** — Auth-System: Login, JWT, Refresh-Token, Logout, /me

---

## D · Security — Demo-User & Secrets bereinigen

- [ ] **D-01** — Demo-Users entfernen, Apps Script URL aus Code raus, Google Fonts lokal
- [ ] **D-02** — Git History bereinigen (falls Secrets committed wurden)

---

## E · Storage — Uploads

- [ ] **E-01** — StorageInterface + Local Provider implementieren
- [ ] **E-02** — Upload-Endpunkte (Avatar, Dokumente)
- [ ] **E-03** — Google Drive Setup einmalig (falls gdrive als Storage-Provider gewählt)

---

## F · API — REST-Endpunkte

- [ ] **F-01** — Organisation & Org-Config (GET/PUT /api/org)
- [ ] **F-02** — Mitglieder-Endpunkte (CRUD, Rollen, Status)
- [ ] **F-03** — Projekte-Endpunkte (CRUD, Typen, Mitglieder)
- [ ] **F-04** — Schichten-Endpunkte (Planung, Buchung, Bestätigung)
- [ ] **F-05** — Aufgaben, Ideen, Feed
- [ ] **F-06** — Protokolle
- [ ] **F-07** — Inventar & Archiv
- [ ] **F-08** — Admin-Endpunkte & Mitgliedsanträge
- [ ] **F-09** — Social Media Planer
- [ ] **F-10** — Team-Verwaltung

---

## G · Frontend — API-Anbindung

- [ ] **G-01** — API-Client + Org-Config laden (CFG-Platzhalter ersetzen)
- [ ] **G-02** — Auth-Anbindung (Login, Logout, Token-Refresh)
- [ ] **G-03** — Projekte, Schichten, Feed von API laden
- [ ] **G-04** — Mitglieder, Aufgaben, Protokolle, Inventar

---

## H · UI — Bug-Fixes & Design System

- [ ] **H-01** — 10 bekannte Bugs fixen
- [ ] **H-02** — Next-Level UI — Design System (Tokens, Komponenten)
- [ ] **H-03** — Owner-Panel vollständig
- [ ] **H-04** — Projekt-Typen dynamisch + UI-Polish
- [ ] **H-05** — Mobile-Optimierung & Performance
- [ ] **H-06** — Social Media Tab — Redaktionskalender & Kanban
- [ ] **H-07** — Team-Workspace — Eigenständiger Bereich pro Team

---

## I · KI — Claude API Integration

- [ ] **I-01** — Template-System Backend
- [ ] **I-02** — Template-Auswahl im Projekt-Wizard
- [ ] **I-03** — Automation-Trigger (Connected Actions)
- [ ] **I-04** — Smart Defaults & Progressive Disclosure

---

## J · DSGVO — Export & Löschung

- [ ] **J-01** — Export & Löschung Backend (Art. 17 + Art. 20 DSGVO)
- [ ] **J-02** — DSGVO-UI im Profil

---

## K · Betrieb — Monitoring & Crons

- [ ] **K-01** — Security Headers + Rate Limiting
- [ ] **K-02** — Monitoring & Health

---

## L · Launch — KNH-Setup & Checkliste

- [ ] **L-01** — EasyVerein-Import
- [ ] **L-02** — KNH Org-Config einrichten
- [ ] **L-03** — Ersten Owner-Account aktivieren
- [ ] **L-04** — `IS_LIVE=true` in `.env` setzen
- [ ] **L-05** — Launch-Checkliste vollständig abarbeiten

---

## M · Zukunft — Vision

- [ ] **M-01** — Chat-Funktion (WebSockets)
- [ ] **M-02** — Finanz-Tool-Koop
- [ ] **M-04** — Kalender-API-Anbindung
- [ ] **M-05** — Meetings & Audio-Transkription (Vision)

---

## N · Modul-Builder

- [ ] **N-01** — Modul-Builder Backend
- [ ] **N-02** — Modul-Builder Frontend (Owner-Panel)

---

## O · Template-System

- [ ] **O-01** — Template-System Backend
- [ ] **O-02** — KNH Kulturverein Template (aus KNH-App extrahieren)
- [ ] **O-03** — Onboarding-Flow mit Template-Auswahl

---

## P · Template-Marketplace

- [ ] **P-01** — Template-Registry Backend
- [ ] **P-02** — Clickbarer Preview — Live-Demo ohne Account
- [ ] **P-03** — Market-Frontend — Entdecken & Installieren
- [ ] **P-04** — Virale Loops — Wie KNH andere Vereine einlädt
