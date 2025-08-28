# Dokumentenmanagement-App – To-Do Liste (Strukturiert mit Kategorien)

## Phase 0 – Projekt-Setup & Basis
<details><summary>Details anzeigen</summary>

- [ ] Repo anlegen, SvelteKit v5 initialisieren
- [ ] Pakete installieren: tailwindcss, daisyui, @supabase/supabase-js, pdfjs-dist, idb, pdf-lib
- [ ] Tailwind/DaisyUI konfigurieren (Light/Dark Themes, Theme-Toggle)
- [ ] .env anlegen (Supabase URL/Anon Key)
- [ ] Grundstruktur der Routen inkl. (app)-Gruppe erstellen

</details>

## Phase 1 – Routing, Layouts, Auth
<details><summary>Details anzeigen</summary>

- [ ] Public-Routen: /, /login, /signup, /auth/callback
- [ ] Private Gruppe (app)/ mit Auth-Guard im +layout.ts
- [ ] App-Shell: Sidebar, Topbar, Theme-Toggle
- [ ] Session-Handling, Logout, Passwort zurücksetzen

</details>

## Phase 2 – Datenbankmodell & RLS
<details><summary>Details anzeigen</summary>

- [ ] Tabellen: profiles, folders, documents, document_versions, annotations, reminders, extracted_text
- [ ] RLS-Policies: owner = auth.uid(), bei Child-Tabellen Join auf documents.owner
- [ ] Index auf extracted_text.tsv
- [ ] Seed-Skript für Dev-Daten

</details>

## Phase 3 – Storage & Upload
<details><summary>Details anzeigen</summary>

- [ ] Storage-Bucket docs (privat) in Supabase anlegen
- [ ] Upload-Flows: Drag&Drop, Foto → Crop → PDF (pdf-lib)
- [ ] Nach Upload DB-Eintrag in documents erzeugen
- [ ] Soft-Delete: deleted_at setzen, Papierkorb-Ansicht

</details>

## Phase 4 – App-Navigation & Kernseiten
<details><summary>Details anzeigen</summary>

- [ ] (app)/home: Übersicht
- [ ] (app)/folders/[id]: Dokumentliste/Grid
- [ ] (app)/documents/upload: Upload-Seite
- [ ] (app)/documents/[id]: PDF-Viewer (pdf.js)
- [ ] (app)/search: Suche
- [ ] (app)/reminders: Erinnerungen CRUD
- [ ] (app)/trash: Papierkorb
- [ ] (app)/profile, (app)/settings: Profil, Einstellungen

</details>

## Phase 5 – Dokumentaktionen & Dialoge
<details><summary>Details anzeigen</summary>

- [ ] Umbenennen, Verschieben, Löschen/Wiederherstellen
- [ ] Dialoge (Move, Rename, Delete), Toaster
- [ ] Versionierung bei Re-Upload

</details>

## Phase 6 – Edge Functions
<details><summary>Details anzeigen</summary>

- [ ] sign-download-url: Signierte Downloads
- [ ] extract-text: PDF-Text/OCR nach extracted_text
- [ ] generate-thumbnail: Thumbnails
- [ ] reminders-cron: tägliche Erinnerungsauswertung
- [ ] admin-gc: alte Soft-Deletes entfernen

</details>

## Phase 7 – PDF-Viewer & Annotationen
<details><summary>Details anzeigen</summary>

- [ ] pdf.js Integration
- [ ] Annotationen (Highlight, Notiz) speichern/anzeigen

</details>

## Phase 8 – Erinnerungen (UI + Cron)
<details><summary>Details anzeigen</summary>

- [ ] CRUD-UI für Reminders
- [ ] Cron-Funktion aktivieren
- [ ] E-Mail/Push-Benachrichtigung

</details>

## Phase 9 – Suche
<details><summary>Details anzeigen</summary>

- [ ] extract-text nach Upload triggern
- [ ] Volltextsuche über extracted_text.tsv
- [ ] UI: Snippets, Filter

</details>

## Phase 10 – PWA
<details><summary>Details anzeigen</summary>

- [ ] vite-plugin-pwa einrichten
- [ ] manifest.json konfigurieren (Icons, Farben)
- [ ] SW-Strategie (App-Shell, keine privaten PDFs)

</details>

## Phase 11 – Qualität & Sicherheit
<details><summary>Details anzeigen</summary>

- [ ] Edge-Cases prüfen (Dateitypen, Uploadgröße, Abbrüche)
- [ ] Tests: Unit, Komponenten, E2E
- [ ] Logging/Monitoring
- [ ] Security-Check: RLS, Storage privat, keine Secrets im Client

</details>

## Phase 12 – Deployment
<details><summary>Details anzeigen</summary>

- [ ] Frontend: Vercel/Cloudflare Pages
- [ ] Supabase Edge Functions deployen
- [ ] ENV-Variablen für Prod setzen

</details>

## Phase 13 – Landingpage (separates Projekt)
<details><summary>Details anzeigen</summary>

- [ ] Marketing-Seite mit Preisen/Features/FAQ
- [ ] CTAs: „Jetzt starten“ → Link zur App

</details>

## Phase 14 – Stripe (Ende)
<details><summary>Details anzeigen</summary>

- [ ] DB-Erweiterung: profiles.stripe_customer_id, subscriptions
- [ ] Server-Routes: create-checkout, create-portal
- [ ] Edge Function: stripe-webhook
- [ ] Billing-UI: (app)/account/billing
- [ ] Usage/Quoten pro Plan
- [ ] Tests mit Stripe Test-Mode

</details>
