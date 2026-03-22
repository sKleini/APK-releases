# Sicherheitshinweise

## APK-Integrität verifizieren

Vor der Installation sollte jede APK auf Integrität geprüft werden. Jedes App-Verzeichnis enthält eine `checksums.txt` mit SHA256-Hashes.

### Prüfung unter Linux/macOS

```bash
# Beispiel für Lock
cd Lock/
sha256sum -c checksums.txt
```

### Prüfung unter Windows (PowerShell)

```powershell
# Beispiel für Lock
Get-FileHash Lock\Lock.apk -Algorithm SHA256
# Ausgabe mit dem Wert in checksums.txt vergleichen
```

## Herkunft der APKs

Alle APKs in diesem Repository stammen direkt aus den folgenden Upstream-Repositories:

| App | Quelle |
|-----|--------|
| APK-installer | https://github.com/sKleini/APK-installer |
| Lock | https://github.com/sKleini/Lock |
| bxLock | https://github.com/sKleini/bxLock |

Der genaue Upstream-Commit, dem jede APK entspricht, ist in der jeweiligen `VERSION`-Datei vermerkt.

## Sicherheitsbedenken melden

Bei Sicherheitsproblemen (z. B. kompromittierte APK, falsche Prüfsummen):

1. Öffne ein Issue im Repository
2. Beschreibe das Problem so detailliert wie möglich
3. Verlinke den betroffenen Commit oder die betroffene Datei

## Hinweis zur Android-Sicherheit

- APKs aus diesem Repository sind **nicht** über den Google Play Store signiert
- Aktiviere „Installation aus unbekannten Quellen" nur temporär
- Deaktiviere diese Option nach der Installation wieder
- Vertraue APKs nur, wenn du die Prüfsumme verifiziert hast
