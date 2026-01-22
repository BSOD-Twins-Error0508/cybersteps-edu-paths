# 🌐 [Aufgaben-Titel]

**Kurs:** [Kursname] | **Datum:** [TT.MM.JJJJ]

---

## 📋 Aufgabenstellung

**Thema:** [z.B. Responsive Landing Page]

**Ziel:** [Kurze Beschreibung]

**Tech Stack:**
- HTML5
- CSS3 (Flexbox/Grid)
- JavaScript (ES6+)

---

## 🖥️ Demo & Screenshots

**Live:** [https://benutzername.github.io/projekt](https://benutzername.github.io/projekt)

![Desktop](./screenshots/desktop.png) ![Mobile](./screenshots/mobile.png)

---

## 📂 Struktur

```
projekt/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
└── assets/
    └── bilder/
```

---

## 💻 Implementierung

### HTML
```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Titel]</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header><!-- Navigation --></header>
    <main><!-- Inhalt --></main>
    <footer><!-- Fußzeile --></footer>
</body>
</html>
```

### CSS
```css
:root {
    --primär: #007bff;
    --text: #333;
}

/* Mobile First */
.container { ... }

@media (min-width: 768px) {
    /* Tablet */
}

@media (min-width: 1024px) {
    /* Desktop */
}
```

### JavaScript
```javascript
'use strict';

const navbar = document.querySelector('.navbar');

function toggleMenu() {
    navbar.classList.toggle('active');
}

document.addEventListener('DOMContentLoaded', init);
```

---

## 🧪 Testing

### Browser-Kompatibilität
| Browser | Status |
|---------|--------|
| Chrome | ✅ |
| Firefox | ✅ |
| Safari | ✅ |
| Edge | ✅ |

### Responsive
| Gerät | Status |
|-------|--------|
| Desktop (1920x1080) | ✅ |
| Tablet (768x1024) | ✅ |
| Mobile (375x667) | ✅ |

### Validierung
- ✅ HTML: W3C validiert
- ✅ CSS: W3C validiert
- ✅ Barrierefreiheit: WCAG AA

---

## ✅ Fragen & Antworten

**Frage 1:** [Frage]  
**Antwort 1:** [Antwort]

---

## 💡 Erkenntnisse

**Gelernt:**
- [Konzept 1]
- [Konzept 2]

**Design-Entscheidungen:**
- [Farben, Schriften, Layout]

**Verbesserungen:**
- [ ] Dark Mode
- [ ] Animationen
- [ ] Performance

---

## 🚀 Deployment

**GitHub Pages:**
```bash
git add .
git commit -m "Website deployen"
git push origin main
```

---

**Status:** ✅ Abgeschlossen | **Zeit:** ~[X] Std.
