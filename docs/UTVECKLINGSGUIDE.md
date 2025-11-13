# Utvecklingsguide - Telink Presentation

## 🚀 Kom igång

### Förutsättningar
- **Code Editor:** VS Code (rekommenderat) eller annan modern editor
- **Browser:** Chrome eller Edge (bäst support för glassmorphism)
- **Live Server:** För lokal utveckling (VS Code extension rekommenderas)

### Installation

1. **Öppna projektet i VS Code:**
   ```bash
   code telink-presentation-project
   ```

2. **Installera rekommenderade extensions:**
   - VS Code kommer att föreslå extensions automatiskt
   - Eller tryck `Cmd/Ctrl + Shift + P` → "Extensions: Show Recommended Extensions"

3. **Starta Live Server:**
   - Högerklicka på `index.html`
   - Välj "Open with Live Server"
   - Eller tryck `Alt + L, Alt + O`

4. **Öppna i browser:**
   - Presentationen öppnas automatiskt på `http://localhost:5500`

## 📁 Projektstruktur

```
telink-presentation-project/
├── index.html              # Huvudfil - presentationen
├── README.md               # Användarguide
├── CHANGELOG.md            # Versionshistorik
├── .gitignore             # Git ignore-regler
├── .vscode/               # VS Code konfiguration
│   ├── settings.json      # Editor settings
│   └── extensions.json    # Rekommenderade extensions
├── docs/                  # Dokumentation
│   ├── LEVERANS.md        # Leveransöversikt
│   └── presentation-plan.yaml  # Planeringsplan
└── assets/                # Framtida assets (bilder, etc.)
```

## 🛠️ Vanliga Ändringar

### 1. Uppdatera Texter

**Hero-sektion:**
```html
<!-- Hitta runt rad 800 -->
<h1 class="h1">Automatisera era inkommande och utgående samtal</h1>
<p class="lead">Telinks AI-assistent hanterar...</p>
```

**KPI-siffror:**
```html
<!-- Hitta runt rad 1100 -->
<div class="kpi-value" data-target="40">0</div>
```
Ändra `data-target` till önskat värde.

### 2. Lägg till Nytt Samtals-Scenario

**Steg 1:** Hitta scenarios-objektet (runt rad 500 i JavaScript):
```javascript
const scenarios = {
  booking: { ... },
  faq: { ... },
  support: { ... },
  // Lägg till här:
  newScenario: {
    messages: [
      { speaker: 'customer', text: 'Hej...' },
      { speaker: 'ai', text: 'Svar...' }
    ],
    backendSteps: [
      { step: 1, delay: 500 }
    ]
  }
};
```

**Steg 2:** Lägg till scenario-kort i HTML (runt rad 850):
```html
<div class="scenario-card" data-scenario="newScenario">
  <div class="scenario-icon">🎯</div>
  <div class="scenario-title">Nytt Scenario</div>
  <div class="scenario-desc">Beskrivning</div>
</div>
```

### 3. Ändra Färgpalett

**CSS-variabler (runt rad 25):**
```css
:root {
  --primary: #00D9A3;     /* Cyan/Grön */
  --secondary: #0066FF;   /* Blå */
  --bg-dark: #0A0F1A;     /* Mörk bakgrund */
}
```

Ändra hex-värden till önskade färger.

### 4. Uppdatera Paket-information

**Hitta packages-grid (runt rad 1150):**
```html
<div class="package-card">
  <div class="package-name">Bas</div>
  <div class="package-desc">För enklare behov...</div>
  <ul class="package-features">
    <li>Feature 1</li>
    <li>Feature 2</li>
  </ul>
</div>
```

## 🎨 Design System

### Färger
```css
--primary: #00D9A3       /* Telink cyan/grön */
--secondary: #0066FF     /* Telink blå */
--bg-dark: #0A0F1A       /* Mörk bakgrund */
--bg-darker: #000A1A     /* Mörkare bakgrund */
--text: #E6F0FF          /* Ljus text */
--text-muted: #9FB3C8    /* Dämpad text */
```

### Spacing (8pt grid)
```css
--space-xs: 8px
--space-sm: 16px
--space-md: 24px
--space-lg: 32px
--space-xl: 48px
--space-xxl: 64px
```

### Typografi
```css
H1: 56px / bold         /* Hero */
H2: 42px / bold         /* Sektioner */
H3: 28px / semibold     /* Sub-headings */
Body: 18px / regular    /* Normal text */
```

### Glassmorphism
```css
background: rgba(255, 255, 255, 0.05);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.1);
box-shadow: 0 8px 32px rgba(0, 217, 163, 0.15);
```

## 🔧 Komponenter

### Glass Card
```html
<div class="glass-card">
  <!-- Content -->
</div>
```

### Feature Card
```html
<div class="glass-card feature-card">
  <div class="feature-icon">📊</div>
  <div class="feature-title">Titel</div>
  <div class="feature-desc">Beskrivning</div>
</div>
```

### KPI Counter
```html
<div class="kpi-card">
  <div class="kpi-value" data-target="85">0</div>
  <div class="kpi-label">85%</div>
  <div class="kpi-desc">Beskrivning</div>
</div>
```

