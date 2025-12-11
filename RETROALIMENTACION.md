# Retroalimentación - Mini Proyecto 1: Restaurante
## Revisión del avance de Mario Alberto García
**Fecha de revisión:** 10 de diciembre de 2025

---

## Resumen General

Mario, revisé tu avance y veo que ya iniciaste el proyecto. Eso es positivo. Sin embargo, el proyecto actual está **muy lejos** de cumplir con los requisitos establecidos en `mini-proyecto-1-restaurante.md`.

Antes de continuar, necesito que releas el documento de especificación completo y compares lo que pide contra lo que has entregado.

---

## Preguntas de Reflexión

**Antes de leer mis comentarios, responde estas preguntas honestamente:**

1. ¿Leíste completamente el documento `mini-proyecto-1-restaurante.md` antes de empezar?

2. ¿Cuántas de las 7 secciones requeridas tiene tu página actualmente?

3. ¿Dónde está tu archivo `styles.css`?

4. ¿Por qué tu página se ve igual en un celular que en una computadora? ¿Eso está bien?

5. Si un usuario con discapacidad visual usa un lector de pantalla en tu página, ¿qué escucharía cuando llegue a las imágenes?

6. ¿Qué pasa si haces clic en "Ver menú"? ¿Funciona? ¿Por qué no?

7. ¿Cuántos commits tiene tu repositorio? ¿Eso refleja un proceso de desarrollo organizado?

---

## Lo que SÍ hiciste bien

