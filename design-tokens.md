# Design Tokens — Médano & DataTrackers
> Fuente de verdad para todos los valores de diseño del sistema.  
> **Regla de Oro:** Ningún archivo HTML/CSS puede usar un valor en hexadecimal o número crudo — siempre referenciar una variable de este documento.

---

## 1. COLOR

### 1.1 Paleta Primaria (Brand Identity)
Extraída del Manual de Marca 2024 — Sección 02.1

```css
:root {
  /* Azul Marino — Identidad principal */
  --color-brand-navy:        #00246b;   /* PANTONE P100-16C — C:100 M:100 Y:32 K:3  */
  --color-brand-royal:       #1a4793;   /* PANTONE P102-8C  — C:97  M:87  Y:11 K:0  */
  --color-brand-mid:         #646caa;   /* PANTONE P102-6C  — C:75  M:63  Y:7  K:0  */
  --color-brand-light:       #b4b7d9;   /* PANTONE P102-2C  — C:35  M:29  Y:3  K:0  */
}
```

### 1.2 Paleta Semántica (UI System)
Derivada de la paleta primaria para uso en interfaces.

```css
:root {
  /* Fondos */
  --color-bg-base:           var(--color-brand-navy);      /* Fondo principal dark */
  --color-bg-surface:        var(--color-brand-royal);     /* Cards, módulos elevados */
  --color-bg-overlay:        rgba(0, 36, 107, 0.85);       /* Overlays y modales */
  --color-bg-subtle:         rgba(26, 71, 147, 0.12);      /* Hover states, zebra rows */

  /* Texto */
  --color-text-primary:      #ffffff;                      /* Texto sobre fondos oscuros */
  --color-text-secondary:    var(--color-brand-light);     /* Subtítulos, metadata */
  --color-text-muted:        rgba(180, 183, 217, 0.6);     /* Placeholders, disabled */
  --color-text-inverse:      var(--color-brand-navy);      /* Texto sobre fondos claros */

  /* Bordes */
  --color-border-default:    rgba(100, 108, 170, 0.3);     /* Bordes generales */
  --color-border-strong:     var(--color-brand-mid);       /* Bordes destacados */
  --color-border-subtle:     rgba(100, 108, 170, 0.12);    /* Separadores */

  /* Acento / Interactivos */
  --color-accent:            var(--color-brand-royal);     /* CTAs principales */
  --color-accent-hover:      var(--color-brand-mid);       /* Hover sobre CTAs */
  --color-accent-active:     var(--color-brand-navy);      /* Estado presionado */

  /* Feedback */
  --color-success:           #22c55e;                      /* Confirmaciones */
  --color-warning:           #f59e0b;                      /* Alertas */
  --color-error:             #ef4444;                      /* Errores */
  --color-info:              var(--color-brand-mid);       /* Información */
}
```

### 1.3 Gradientes de Marca

```css
:root {
  /* Gradiente principal — fondo hero / headers */
  --gradient-brand:
    linear-gradient(135deg, var(--color-brand-navy) 0%, var(--color-brand-royal) 60%, var(--color-brand-mid) 100%);

  /* Gradiente sutil — cards y superficies */
  --gradient-surface:
    linear-gradient(180deg, var(--color-brand-royal) 0%, var(--color-brand-navy) 100%);

  /* Gradiente overlay — sobre imágenes */
  --gradient-overlay:
    linear-gradient(to bottom, rgba(0,36,107,0) 0%, rgba(0,36,107,0.9) 100%);

  /* Gradiente de texto — para headings destacados */
  --gradient-text:
    linear-gradient(90deg, #ffffff 0%, var(--color-brand-light) 100%);
}
```

### 1.4 Tints (opacidades por token)

```css
:root {
  --color-brand-navy-75:     rgba(0, 36, 107, 0.75);
  --color-brand-navy-50:     rgba(0, 36, 107, 0.50);
  --color-brand-navy-25:     rgba(0, 36, 107, 0.25);

  --color-brand-royal-75:    rgba(26, 71, 147, 0.75);
  --color-brand-royal-50:    rgba(26, 71, 147, 0.50);
  --color-brand-royal-25:    rgba(26, 71, 147, 0.25);
}
```

