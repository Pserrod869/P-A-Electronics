# Documentación del Proyecto P&A Electronics

Proyecto web de 4 páginas para el Plan de Sostenibilidad de P&A Electronics.  
**Autores:** Grupo nº 4 — Adrian Burgos y Pablo Serrano

---

## Índice

1. [Estructura de archivos](#estructura-de-archivos)
2. [Estructura HTML común](#estructura-html-común)
3. [index.html — Inicio](#indexhtml--inicio)
4. [grupos.html — Grupos de Interés](#gruposhtml--grupos-de-interés)
5. [asg.html — Aspectos ASG](#asghtml--aspectos-asg)
6. [plan.html — Plan de Acción](#planhtml--plan-de-acción)
7. [CSS — style.css](#css--stylecss)

---

## Estructura de archivos

```
P-A-Electronics/
├── index.html        → Página de inicio / presentación
├── grupos.html       → Grupos de interés (stakeholders)
├── asg.html          → Aspectos Ambientales, Sociales y de Gobernanza
├── plan.html         → Plan de acción e indicadores KPI
├── css/
│   └── style.css     → Hoja de estilos global
└── img/              → Carpeta de imágenes (reservada)
```

---

## Estructura HTML común

Todas las páginas comparten la misma estructura base:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="Grupo nº 4">
    <meta name="description" content="Plan de Sostenibilidad de P&A Electronics">
    <title>...</title>
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/.../font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <header>...</header>
    <main>...</main>
    <footer>...</footer>
</body>
</html>
```

### Etiquetas `<meta>`

| Atributo | Valor | Función |
|---|---|---|
| `charset="UTF-8"` | UTF-8 | Soporte de tildes y caracteres especiales |
| `name="viewport"` | `width=device-width, initial-scale=1.0` | Diseño responsive en móviles |
| `name="author"` | Grupo nº 4 | Metadato de autoría |
| `name="description"` | Texto descriptivo | SEO: descripción de la página |

### Recursos externos (`<link>`)

- **`css/style.css`** — Hoja de estilos propia del proyecto.
- **Font Awesome 6.4.0** (CDN) — Librería de iconos vectoriales usada en toda la web.

### `<header>` — Cabecera / Navegación

```html
<header>
    <div class="nav-container">
        <a href="index.html" class="logo">
            <i class="fa-solid fa-microchip"></i> P&A<span>Electronics</span>
        </a>
        <nav>
            <ul>
                <li><a href="index.html" class="active">Inicio</a></li>
                <li><a href="grupos.html">Grupos de Interés</a></li>
                <li><a href="asg.html">Aspectos ASG</a></li>
                <li><a href="plan.html">Plan de Acción</a></li>
            </ul>
        </nav>
    </div>
</header>
```

- **`<header>`** — Elemento semántico que contiene la navegación global.
- **`.nav-container`** — `div` que centra y limita el ancho de la barra de navegación.
- **`.logo`** — Enlace `<a>` que actúa como logo. Usa el icono `fa-microchip` de Font Awesome. La palabra "Electronics" va dentro de `<span>` para colorearse con el color de acento (verde neón).
- **`<nav>` + `<ul>`** — Lista de navegación semántica. El enlace de la página activa lleva la clase `.active` para el subrayado animado.

### `<footer>` — Pie de página

```html
<footer>
    <div class="footer-content">
        <div class="logo justify-center">
            <i class="fa-solid fa-microchip"></i> P&A<span>Electronics</span>
        </div>
        <p>&copy; 2026 P&A Electronics. Todos los derechos reservados.</p>
        <p class="team-members">Proyecto realizado por Grupo nº 4: Adrian Burgos y Pablo Serrano</p>
    </div>
</footer>
```

- **`&copy;`** — Entidad HTML para el símbolo de copyright ©.
- **`.team-members`** — Párrafo en cursiva con los nombres del equipo.
- El logo se repite para coherencia visual.

---

## index.html — Inicio

Página principal con la presentación de la empresa y sus pilares de sostenibilidad.

### Sección Hero

```html
<section class="hero">
    <div class="hero-content">
        <h1>Innovación <span>Sostenible</span></h1>
        <p>En P&A Electronics, lideramos el diseño...</p>
    </div>
</section>
```

- **`.hero`** — Bloque grande de bienvenida con fondo degradado y efecto de brillo radial (pseudo-elemento `::before`).
- **`.hero-content`** — Contenedor del texto. Tiene `z-index: 2` para situarse por encima del efecto de brillo de fondo.
- **`<h1>`** — Título principal de la página (único `<h1>` por página, buena práctica SEO). La palabra "Sostenible" va en `<span>` para aplicarle el color verde neón.

### Sección "Quiénes Somos"

```html
<section class="about-us">
    <h2 class="section-title">Quiénes Somos</h2>
    <div class="card mb-3 text-center">
        <p class="about-text mx-auto">...</p>
    </div>
```

- **`.section-title`** — `<h2>` con subrayado decorativo creado con `::after`. Centra el texto.
- **`.card`** — Tarjeta con fondo oscuro y borde. Tiene animación `hover` de elevación.
- **`.about-text`** — Párrafo con ancho máximo de 800px, centrado con `mx-auto`.

### Grid de compromisos

```html
<h2 class="section-title">Nuestro Compromiso con la Sostenibilidad</h2>
<div class="grid">
    <div class="card">
        <div class="card-icon"><i class="fa-solid fa-leaf"></i></div>
        <h3>Diseño Eco-Eficiente</h3>
        <p>...</p>
    </div>
    <!-- 2 tarjetas más -->
</div>
```

- **`.grid`** — CSS Grid con columnas automáticas de mínimo 280px. Muestra 3 tarjetas en fila en pantallas grandes.
- **`.card-icon`** — Icono grande (2.5rem) de Font Awesome con color y sombra verde neón.
- Iconos usados: `fa-leaf` (medioambiente), `fa-recycle` (economía circular), `fa-handshake-angle` (ética).

---

## grupos.html — Grupos de Interés

Muestra los cuatro grupos de interés (stakeholders) de la empresa.

### Cabecera de página

```html
<section class="page-header text-center mb-3">
    <h1 class="section-title">Nuestros Grupos de Interés</h1>
    <p class="page-header-text mx-auto">...</p>
</section>
```

- **`.page-header`** — Bloque introductorio usado en las páginas interiores (no en `index.html`).
- **`.page-header-text`** — Párrafo descriptivo con ancho máximo de 700px.

### Grid de stakeholders

```html
<div class="grid grid-wide">
    <div class="card">
        <div class="card-icon"><i class="fa-solid fa-users"></i></div>
        <h3>Clientes</h3>
        <p class="highlight">¿Qué esperan de nosotros?</p>
        <p>...</p>
    </div>
    <!-- 3 tarjetas más -->
</div>
```

- **`.grid-wide`** — Variante del grid con columnas mínimas de 300px (más anchas que las de `index.html`).
- **`.highlight`** — Texto en verde neón para la pregunta clave de cada tarjeta.
- Iconos: `fa-users` (Clientes), `fa-helmet-safety` (Empleados), `fa-truck-fast` (Proveedores), `fa-building-columns` (Administraciones Públicas).

---

## asg.html — Aspectos ASG

Presenta los tres ejes de sostenibilidad: Ambiental, Social y Gobernanza, cada uno con color propio.

### Tarjetas ASG con color diferenciado

```html
<div class="grid">
    <!-- Ambiental -->
    <div class="card card-environmental">
        <div class="card-icon icon-environmental">
            <i class="fa-solid fa-earth-europe"></i>
        </div>
        <h3>Ambiental (A)</h3>
        <ul class="card-list">
            <li class="card-list-item">
                <strong><i class="fa-solid fa-check check-environmental"></i> Gestión de Residuos...</strong>
                <p class="card-list-desc">...</p>
            </li>
        </ul>
    </div>
    <!-- Social y Gobernanza igual -->
</div>
```

#### Sistema de color por pilar

| Clase | Color | Pilar |
|---|---|---|
| `.card-environmental` / `.icon-environmental` / `.check-environmental` | `#00ffaa` (verde) | Ambiental |
| `.card-social` / `.icon-social` / `.check-social` | `#00e5ff` (cian) | Social |
| `.card-governance` / `.icon-governance` / `.check-governance` | `#b388ff` (lila) | Gobernanza |

- **`.card-list`** — Lista `<ul>` sin bullet points (se suprimen con `list-style: none`).
- **`.card-list-item`** — Elemento de lista con margen inferior.
- **`.card-list-desc`** — Descripción en texto muted (grisáceo) con margen superior.
- El borde superior (`border-top`) de cada tarjeta toma el color del pilar correspondiente.

---

## plan.html — Plan de Acción

Página más compleja. Incluye acciones, tabla de KPIs y alineación con los ODS.

### Wrapper del plan

```html
<div class="plan-wrapper mb-3">
    ...
</div>
```

- **`.plan-wrapper`** — Contenedor único con fondo de tarjeta, borde y sombra. Agrupa todo el contenido de la página en un bloque unificado.

### Acciones principales (pasos)

```html
<h2 class="plan-title mb-1-5">
    <i class="fa-solid fa-rocket plan-icon"></i> Acciones Principales
</h2>
<div class="flex-column gap-1-5 mb-3">
    <div class="plan-step">
        <h3 class="plan-step-title">1. Minería Urbana</h3>
        <p class="plan-step-desc">...</p>
    </div>
</div>
```

- **`.plan-step`** — Cada acción tiene un borde izquierdo verde de 4px a modo de línea vertical decorativa.
- **`.plan-step-title`** — Título del paso en color blanco.
- **`.plan-step-desc`** — Descripción en color muted.
- **`.flex-column`** + **`.gap-1-5`** — Clases utilitarias para apilar los pasos verticalmente con separación.

### Tabla de KPIs

```html
<div class="table-wrapper">
    <table>
        <thead>
            <tr>
                <th>Acción Asociada</th>
                <th>Indicador</th>
                <th>Meta Actual</th>
                <th>Frecuencia de Medición</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Minería Urbana</td>
                <td><strong>% de materiales recuperados</strong></td>
                <td>Alcance del 45%...</td>
                <td>Trimestral</td>
            </tr>
        </tbody>
    </table>
</div>
```

- **`<table>`** — Tabla HTML estándar con `<thead>` (encabezados) y `<tbody>` (datos).
- **`.table-wrapper`** — En móviles activa `overflow-x: auto` para hacer la tabla deslizable horizontalmente.
- Las filas pares tienen un fondo ligeramente distinto (`tr:nth-child(even)`).

### Badges ODS

```html
<div class="ods-container">
    <div class="ods-badge">
        <i class="fa-solid fa-industry"></i> ODS 9: Industria e Innovación
    </div>
    <div class="ods-badge">
        <i class="fa-solid fa-recycle"></i> ODS 12: Producción y Consumo Responsables
    </div>
</div>
```

- **`.ods-container`** — Flexbox centrado para los badges.
- **`.ods-badge`** — Pastilla/etiqueta con borde redondeado (20px), borde verde y sombra neón. Usa `inline-flex` para alinear icono y texto.

---

## CSS — style.css

### 1. Fuente e importación

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap');
```

Importa la fuente **Inter** desde Google Fonts en cuatro pesos: 300 (light), 400 (regular), 600 (semibold) y 700 (bold).

---

### 2. Variables CSS (`:root`)

Define el sistema de diseño centralizado. Cambiar una variable actualiza toda la web.

```css
:root {
  --primary-color: #0b1d22;    /* Teal oscuro: header y footer */
  --secondary-color: #13323a;  /* Teal medio: hero y badges */
  --accent-color: #00ffaa;     /* Verde neón: elementos destacados */
  --accent-hover: #00e096;     /* Verde neón oscuro: hover del acento */
  --text-dark: #e0f2f1;        /* Blanco-teal: texto principal */
  --text-muted: #88a7a8;       /* Gris-teal: texto secundario */
  --text-light: #ffffff;       /* Blanco puro */
  --bg-color: #051014;         /* Casi negro: fondo general */
  --card-bg: #0d242a;          /* Oscuro: fondo de tarjetas */
  --border-color: #1a444f;     /* Borde sutil */

  --transition-speed: 0.3s;    /* Velocidad de transiciones */
  --border-radius: 8px;        /* Redondeo estándar */
  --box-shadow: 0 4px 15px rgba(0, 255, 170, 0.05);       /* Sombra sutil */
  --box-shadow-hover: 0 10px 25px rgba(0, 255, 170, 0.2); /* Sombra hover */
}
```

**Paleta:** "Solarpunk / Neon-Tech Green Dark" — oscuro con detalles en verde neón.

---

### 3. Reset global (`*`)

```css
* { margin: 0; padding: 0; box-sizing: border-box; }
```

Elimina márgenes y rellenos por defecto del navegador. `box-sizing: border-box` hace que el padding se incluya dentro del ancho declarado.

---

### 4. `body`

```css
body {
  font-family: 'Inter', sans-serif;
  background-color: var(--bg-color);
  color: var(--text-dark);
  line-height: 1.6;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
```

- `display: flex; flex-direction: column; min-height: 100vh` — Patrón para que el footer siempre quede pegado al fondo aunque el contenido sea corto.
- `line-height: 1.6` — Interlineado cómodo para lectura.

---

### 5. Header y Navegación

```css
header {
  position: sticky;
  top: 0;
  z-index: 1000;
}
```

`position: sticky` hace que la barra de navegación quede fija al hacer scroll.

#### Subrayado animado de los enlaces

```css
nav a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: var(--accent-color);
  transition: width 0.3s ease;
}

nav a:hover::after,
nav a.active::after {
  width: 100%;
}
```

Crea una línea verde de 0px de ancho que se expande al 100% en hover o cuando el enlace es el activo. Técnica de animación CSS pura con pseudo-elemento `::after`.

---

### 6. Contenedor principal

```css
.container {
  max-width: 1200px;
  margin: 2rem auto;
  padding: 0 2rem;
}
```

Limita el ancho del contenido a 1200px y lo centra horizontalmente con `margin: auto`.

---

### 7. Sección Hero

```css
.hero {
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  padding: 6rem 2rem;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: -50%; left: -50%;
  width: 200%; height: 200%;
  background: radial-gradient(circle, rgba(0,255,170,0.15) 0%, transparent 70%);
  z-index: 1;
}

.hero-content { position: relative; z-index: 2; }
```

- `linear-gradient` — Fondo degradado diagonal.
- `::before` — Brillo radial semitransparente centrado. Al ser 200% del tamaño del contenedor y estar desplazado al -50%, el degradado circular queda perfectamente centrado y visible.
- `overflow: hidden` — Recorta el pseudo-elemento que sale fuera del bloque.

---

### 8. Títulos de sección

```css
.section-title::after {
  content: '';
  display: block;
  width: 60px;
  height: 4px;
  background-color: var(--accent-color);
  margin: 0.5rem auto 0;
  border-radius: 2px;
  box-shadow: 0 0 8px rgba(0, 255, 170, 0.5);
}
```

Línea decorativa verde de 60px debajo de los títulos `<h2>` con efecto glow.

---

### 9. Grid de tarjetas

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}
```

`repeat(auto-fit, minmax(280px, 1fr))` — Crea automáticamente tantas columnas como quepan, cada una de al menos 280px. En pantallas pequeñas pasa a una sola columna sin necesidad de media queries.

---

### 10. Tarjetas (`.card`)

```css
.card {
  background-color: var(--card-bg);
  border-radius: 8px;
  padding: 2rem;
  border: 1px solid var(--border-color);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: var(--box-shadow-hover);
  border-color: var(--accent-color);
}
```

Al hacer hover, la tarjeta se eleva 5px (`translateY(-5px)`) y el borde pasa a verde neón. Las `transition` hacen el efecto suave.

---

### 11. Clases utilitarias

Clases de una sola propiedad para usarse directamente en el HTML, similar a una versión mínima de Tailwind:

| Clase | Propiedad CSS |
|---|---|
| `.text-center` | `text-align: center` |
| `.mb-3` | `margin-bottom: 3rem` |
| `.mb-1-5` | `margin-bottom: 1.5rem` |
| `.mx-auto` | `margin-left: auto; margin-right: auto` |
| `.flex-column` | `display: flex; flex-direction: column` |
| `.gap-1-5` | `gap: 1.5rem` |
| `.justify-center` | `justify-content: center` |
| `.text-primary` | `color: var(--accent-color)` |

---

### 12. Tabla

```css
table { width: 100%; border-collapse: collapse; border-radius: 8px; overflow: hidden; }
th { background-color: var(--primary-color); color: var(--accent-color); }
tr:nth-child(even) { background-color: #0c2227; }
tr:hover { background-color: #12333b; }
```

- `border-collapse: collapse` — Elimina el espacio entre celdas.
- `overflow: hidden` + `border-radius` — El redondeo en tablas solo funciona si se oculta el desbordamiento.
- `nth-child(even)` — Filas alternadas con fondo ligeramente distinto para facilitar la lectura.

---

### 13. Diseño Responsive (Media Queries)

#### Tablets y móviles (`max-width: 768px`)

```css
@media (max-width: 768px) {
  .nav-container { flex-direction: column; }
  nav ul { flex-wrap: wrap; justify-content: center; }
  .hero { padding: 3rem 1.5rem; }
  .hero h1 { font-size: 2.2rem; }
  .table-wrapper { overflow-x: auto; }
}
```

- La navegación pasa a apilarse verticalmente.
- El hero reduce su padding y el título de texto.
- La tabla permite scroll horizontal en pantallas pequeñas.

#### Móviles pequeños (`max-width: 480px`)

```css
@media (max-width: 480px) {
  .hero h1 { font-size: 1.8rem; }
  .grid { grid-template-columns: 1fr; }
}
```

En pantallas muy pequeñas, el grid fuerza una sola columna y el título del hero se hace aún más pequeño.

---

## Resumen de clases CSS por página

| Clase | Usado en |
|---|---|
| `.hero`, `.hero-content` | `index.html` |
| `.about-text` | `index.html` |
| `.page-header`, `.page-header-text` | `grupos.html`, `asg.html`, `plan.html` |
| `.grid-wide` | `grupos.html` |
| `.highlight` | `grupos.html` |
| `.card-environmental/social/governance` | `asg.html` |
| `.card-list`, `.card-list-item`, `.card-list-desc` | `asg.html` |
| `.plan-wrapper`, `.plan-step`, `.plan-title` | `plan.html` |
| `.ods-container`, `.ods-badge` | `plan.html` |
| `.table-wrapper` | `plan.html` |
| `.nav-container`, `.logo`, `.team-members` | Todas |
| `.container`, `.grid`, `.card`, `.card-icon` | Todas |
| `.section-title` | Todas |
