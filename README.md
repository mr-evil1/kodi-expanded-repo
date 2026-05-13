# Kodi Expanded Repo

Konform Kodi Addons

---

## Installation in Kodi

### 1. Unbekannte Quellen erlauben
`Einstellungen → System → Add-ons → Unbekannte Quellen` → **Ein**

### 2. Repository-Quelle hinzufügen
`Einstellungen → Dateimanager → Quelle hinzufügen`

```
https://mr-evil1.github.io/kodi-expanded-repo
```

Name: `Kodi Expanded Repo`

### 3. Repository-Addon installieren
`Add-ons → Add-on-Browser → Aus ZIP installieren`
→ Quelle `Kodi Expanded Repo` → `repository.kodi.expanded` → ZIP installieren

### 4. Addons installieren
`Add-ons → Add-on-Browser → Aus Repository installieren → Kodi Expanded Repo`

---

## GitHub Pages aktivieren

Damit die Repo-URLs (`mr-evil1.github.io/kodi-expanded-repo/...`) funktionieren:

1. GitHub → Settings → Pages
2. Source: `Deploy from a branch`
3. Branch: `main` / `/ (root)`
4. Save

---

## Neues Addon hinzufügen

1. Ordner `<dein.addon.id>/` direkt im Root anlegen
2. `addon.xml` (Pflicht) + Dateien hinzufügen
3. Push auf `main` → GitHub Actions baut automatisch:
   - `addons.xml` + `addons.xml.md5` neu
   - `<addon_id>-<version>.zip` im Addon-Ordner

### Mindeststruktur

```
dein.addon.id/
├── addon.xml        ← Pflicht
├── default.py       ← Einstiegspunkt
├── icon.png         ← Optional
└── fanart.jpg       ← Optional
```

---

## Repo-Struktur

```
kodi-expanded-repo/
├── .github/
│   ├── workflows/update_repo.yml
│   └── scripts/
│       ├── build_repo.py
│       └── zip_addons.py
├── repository.kodi.expanded/
│   ├── addon.xml
│   └── repository.kodi.expanded-1.0.0.zip  ← auto
├── dein.addon.id/
│   ├── addon.xml
│   └── dein.addon.id-1.0.0.zip             ← auto
├── addons.xml                               ← auto
└── addons.xml.md5                           ← auto
```