---

## 2. TIPOGRAFÍA

### 2.1 Familias
Extraídas del Manual de Marca 2024 — Sección 02.2

```css
:root {
  /* Display / Titulares — Carácter de marca, bold */
  --font-display:     'Barlow Condensed', 'Oswald', sans-serif;

  /* Body / Cuerpo — Legibilidad en párrafos */
  --font-body:        'DM Sans', 'Mulish', sans-serif;

  /* Mono / Código — DataTrackers dashboards */
  --font-mono:        'JetBrains Mono', 'Fira Code', monospace;

  /* UI / Labels — Sistema, botones, navegación */
  --font-ui:          'DM Sans', sans-serif;
}
```

> **Nota de implementación:** Cargar desde Google Fonts:  
> `Barlow+Condensed:wght@400;600;700|DM+Sans:wght@300;400;500;600`

### 2.2 Escala Tipográfica (Type Scale)

```css
:root {
  /* --- Tamaños (fluid scale recomendada) --- */
  --text-xs:          0.75rem;    /*  12px */
  --text-sm:          0.875rem;   /*  14px */
  --text-base:        1rem;       /*  16px */
  --text-md:          1.125rem;   /*  18px */
  --text-lg:          1.25rem;    /*  20px */
  --text-xl:          1.5rem;     /*  24px */
  --text-2xl:         1.875rem;   /*  30px */
  --text-3xl:         2.25rem;    /*  36px */
  --text-4xl:         3rem;       /*  48px */
  --text-5xl:         3.75rem;    /*  60px */
  --text-6xl:         4.5rem;     /*  72px */

  /* --- Pesos --- */
  --font-weight-light:      300;
  --font-weight-regular:    400;
  --font-weight-medium:     500;
  --font-weight-semibold:   600;
  --font-weight-bold:       700;
  --font-weight-extrabold:  800;

  /* --- Interlineado (line-height) --- */
  --leading-none:     1;
  --leading-tight:    1.15;
  --leading-snug:     1.3;
  --leading-normal:   1.5;
  --leading-relaxed:  1.65;
  --leading-loose:    1.8;

  /* --- Espaciado entre letras (letter-spacing) --- */
  --tracking-tighter: -0.04em;
  --tracking-tight:   -0.02em;
  --tracking-normal:   0em;
  --tracking-wide:     0.05em;
  --tracking-wider:    0.1em;
  --tracking-widest:   0.2em;    /* Labels, caps, overlines */
}
```

### 2.3 Roles Tipográficos

```css
/* Roles semánticos — Aplicar en componentes */
:root {
  /* Hero / Display */
  --type-hero-size:       var(--text-5xl);
  --type-hero-weight:     var(--font-weight-bold);
  --type-hero-family:     var(--font-display);
  --type-hero-leading:    var(--leading-tight);
  --type-hero-tracking:   var(--tracking-tight);

  /* H1 */
  --type-h1-size:         var(--text-4xl);
  --type-h1-weight:       var(--font-weight-bold);
  --type-h1-family:       var(--font-display);
  --type-h1-leading:      var(--leading-tight);

  /* H2 */
  --type-h2-size:         var(--text-3xl);
  --type-h2-weight:       var(--font-weight-semibold);
  --type-h2-family:       var(--font-display);
  --type-h2-leading:      var(--leading-snug);

  /* H3 */
  --type-h3-size:         var(--text-2xl);
  --type-h3-weight:       var(--font-weight-semibold);
  --type-h3-family:       var(--font-body);
  --type-h3-leading:      var(--leading-snug);

  /* Body Large */
  --type-body-lg-size:    var(--text-md);
  --type-body-lg-weight:  var(--font-weight-regular);
  --type-body-lg-family:  var(--font-body);
  --type-body-lg-leading: var(--leading-relaxed);

  /* Body */
  --type-body-size:       var(--text-base);
  --type-body-weight:     var(--font-weight-regular);
  --type-body-family:     var(--font-body);
  --type-body-leading:    var(--leading-normal);

  /* Caption / Overline */
  --type-caption-size:    var(--text-sm);
  --type-caption-weight:  var(--font-weight-medium);
  --type-caption-tracking:var(--tracking-widest);

  /* Label / Button */
  --type-label-size:      var(--text-sm);
  --type-label-weight:    var(--font-weight-semibold);
  --type-label-tracking:  var(--tracking-wide);
}
```

