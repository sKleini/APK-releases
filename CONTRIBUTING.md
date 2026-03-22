# Beitragsleitfaden

## Zweck dieses Repositories

Dieses Repository spiegelt APK-Releases der folgenden Upstream-Projekte wider:

| App | Upstream-Repository |
|-----|---------------------|
| APK-installer | https://github.com/sKleini/APK-installer |
| Lock | https://github.com/sKleini/Lock |
| bxLock | https://github.com/sKleini/bxLock |

## Wie wird ein Update eingepflegt?

### 1. Upstream auf neue Releases prüfen

Besuche das jeweilige Upstream-Repository und prüfe, ob neue Commits oder Releases vorliegen.

### 2. APK herunterladen und verifizieren

Lade die neue APK aus dem Upstream-Release herunter und verifiziere sie:

```bash
# Prüfsumme des neuen APK notieren
sha256sum neue-app.apk
```

### 3. APK-Datei aktualisieren

Ersetze die vorhandene APK im entsprechenden Verzeichnis:

```bash
# Beispiel für Lock (Stable)
cp neue-lock.apk Lock/Lock.apk

# Beispiel für Lock (Develop)
cp neue-lock-dev.apk Lock/develop/Lock.apk
```

### 4. VERSION-Datei aktualisieren

Aktualisiere die `VERSION`-Datei im jeweiligen App-Verzeichnis:

```
upstream_commit: <vollständiger SHA des Upstream-Commits>
upstream_date: YYYY-MM-DD
updated: YYYY-MM-DD
```

### 5. Prüfsummen neu generieren

```bash
# Im jeweiligen App-Verzeichnis
cd Lock/
sha256sum Lock.apk > checksums.txt
sha256sum develop/Lock.apk >> checksums.txt
```

### 6. CHANGELOG.md aktualisieren

Füge einen neuen Eintrag im `CHANGELOG.md` hinzu:

```markdown
### YYYY-MM-DD
- Upstream-Commit: [kurzHash](vollständige URL)
```

### 7. Commit erstellen

Verwende ein aussagekräftiges Commit-Format:

```
chore(lock): Update auf Upstream-Commit abc1234

- Upstream-Quelle: https://github.com/sKleini/Lock/commit/abc1234...
- Vorheriger Commit: xyz5678
```

## Verzeichnisstruktur

```
AppName/
├── AppName.apk      # Stabile, getestete Version
├── develop/
│   └── AppName.apk  # Neueste Entwicklungsversion (kann instabil sein)
├── VERSION          # Upstream-Commit-Referenz
└── checksums.txt    # SHA256-Prüfsummen beider APKs
```

## Stabiler vs. Develop-Kanal

- **Stabil (`/AppName.apk`)**: Getestete, empfohlene Version für den Alltagseinsatz
- **Develop (`/develop/AppName.apk`)**: Neueste Version direkt aus dem Entwicklungszweig – kann Bugs enthalten

## Commit-Konventionen

Verwende [Conventional Commits](https://www.conventionalcommits.org/):

- `chore(app-name): Update auf Upstream-Commit xyz`
- `docs: README aktualisieren`
- `fix(bxlock): Fehlerhafte APK ersetzen`