## 🐛 Debugging

### Vanliga Problem

**Problem:** Glassmorphism syns inte
- **Lösning:** Kontrollera att du använder Chrome/Edge. Firefox kan ha begränsad support.

**Problem:** Animationer är hackiga
- **Lösning:** Stäng andra tunga program. Kontrollera GPU-acceleration i browser.

**Problem:** Keyboard shortcuts fungerar inte
- **Lösning:** Klicka i dokumentet först för att ge fokus.

**Problem:** Samtals-simulator startar inte
- **Lösning:** Öppna Developer Console (F12) och leta efter JavaScript-fel.

### Developer Console
Öppna med `F12` eller `Cmd/Ctrl + Shift + I`:
- **Console:** För JavaScript-fel
- **Network:** För loading-problem
- **Elements:** För HTML/CSS-inspektion
- **Performance:** För performance-analys

## 📊 Performance Optimization

### Nuvarande Metrics
- ✅ Initial load: <3 sekunder
- ✅ Animations: 60fps
- ✅ Total size: ~57KB (inga externa dependencies)

### Tips för Bättre Performance
1. **Optimera bilder:** Om du lägger till bilder, använd WebP-format
2. **Lazy load:** Off-screen content laddas när det behövs
3. **CSS will-change:** Redan implementerat för animationer
4. **Debounce events:** Scroll/resize events är optimerade

## 🧪 Testing

### Browsers att Testa
- ✅ Chrome/Edge (primär)
- ✅ Firefox
- ✅ Safari
- ⚠️ Äldre browsers (fallback till enklare styling)

### Skärmstorlekar
- Desktop: 1920x1080 (optimal)
- Laptop: 1440x900
- Tablet: 1024x768
- Mobile: 375x667 (begränsad support)

### Checklist
- [ ] Alla sektioner laddas korrekt
- [ ] Keyboard navigation fungerar
- [ ] Progress stepper uppdateras
- [ ] Samtals-simulator kan spelas/pausas/resettas
- [ ] Alla 3 scenarion fungerar
- [ ] Backend-visualisering aktiveras
- [ ] KPI-räknare animerar
- [ ] Integration hub visar connections
- [ ] Paket-kort är klickbara
- [ ] CTA-knappar är synliga

## 🚀 Deployment

### Hosting Options

**1. GitHub Pages (Gratis)**
```bash
# Pusha till GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin <your-repo-url>
git push -u origin main

# Aktivera GitHub Pages i repo settings
```

**2. Netlify (Gratis)**
- Dra och släpp mappen på netlify.com
- Eller connect GitHub repo för auto-deploy

**3. Vercel (Gratis)**
```bash
npm i -g vercel
vercel
```

**4. Lokal USB-stick (För Offline Presentations)**
- Kopiera hela mappen till USB
- Öppna `index.html` direkt i browser

## 📝 Git Workflow

### Första Commit
```bash
git init
git add .
git commit -m "feat: initial presentation setup v1.0.0"
```

### Feature Development
```bash
git checkout -b feature/new-scenario
# Gör ändringar
git add .
git commit -m "feat: add follow-up call scenario"
git checkout main
git merge feature/new-scenario
```

### Version Tags
```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin v1.0.0
```

## 🤝 Contribution Guidelines

Om flera utvecklare jobbar på projektet:

1. **Skapa en branch** för varje feature
2. **Skriv tydliga commit messages:**
   - `feat:` för nya features
   - `fix:` för bugfixar
   - `docs:` för dokumentation
   - `style:` för styling-ändringar
3. **Testa lokalt** innan merge till main
4. **Uppdatera CHANGELOG.md** för varje ändring

## 📚 Resurser

### Documentation
- [MDN Web Docs](https://developer.mozilla.org/)
- [CSS Tricks - Glassmorphism](https://css-tricks.com/glassmorphism/)
- [Web.dev - Performance](https://web.dev/performance/)

### Tools
- [Can I Use](https://caniuse.com/) - Browser compatibility
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [PageSpeed Insights](https://pagespeed.web.dev/)

## 💡 Tips & Tricks

### VS Code Shortcuts
- `Ctrl + /` - Kommentera kod
- `Alt + Up/Down` - Flytta rader
- `Ctrl + D` - Multi-cursor på samma ord
- `F2` - Rename symbol

### Live Reload
Live Server ger automatisk reload vid ändringar. Spara filen så uppdateras browsern!

### Custom CSS Variables
Lägg till egna variabler i `:root` för enkel anpassning:
```css
:root {
  --my-custom-color: #FF6B6B;
  --my-spacing: 20px;
}
```

## ❓ Support

### Var Hittar Jag Hjälp?
1. **README.md** - Användarguide för presentatörer
2. **Denna fil** - Teknisk utvecklingsguide
3. **presentation-plan.yaml** - Design rationale och research
4. **Code comments** - Inline dokumentation i index.html

### Kontakt
Om du behöver hjälp med större ändringar, kontakta original-utvecklaren eller din tech lead.

---

**Happy Coding! 🎉**

**Last Updated:** November 2025  
**Version:** 1.0.0