---

## 3. ESPACIADO

### 3.1 Escala Base (4px grid)

```css
:root {
  --space-0:    0;
  --space-1:    0.25rem;   /*  4px */
  --space-2:    0.5rem;    /*  8px */
  --space-3:    0.75rem;   /* 12px */
  --space-4:    1rem;      /* 16px */
  --space-5:    1.25rem;   /* 20px */
  --space-6:    1.5rem;    /* 24px */
  --space-8:    2rem;      /* 32px */
  --space-10:   2.5rem;    /* 40px */
  --space-12:   3rem;      /* 48px */
  --space-16:   4rem;      /* 64px */
  --space-20:   5rem;      /* 80px */
  --space-24:   6rem;      /* 96px */
  --space-32:   8rem;      /* 128px */
  --space-40:   10rem;     /* 160px */
  --space-48:   12rem;     /* 192px */
}
```

### 3.2 Espaciado Semántico (Layout)

```css
:root {
  /* Secciones */
  --section-padding-y:      var(--space-20);   /* Padding vertical de sections */
  --section-padding-y-sm:   var(--space-12);   /* Mobile */
  --section-gap:            var(--space-16);   /* Espacio entre sections */

  /* Container */
  --container-max-width:    1280px;
  --container-padding-x:    var(--space-6);    /* Padding horizontal */
  --container-padding-x-sm: var(--space-4);    /* Mobile */

  /* Grid */
  --grid-gap:               var(--space-6);    /* Gap entre columnas */
  --grid-gap-sm:            var(--space-4);    /* Mobile gap */

  /* Cards */
  --card-padding:           var(--space-8);
  --card-padding-sm:        var(--space-6);
  --card-gap:               var(--space-6);

  /* Componentes internos */
  --component-gap-xs:       var(--space-2);
  --component-gap-sm:       var(--space-3);
  --component-gap-md:       var(--space-4);
  --component-gap-lg:       var(--space-6);
  --component-gap-xl:       var(--space-8);
}
```

---

## 4. BORDES Y RADIOS

```css
:root {
  /* Border Radius — Consistente con index.html aprobado */
  --radius-none:     0;
  --radius-sm:       4px;
  --radius-md:       6px;    /* ← Valor canónico del proyecto */
  --radius-lg:       10px;
  --radius-xl:       16px;
  --radius-2xl:      24px;
  --radius-full:     9999px;

  /* Border Width */
  --border-width-thin:    1px;
  --border-width-default: 1px;
  --border-width-thick:   2px;
  --border-width-heavy:   3px;
}
```

---

## 5. SOMBRAS (Box Shadow)

```css
:root {
  /* Sombras — Coherentes con la identidad oscura de la marca */
  --shadow-sm:
    0 1px 3px rgba(0, 36, 107, 0.3),
    0 1px 2px rgba(0, 36, 107, 0.2);

  --shadow-md:
    0 4px 6px rgba(0, 36, 107, 0.25),
    0 2px 4px rgba(0, 36, 107, 0.15);

  --shadow-lg:
    0 10px 25px rgba(0, 36, 107, 0.35),
    0 4px 10px rgba(0, 36, 107, 0.2);

  --shadow-xl:
    0 20px 50px rgba(0, 36, 107, 0.4),
    0 8px 20px rgba(0, 36, 107, 0.25);

  --shadow-card:
    0 4px 20px rgba(0, 36, 107, 0.3);   /* Sombra canónica de cards */

  --shadow-glow:
    0 0 30px rgba(26, 71, 147, 0.4);    /* Efecto glow marca */

  --shadow-inset:
    inset 0 2px 8px rgba(0, 36, 107, 0.3);
}
```

---

## 6. ANIMACIONES Y TRANSICIONES

