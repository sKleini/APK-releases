# APK-Releases

Zentrales Repository zur Verteilung von Android-APKs für Projekte von [sKleini](https://github.com/sKleini).

## Enthaltene Apps

| App | Beschreibung | Upstream-Repo |
|-----|-------------|---------------|
| **APK-installer** | Android-App zum einfachen Installieren von APK-Dateien | [sKleini/APK-installer](https://github.com/sKleini/APK-installer) |
| **Lock** | Sperr-App für Android | [sKleini/Lock](https://github.com/sKleini/Lock) |
| **bxLock** | Erweiterte Sperr-App (Box-Variante) | [sKleini/bxLock](https://github.com/sKleini/bxLock) |

## Repository-Struktur

```
APK-releases/
├── APK-installer/
│   ├── APK-installer.apk       # Stabile Release-Version
│   ├── VERSION                 # Aktuelle Version & Upstream-Commit
│   └── checksums.txt           # SHA256-Prüfsummen
├── Lock/
│   ├── Lock.apk                # Stabile Release-Version
│   ├── develop/
│   │   └── Lock.apk            # Entwicklungsversion (Pre-Release)
│   ├── VERSION                 # Aktuelle Version & Upstream-Commit
│   └── checksums.txt           # SHA256-Prüfsummen
├── bxLock/
│   ├── bxLock.apk              # Stabile Release-Version
│   ├── develop/
│   │   └── bxLock.apk          # Entwicklungsversion (Pre-Release)
│   ├── VERSION                 # Aktuelle Version & Upstream-Commit
│   └── checksums.txt           # SHA256-Prüfsummen
├── .github/
│   └── workflows/
│       └── upstream-check.yml  # Automatische Upstream-Überwachung
├── CHANGELOG.md                # Versionshistorie
├── CONTRIBUTING.md             # Beitragsleitfaden
└── SECURITY.md                 # Sicherheitshinweise
```

## Installation

1. Lade die gewünschte APK-Datei herunter
2. **Prüfsumme verifizieren** (empfohlen):
   ```bash
   sha256sum -c checksums.txt
   ```
3. Auf dem Android-Gerät: Einstellungen → Sicherheit → „Installation aus unbekannten Quellen" aktivieren
4. APK-Datei öffnen und Installation bestätigen

## Versionen

- **Stabile Version**: Die APK im Hauptverzeichnis (`/Lock/Lock.apk`)
- **Entwicklungsversion**: Die APK im `develop/`-Unterordner – enthält neueste Features, kann instabil sein

## Prüfsummen verifizieren

Jede App enthält eine `checksums.txt` mit SHA256-Hashes zur Integritätsprüfung:

```bash
# Beispiel für Lock
cd Lock/
sha256sum -c checksums.txt
```

## Wartungsstatus

![Maintenance Status](https://img.shields.io/badge/maintenance-archived-red.svg)

> **Hinweis:** Dieses Repository wurde zuletzt im September 2021 aktualisiert.
> Die APKs entsprechen dem Stand der Upstream-Repositories zu diesem Zeitpunkt.

## Lizenz

Siehe die jeweiligen Upstream-Repositories für Lizenzinformationen.
