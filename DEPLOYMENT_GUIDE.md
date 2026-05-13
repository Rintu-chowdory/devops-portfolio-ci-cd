# GitHub Pages Deployment Guide

## Automatisches Deployment mit GitHub Actions

Diese Anleitung erklärt, wie Sie GitHub Pages mit automatischem Deployment einrichten.

### Schritt 1: GitHub Pages aktivieren

1. Gehen Sie zu Ihrem Repository: https://github.com/Rintu-chowdory/devops-portfolio-ci-cd
2. Klicken Sie auf **Settings** (Einstellungen)
3. Wählen Sie im linken Menü **Pages**
4. Unter "Build and deployment":
   - Wählen Sie **GitHub Actions** als Source
   - Dies ermöglicht automatisches Deployment über Workflows

### Schritt 2: GitHub Actions Workflows aktivieren

1. Gehen Sie zum Tab **Actions** in Ihrem Repository
2. Sie sollten die Workflows sehen:
   - `Build and Deploy to GitHub Pages` (deploy.yml)
   - `Code Quality Checks` (quality.yml)
3. Klicken Sie auf jeden Workflow und aktivieren Sie ihn

### Schritt 3: Deployment testen

1. Pushen Sie eine Änderung zu `main`:
   ```bash
   git add .
   git commit -m "test: trigger deployment"
   git push origin main
   ```

2. Gehen Sie zum Tab **Actions** und beobachten Sie den Workflow:
   - `Build and Deploy to GitHub Pages` sollte starten
   - Warten Sie, bis der Build erfolgreich ist
   - Der Deploy-Job wird automatisch ausgelöst

### Schritt 4: Website besuchen

Nach erfolgreichem Deployment ist die Website verfügbar unter:
```
https://rintu-chowdory.github.io/devops-portfolio-ci-cd/
```

## Manuelle Deployment-Schritte (falls nötig)

### Build lokal erstellen

```bash
cd /home/ubuntu/devops-portfolio-ci-cd
GITHUB_PAGES=true pnpm run build
```

Dies erstellt die `dist/` Verzeichnis mit allen statischen Dateien.

### Auf `gh-pages` Branch deployen

```bash
# Installieren Sie gh-pages (falls nicht vorhanden)
pnpm add -D gh-pages

# Deploy
pnpm run deploy
```

## Troubleshooting

### Workflow wird nicht ausgelöst

- Überprüfen Sie, dass die Workflows in `.github/workflows/` existieren
- Gehen Sie zu **Settings** → **Actions** → **General**
- Stellen Sie sicher, dass "Allow all actions and reusable workflows" ausgewählt ist

### Build schlägt fehl

- Überprüfen Sie die Logs im **Actions** Tab
- Stellen Sie sicher, dass alle Dependencies installiert sind:
  ```bash
  pnpm install
  ```
- Führen Sie lokal einen Build durch:
  ```bash
  GITHUB_PAGES=true pnpm run build
  ```

### Website wird nicht angezeigt

- Warten Sie 1-2 Minuten nach dem Deploy
- Leeren Sie den Browser-Cache (Ctrl+Shift+Delete)
- Überprüfen Sie, dass GitHub Pages in den Settings aktiviert ist

## Umgebungsvariablen

Der Build-Prozess verwendet folgende Variablen:

- `GITHUB_PAGES=true` - Setzt den korrekten Base Path für GitHub Pages
- `VITE_APP_TITLE` - Titel der Anwendung
- `VITE_APP_ID` - App-Identifier

Diese sind in der `deploy.yml` konfiguriert.

## Weitere Konfiguration

### Custom Domain (optional)

1. Gehen Sie zu **Settings** → **Pages**
2. Unter "Custom domain" geben Sie Ihre Domain ein
3. Folgen Sie den DNS-Konfigurationsschritten

### Branch für Deployment ändern

1. Gehen Sie zu **Settings** → **Pages**
2. Ändern Sie unter "Build and deployment" den Branch
3. Standard ist `main`

## Support

Für Probleme oder Fragen:
- Überprüfen Sie die GitHub Actions Logs
- Konsultieren Sie die [GitHub Pages Dokumentation](https://docs.github.com/en/pages)
- Erstellen Sie ein Issue im Repository
