# Documentación Técnica - Portafolio Personal

## Estructura de Archivos CSS

### 1. reset.css
```css
/* Reset CSS básico */
*, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Configuraciones base */
html {
    scroll-behavior: smooth;
}

body {
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
}

/* Configuraciones de elementos multimedia */
img, picture, video, canvas, svg {
    display: block;
    max-width: 100%;
}

/* Configuraciones de formularios */
input, button, textarea, select {
    font: inherit;
}

/* Configuraciones de texto */
p, h1, h2, h3, h4, h5, h6 {
    overflow-wrap: break-word;
}
```

### 2. styles.css
```css
/* Variables globales */
:root {
    --bg-color: #0F1624;
    --text-color: #FFFFFF;
    --accent-color: #854CE6;
    --secondary-color: #ABB2BF;
    --container-width: 1200px;
    --spacing-unit: 1rem;
}

/* Estilos base */
body {
    font-family: 'Poppins', sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
}

/* Layout principal */
.main-container {
    display: grid;
    grid-template-columns: 1fr 300px;
    gap: calc(var(--spacing-unit) * 2);
    max-width: var(--container-width);
    margin: 80px auto 0;
    padding: var(--spacing-unit);
}

/* Componentes */
.header-logo {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.nav-list {
    display: flex;
    gap: 2rem;
    list-style: none;
}

/* ... más estilos ... */
```

### 3. responsive.css
```css
/* Media Queries */
@media screen and (max-width: 768px) {
    .main-container {
        grid-template-columns: 1fr;
    }

    .nav-list {
        flex-direction: column;
    }

    /* ... más estilos responsivos ... */
}
```

## Estructura JavaScript

### main.js
```javascript
// Navegación suave
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
    });
});

// Menú móvil
document.addEventListener('DOMContentLoaded', () => {
    const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
    const mainNav = document.querySelector('.main-nav');
    
    mobileMenuBtn.addEventListener('click', () => {
        mobileMenuBtn.classList.toggle('active');
        mainNav.classList.toggle('show');
    });
});

// ... más funcionalidades ...
```

## Guía de Componentes

### 1. Header
- Clase: `.main-header`
- Responsabilidades:
  * Contiene el logo y nombre
  * Navegación principal
  * Botón de menú móvil
- Comportamiento:
  * Fijo en la parte superior
  * Cambia de opacidad al hacer scroll
  * Se convierte en menú hamburguesa en móvil

### 2. Navegación
- Clase: `.main-nav`
- Elementos:
  * Lista de enlaces
  * Indicadores de sección
  * Estados activos
- Comportamiento:
  * Enlaces suaves
  * Indicador de sección actual
  * Menú desplegable en móvil

### 3. Secciones de Contenido
- Estructura:
  * Grid de dos columnas en desktop
  * Una columna en móvil
  * Espaciado consistente
- Componentes:
  * Tarjetas de proyecto
  * Grillas de habilidades
  * Formulario de contacto

## Guía de Estilos

### Colores
```css
:root {
    --bg-color: #0F1624;      /* Fondo principal */
    --text-color: #FFFFFF;    /* Texto principal */
    --accent-color: #854CE6;  /* Color de acento */
    --secondary-color: #ABB2BF; /* Texto secundario */
}
```

### Tipografía
```css
/* Fuentes */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');

/* Tamaños */
h1 { font-size: 2.5rem; }
h2 { font-size: 2rem; }
h3 { font-size: 1.5rem; }
p { font-size: 1rem; }
```

### Espaciado
```css
:root {
    --spacing-unit: 1rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1.5rem;
    --spacing-lg: 2rem;
}
```

## Guía de Responsive Design

### Breakpoints
```css
/* Desktop: > 768px */
/* Tablet: 768px */
/* Móvil: < 768px */
```

### Adaptaciones
1. **Desktop**
   - Layout de dos columnas
   - Navegación horizontal
   - Tamaños de fuente completos

2. **Tablet**
   - Layout de una columna
   - Navegación adaptada
   - Espaciado reducido

3. **Móvil**
   - Menú hamburguesa
   - Contenido optimizado
   - Fuentes ajustadas

## Mejores Prácticas Implementadas

1. **Semántica HTML**
   - Uso de etiquetas semánticas
   - Estructura clara y organizada
   - Atributos ARIA para accesibilidad

2. **CSS**
   - Variables CSS para consistencia
   - BEM para nomenclatura
   - Media queries organizadas

3. **JavaScript**
   - Código modular
   - Eventos delegados
   - Manejo de estados

4. **Rendimiento**
   - Imágenes optimizadas
   - CSS minificado
   - JavaScript deferido

## Solución de Problemas Comunes

1. **Menú Móvil**
   - Verificar z-index
   - Comprobar eventos JavaScript
   - Revisar media queries

2. **Layout**
   - Comprobar Grid/Flexbox
   - Verificar breakpoints
   - Revisar contenedores

3. **Animaciones**
   - Verificar transiciones
   - Comprobar keyframes
   - Revisar estados

## Mantenimiento

1. **Actualización de Contenido**
   - Modificar HTML directamente
   - Mantener estructura semántica
   - Actualizar imágenes en assets/img

2. **Modificación de Estilos**
   - Usar variables CSS
   - Seguir estructura de archivos
   - Mantener consistencia

3. **Agregar Funcionalidades**
   - Seguir estructura JavaScript
   - Mantener modularidad
   - Documentar cambios 