```css
:root {
  /* Duraciones */
  --duration-instant:   50ms;
  --duration-fast:      150ms;
  --duration-normal:    250ms;
  --duration-slow:      400ms;
  --duration-slower:    600ms;
  --duration-sluggish:  800ms;

  /* Easings */
  --ease-linear:        linear;
  --ease-in:            cubic-bezier(0.4, 0, 1, 1);
  --ease-out:           cubic-bezier(0, 0, 0.2, 1);
  --ease-in-out:        cubic-bezier(0.4, 0, 0.2, 1);
  --ease-bounce:        cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-brand:         cubic-bezier(0.25, 0.46, 0.45, 0.94);

  /* Transiciones canónicas */
  --transition-default: all var(--duration-normal) var(--ease-in-out);
  --transition-colors:  color var(--duration-fast) var(--ease-out),
                        background-color var(--duration-fast) var(--ease-out),
                        border-color var(--duration-fast) var(--ease-out);
  --transition-transform: transform var(--duration-normal) var(--ease-out);
  --transition-opacity: opacity var(--duration-normal) var(--ease-out);
}
```

---

## 7. Z-INDEX

```css
:root {
  --z-below:      -1;
  --z-base:        0;
  --z-raised:     10;
  --z-dropdown:   100;
  --z-sticky:     200;
  --z-fixed:      300;
  --z-overlay:    400;
  --z-modal:      500;
  --z-toast:      600;
  --z-tooltip:    700;
}
```

---

## 8. BREAKPOINTS

```css
/* Breakpoints (usar en @media queries) */
:root {
  --bp-xs:   480px;
  --bp-sm:   640px;
  --bp-md:   768px;
  --bp-lg:   1024px;
  --bp-xl:   1280px;
  --bp-2xl:  1536px;
}

/*
  Uso recomendado:
  @media (max-width: 768px)  { ... }   → Mobile
  @media (min-width: 768px)  { ... }   → Tablet+
  @media (min-width: 1024px) { ... }   → Desktop
  @media (min-width: 1280px) { ... }   → Wide
*/
```

---

## 9. OPACIDADES

```css
:root {
  --opacity-0:      0;
  --opacity-5:      0.05;
  --opacity-10:     0.10;
  --opacity-20:     0.20;
  --opacity-25:     0.25;
  --opacity-40:     0.40;
  --opacity-50:     0.50;
  --opacity-60:     0.60;
  --opacity-75:     0.75;
  --opacity-80:     0.80;
  --opacity-90:     0.90;
  --opacity-100:    1;

  /* Estados */
  --opacity-disabled: 0.4;
  --opacity-hover:    0.85;
}
```

---

## 10. REFERENCIA RÁPIDA — Tokens por Caso de Uso

| Caso de uso                  | Token                          |
|------------------------------|-------------------------------|
| Fondo de página              | `--color-bg-base`             |
| Fondo de card                | `--color-bg-surface`          |
| Texto principal              | `--color-text-primary`        |
| Texto secundario             | `--color-text-secondary`      |
| Botón primario               | `--color-accent`              |
| Hover de botón               | `--color-accent-hover`        |
| Borde default                | `--color-border-default`      |
| Heading hero                 | `--type-hero-*`               |
| Párrafo cuerpo               | `--type-body-*`               |
| Radio canónico de card       | `--radius-md`                 |
| Sombra de card               | `--shadow-card`               |
| Padding de section           | `--section-padding-y`         |
| Gap de grid                  | `--grid-gap`                  |
| Transición estándar          | `--transition-default`        |
| Modal z-index                | `--z-modal`                   |

---

## 11. IMPLEMENTACIÓN — Cómo importar

### En HTML (inline):
```html
<link rel="stylesheet" href="/assets/css/tokens.css">
```

### En CSS global (tokens.css):
```css
/* Importar este archivo como :root block en tokens.css */
/* Luego en cada componente referenciar las variables */

.btn-primary {
  background-color: var(--color-accent);
  color: var(--color-text-primary);
  border-radius: var(--radius-md);
  padding: var(--space-3) var(--space-6);
  font-family: var(--font-ui);
  font-size: var(--type-label-size);
  font-weight: var(--type-label-weight);
  letter-spacing: var(--type-label-tracking);
  transition: var(--transition-colors);
}
```

---

*Design Tokens — Médano / DataTrackers | v1.0 | Marzo 2026*  
*Basado en: Manual de Marca Médano 2024 (wapidesign.com)*
