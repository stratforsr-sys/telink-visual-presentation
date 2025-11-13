# 🚀 Snabbstart - Telink Presentation

## För VS Code-användare (Rekommenderat)

### Steg 1: Öppna Projektet
```bash
cd telink-presentation-project
code .
```

### Steg 2: Installera Extensions
När VS Code öppnas kommer du att se ett meddelande: "This workspace has extension recommendations"
- Klicka **"Install All"** för bästa utvecklingsupplevelse

**Rekommenderade extensions:**
- ✅ Live Server - För live preview
- ✅ Prettier - För kod-formatering
- ✅ Auto Rename Tag - HTML helper
- ✅ HTML CSS Support - IntelliSense

### Steg 3: Starta Live Server
**Metod 1:** Högerklicka på `index.html` → "Open with Live Server"  
**Metod 2:** Tryck `Alt + L, Alt + O`  
**Metod 3:** Klicka "Go Live" i status bar (nere till höger)

### Steg 4: Presentationen Öppnas!
Browser öppnas automatiskt på: `http://localhost:5500`

---

## För Andra Editors

### Steg 1: Öppna Projektet
Öppna mappen i din editor (Sublime, Atom, etc.)

### Steg 2: Öppna i Browser
Dubbelklicka på `index.html` eller dra filen till browser

**OBS:** Vissa features fungerar bättre med en lokal server. Alternativ:
```bash
# Python 3
python -m http.server 8000

# Node.js
npx http-server
```

---

## Snabbtester

### ✅ Verkar Allt Fungera?
1. Öppna presentationen
2. Tryck **→** (höger pil)
3. Du bör scrollas till nästa sektion
4. Tryck **→** igen tills du når demo-sektionen (sektion 3)
5. Tryck **Space** för att starta samtalet
6. Du bör se text skrivas fram med typewriter-effekt
7. Tryck **R** för att resetta
8. Välj ett annat scenario och tryck **Space** igen

**Om allt ovan fungerar → Du är redo! 🎉**

---

## Första Anpassningar

### Ändra Företagsnamn
1. Öppna `index.html`
2. Sök efter "Telink" (Ctrl/Cmd + F)
3. Ersätt med ditt företagsnamn
4. Spara (Ctrl/Cmd + S)
5. Sidan uppdateras automatiskt (om Live Server är aktivt)

### Ändra Färger
1. Öppna `index.html`
2. Leta upp `:root` CSS-variablerna (runt rad 25)
3. Ändra:
   ```css
   --primary: #00D9A3;      /* Din primärfärg */
   --secondary: #0066FF;    /* Din sekundärfärg */
   ```
4. Spara och se resultat direkt!

### Uppdatera KPI-siffror
1. Hitta `.kpi-value` elements (runt rad 1100)
2. Ändra `data-target="40"` till ditt värde
3. Uppdatera texten bredvid för att matcha

---

## Keyboard Shortcuts i Presentationen

| Tangent | Funktion |
|---------|----------|
| → | Nästa sektion |
| ← | Föregående sektion |
| Space | Play/Pause demo |
| R | Reset demo |
| 1-9 | Hoppa till sektion |
| F11 | Fullscreen (Windows/Linux) |
| Cmd+Ctrl+F | Fullscreen (Mac) |

---

## Nästa Steg

### För Presentatörer
📖 Läs **README.md** för komplett guide om hur du använder presentationen under säljmöten

### För Utvecklare
🛠️ Läs **docs/UTVECKLINGSGUIDE.md** för teknisk dokumentation och hur du gör ändringar

### För PM/Managers
📋 Läs **docs/LEVERANS.md** för översikt av vad som ingår och project scope

---

## Snabb Felsökning

### ❌ Glassmorphism syns inte
→ Använd Chrome eller Edge (bäst support)

### ❌ Animationer är hackiga
→ Stäng andra program, testa i Chrome

### ❌ Live Server funkar inte
→ Kontrollera att extensionen är installerad. Starta om VS Code.

### ❌ Keyboard shortcuts fungerar inte
→ Klicka i dokumentet först (ge fokus till sidan)

### ❌ Samtals-demo startar inte
→ Öppna Developer Console (F12) och leta efter fel i röd text

---

## Support

**Dokumentation:**
- `README.md` - Användarguide
- `docs/UTVECKLINGSGUIDE.md` - Teknisk guide
- `docs/presentation-plan.yaml` - Design & research

**Problem?** Öppna Developer Console (F12) och leta efter error messages.

---

**Lycka till! 🚀**

*Total setup-tid: ~5 minuter*