- Creaste el repositorio en GitHub
- Usaste estructura básica de HTML (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`)
- Incluiste contenido real (menú con platillos, precios, descripciones)
- Usaste listas `<ul>` y `<li>` para organizar el menú
- Agregaste imágenes
- Escribiste una pequeña historia del restaurante

---

## Lo que FALTA o está MAL

### 1. Estructura HTML Semántica (Requisito crítico)

**Tu código actual:**
```html
<body>
    <img>
    <h1>
    <hr>
    <img>
    ...todo mezclado...
</body>
```

**Lo que debería ser:**
```html
<body>
    <header>
        <!-- Logo y navegación -->
    </header>
    <main>
        <section id="hero">
            <!-- Sección principal -->
        </section>
        <section id="nosotros">
            <!-- Historia -->
        </section>
        <section id="menu">
            <!-- Menú organizado -->
        </section>
        <!-- ... más secciones -->
    </main>
    <footer>
        <!-- Pie de página -->
    </footer>
</body>
```

**¿Por qué importa?**
- Los motores de búsqueda (Google) entienden mejor tu página
- Los lectores de pantalla pueden navegar por secciones
- El código es más fácil de mantener y estilizar con CSS
- Es el estándar profesional de la industria

---

### 2. NO tienes CSS

El requisito dice claramente:
> "Estilos en archivo separado llamado `styles.css`"

Tu página no tiene **ningún** estilo. Se ve como una página de 1995.

**Preguntas para ti:**
- ¿Cómo vas a hacer que el menú se vea en columnas/tarjetas?
- ¿Cómo vas a poner el logo y la navegación lado a lado?
- ¿Cómo vas a hacer que la galería sea una cuadrícula?
- ¿Cómo vas a hacer que se vea diferente en celular vs computadora?

**La respuesta a todo es: CSS.**

---

### 3. Navegación rota

Tu código:
```html
<form action="pagina4.html" method="get">
    <input type="submit" value="Ver menu">
</form>
```

**Problemas:**
1. `pagina4.html` no existe - el botón no funciona
2. Usar un `<form>` para navegación es incorrecto
3. No tienes menú de navegación real

**Lo que debería ser:**
```html
<nav>
    <ul>
        <li><a href="#hero">Inicio</a></li>
        <li><a href="#nosotros">Nosotros</a></li>
        <li><a href="#menu">Menú</a></li>
        <li><a href="#galeria">Galería</a></li>
        <li><a href="#ubicacion">Ubicación</a></li>
    </ul>
</nav>
```

Y en cada sección:
```html
<section id="menu">
    ...
</section>
```

Así cuando haces clic en "Menú", la página se desplaza a esa sección.

---

### 4. Imágenes sin atributo `alt`

**Tu código:**
```html
<img src="ChatGPT Image 8 dic 2025, 09_09_49 a.m..png" width="500"/>
```

**Problemas:**
1. No tiene `alt` - personas con discapacidad visual no saben qué es
2. El nombre del archivo es terrible (espacios, caracteres especiales, muy largo)
3. Usar `width="500"` en HTML es obsoleto - debe hacerse con CSS

**Lo correcto:**
```html
<img src="images/logo-restaurante.png" alt="Logo del restaurante El Buen Sabor">
```

---

### 5. Estructura de archivos incorrecta

**Tu estructura actual:**
```
Menu-restaurante/
├── index.html
├── ChatGPT Image 8 dic 2025, 09_09_49 a.m..png  (nombre horrible)
├── ChatGPT Image 8 dic 2025, 09_55_24 a.m..png  (nombre horrible)
└── Recetas-Italianas.jpg
```

**Estructura requerida:**
```
Menu-restaurante/
├── index.html
├── styles.css          <-- NO EXISTE
├── images/             <-- NO EXISTE
│   ├── logo.png
│   ├── hero.jpg
│   ├── chef.jpg
│   ├── galeria-1.jpg
│   └── ...
└── README.md           <-- NO EXISTE
```

---

### 6. Falta `<meta charset="UTF-8">`

Por eso caracteres como "ú" o "ñ" podrían verse mal en algunos navegadores.

```html
<head>
    <meta charset="UTF-8">
    <title>El Buen Sabor</title>
</head>
```

---

### 7. Secciones faltantes

| Sección | Requerida | ¿La tienes? |
|---------|-----------|-------------|
| Header con logo y navegación | Sí | NO |
| Hero (imagen grande + slogan + botón) | Sí | Parcial (sin estilo) |
| Nosotros | Sí | Parcial (muy básico) |
| Menú organizado | Sí | Parcial (sin estilo) |
| Galería (CSS Grid) | Sí | NO |
| Ubicación y horarios | Sí | NO |
| Footer | Sí | NO |

---

### 8. Solo 1 commit

Tu historial de Git:
```
6d6bfdc restaurant
```

Esto indica que:
- No estás haciendo commits frecuentes
- No estás documentando tu proceso
- Si algo se rompe, no puedes volver atrás

**Deberías tener mínimo 5-6 commits:**
1. "Crear estructura HTML inicial"
2. "Agregar sección hero y navegación"
3. "Agregar sección menú con platillos"
4. "Crear archivo CSS con estilos base"
5. "Agregar galería con CSS Grid"
6. "Hacer diseño responsive"

---

## Checklist de Requisitos

Marca con ✅ lo que ya tienes, con ❌ lo que falta:

### HTML
- [ ] Estructura semántica: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`
- [ ] Un solo `<h1>`, luego `<h2>` para secciones, `<h3>` para subsecciones
- [ ] Listas `<ul>` y `<li>` para navegación y platillos
- [ ] Todas las imágenes con atributo `alt`
- [ ] Enlaces de navegación con `#id`
- [ ] Meta charset UTF-8

### CSS
- [ ] Archivo `styles.css` separado
- [ ] Flexbox para header y tarjetas del menú
- [ ] CSS Grid para galería
- [ ] 1-2 tipografías de Google Fonts
- [ ] Paleta de colores definida (máximo 4 colores)
- [ ] Diseño responsive (mobile-first)
- [ ] Al menos 1 media query `@media (min-width: 768px)`

### Archivos
- [ ] Carpeta `images/` con imágenes organizadas
- [ ] Nombres de archivos sin espacios ni caracteres especiales
- [ ] `README.md` con descripción del proyecto

### Git
- [ ] Mínimo 5 commits descriptivos
- [ ] Repositorio limpio y organizado

---

## Tarea

1. **Relee** completamente `mini-proyecto-1-restaurante.md`

2. **Revisa** la rama `ejemplo-referencia` que creé en tu repositorio (lee la siguiente sección para aprender cómo hacerlo)

3. **Responde** las preguntas de reflexión al inicio de este documento

4. **Reorganiza** tu proyecto:
   - Crea la carpeta `images/`
   - Renombra tus imágenes con nombres descriptivos
   - Crea el archivo `styles.css`
   - Crea el `README.md`

5. **Reestructura** tu HTML con etiquetas semánticas

6. **Haz commits** frecuentes mientras trabajas

7. **Reporta** tu avance en 2 días

---

## Cómo ver el ejemplo de referencia (Git branches)

Creé una rama llamada `ejemplo-referencia` en tu repositorio con un ejemplo completo de cómo debería verse tu proyecto. Aquí te explico cómo verla y cómo regresar a tu código.

### ¿Qué es una rama (branch)?

Imagina que tu proyecto es un árbol. El tronco principal es la rama `master` (tu código actual). Las ramas son versiones alternativas del código que existen en paralelo sin afectarse entre sí.

```
        ejemplo-referencia  (código de ejemplo)
       /
master ─────────────────── (tu código actual)
```

### Paso 1: Actualiza tu repositorio local

Primero, asegúrate de tener los últimos cambios del repositorio remoto:

```bash
git fetch origin
```

Esto descarga la información de todas las ramas sin modificar tu código actual.

### Paso 2: Ver las ramas disponibles

Para ver todas las ramas (locales y remotas):

```bash
git branch -a
```

Deberías ver algo como:
```
* master
  remotes/origin/ejemplo-referencia
  remotes/origin/master
```

El asterisco (*) indica en qué rama estás actualmente.

### Paso 3: Cambiar a la rama de ejemplo

Para ver el código de ejemplo, cambia a esa rama:

```bash
git checkout ejemplo-referencia
```

Verás un mensaje como:
```
Switched to branch 'ejemplo-referencia'
```

**¡IMPORTANTE!** Ahora los archivos en tu carpeta cambiaron. Si abres `index.html` y `styles.css` verás el código de ejemplo.

### Paso 4: Explora el código de ejemplo

Ahora puedes:
- Abrir `index.html` en VS Code y estudiar la estructura
- Abrir `styles.css` y ver cómo se organizan los estilos
- Abrir `index.html` en el navegador para ver cómo se ve (nota: las imágenes no cargarán porque no están incluidas)
- Leer los comentarios en el código que explican cada sección

**RECUERDA:** Esto es solo para que veas la estructura. NO copies el código. Debes escribirlo tú mismo para aprender.

### Paso 5: Regresar a tu código (rama master)

Cuando termines de revisar el ejemplo, regresa a tu rama:

```bash
git checkout master
```

Verás:
```
Switched to branch 'master'
```

Ahora tus archivos volvieron a ser tu código original. Puedes continuar trabajando en tu proyecto.

### Resumen de comandos

| Acción | Comando |
|--------|---------|
| Descargar cambios remotos | `git fetch origin` |
| Ver todas las ramas | `git branch -a` |
| Ir a la rama de ejemplo | `git checkout ejemplo-referencia` |
| Regresar a tu código | `git checkout master` |
| Ver en qué rama estás | `git branch` |

### Advertencia

- **NO** hagas commits mientras estás en la rama `ejemplo-referencia`
- **NO** copies y pegues el código del ejemplo a tu rama
- **SÍ** estudia la estructura y entiende el "por qué" de cada cosa
- **SÍ** escribe tu propio código basándote en lo que aprendiste

Si te confundes o algo sale mal, escríbeme y te ayudo.

---

## Recursos que debes estudiar

Antes de continuar, dedica tiempo a estos recursos:

1. **HTML Semántico** - https://developer.mozilla.org/es/docs/Glossary/Semantics#sem%C3%A1ntica_en_html

2. **Flexbox Froggy** (juego para aprender Flexbox) - https://flexboxfroggy.com/#es

3. **Grid Garden** (juego para aprender CSS Grid) - https://cssgridgarden.com/#es

4. **Google Fonts** (elige 2 tipografías) - https://fonts.google.com/

5. **Coolors** (genera tu paleta de colores) - https://coolors.co/

---

## Nota Final

Mario, no te desanimes. Todos empezamos así. Pero parte del aprendizaje es recibir retroalimentación honesta y usarla para mejorar.

El proyecto actual muestra que empezaste, pero también muestra que no seguiste las instrucciones del documento de especificación. En el mundo laboral, entregar algo que no cumple con los requisitos significa tener que rehacerlo.

Tómate el tiempo de hacer las cosas bien. Prefiero que tardes más y aprendas, a que entregues rápido sin entender.

**Revisa la rama `ejemplo-referencia` para ver hacia dónde debes llegar.**

---

*Instructor: Horacio Colina*
