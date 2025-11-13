# Assets

Denna mapp är för framtida assets som bilder, ikoner, videos, etc.

## 📁 Rekommenderad Struktur

```
assets/
├── images/           # Bilder och screenshots
│   ├── logo.png
│   ├── hero-bg.jpg
│   └── screenshots/
├── icons/            # Ikoner och små grafik
│   ├── favicon.ico
│   └── app-icon.png
├── fonts/            # Custom fonts (om behövs)
└── videos/           # Demo-videos (om behövs)
```

## 💡 Tips

### Bilder
- **Format:** WebP för bäst kompression, PNG/JPG som fallback
- **Optimera:** Använd TinyPNG eller ImageOptim före upload
- **Storlekar:** Responsiva varianter (1x, 2x, 3x)

### Ikoner
- **Format:** SVG för skalbarhet
- **Fallback:** PNG för äldre browsers
- **Size:** 16x16, 32x32, 64x64, 128x128, 256x256

### Fonts
- Om du vill använda custom fonts, lägg dem här
- Använd WOFF2-format för modern browsers
- Inkludera fallback system fonts

## 🎨 Användning i HTML

```html
<!-- Bilder -->
<img src="assets/images/logo.png" alt="Telink Logo">

<!-- Bakgrundsbilder -->
<div style="background-image: url('assets/images/hero-bg.jpg')"></div>

<!-- Favicon -->
<link rel="icon" href="assets/icons/favicon.ico">
```

## 📏 Bildstorlekar för Presentationen

- **Hero background:** 1920x1080 (Full HD)
- **Feature ikoner:** 64x64 eller SVG
- **Screenshots:** 1440x900 (optimalt för presentation)
- **Logotyper:** SVG eller PNG 256x256

---

*Denna mapp är för närvarande tom. Lägg till assets när de behövs.*
