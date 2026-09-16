# NTY — Nobody Tells You

Contexto de proyecto para trabajar en este repo. Basado en el briefing del usuario (junio 2026), verificado y corregido directamente contra el código — donde ambos diferían, gana el código.

Al empezar una sesión nueva: lee también [NOTAS.md](NOTAS.md) para ver en qué punto se quedó el trabajo.

## Qué es NTY

- Nombre completo: Nobody Tells You. Handle: `@ntytravel` (Instagram y TikTok).
- Concepto: marca de contenido de viajes en español, consejos prácticos y honestos para mochileros/viajeros independientes de habla hispana.
- Gancho de vídeos/artículos: "Nadie te dice que…". Cierre: "Esto es lo que nadie te dice antes de llegar."
- Tono: directo, honesto, sin filtros turísticos. Sin hashtags en Instagram (keywords integradas de forma natural).

## Identidad visual

- Fondo: `#0a0a0a` (negro). Texto: `#f5f3ef`. Gris secundario: `#888`. **Acento: `#c8b89a`** (dorado apagado).
- Tipografías: **Playfair Display** (títulos/logo/serif) + **DM Sans** (cuerpo, light 300).
- Estilo: dark, minimalista, elegante — tarjetas con bordes finos (0.5px), mucho espacio negativo, animación de "libro 3D" en el hero de `index.html`.
- Estos son los valores correctos y confirmados por el usuario. (El briefing original citaba de memoria otro acento y otras tipografías — Poppins/Bebas Neue/Crimson Pro/Space Mono — y un `style.css` separado que nunca existió; descartado.)

## El repo y cómo se publica

- Repo: [github.com/ntytravel/ntytravel](https://github.com/ntytravel/ntytravel), rama `main`.
- Sitio estático puro: **no hay build system, ni `package.json`, ni `style.css`** — cada página HTML lleva su CSS inline en un `<style>` dentro del `<head>`.
- Hosting: **GitHub Pages** (`https://ntytravel.github.io/ntytravel/`), confirmado por el usuario — es la URL activa. Dominio propio `ntytravel.com` comprado en Namecheap. (Un commit antiguo mencionaba "Netlify": era una referencia de antes de migrar y ya no aplica.)
- Workflow: editar los `.html` directamente → commit → push a `origin/main` → se publica solo (sea cual sea el hosting activo).

## Estructura de archivos actual

```
ntytravel/
├── index.html              ← home, grid de destinos, animación libro
├── bali.html
├── lombok.html
├── sulawesi.html
├── vietnam.html
├── thailand.html
├── bali.html.webloc        ← acceso directo macOS, probablemente prescindible
└── *.jpg                   ← fotos usadas en las páginas de destino
```

No hay `style.css` ni carpeta `assets/` — todo vive en la raíz.

## Estado de los destinos

| Destino | Estado en la web |
|---|---|
| Bali 🇮🇩 | ✅ Publicado |
| Lombok 🇮🇩 | ✅ Publicado |
| Sulawesi 🇮🇩 | ✅ Publicado |
| Vietnam 🇻🇳 | ✅ Publicado |
| Tailandia 🇹🇭 | ✅ Publicado |
| Colombia 🇨🇴 | 🔒 "Próximamente" (siguiente destino previsto) |
| Corea del Sur 🇰🇷 | 🔒 "Próximamente" |
| China 🇨🇳 | 🔒 "Próximamente" |

Esta tabla es la correcta y confirmada por el usuario (Vietnam y Tailandia ya están publicados, Colombia es el siguiente destino en el grid). El briefing original los daba como "en proceso"/"pendiente" y no mencionaba Colombia — descartado.

- Destinos sin página propia (solo contenido personal, no en la web): Corea del Sur (viaje jun 2026) y China (Shanghai, Zhangjiajie, Chengdu, Xi'an, Pekín — viaje jun-jul 2026) están pendientes de crear tras esos viajes.
- Decisión de diseño: páginas separadas por destino (no agrupadas por país) hasta tener 8-10+ destinos; cada card de la home lleva bandera + nombre; SEO favorece páginas individuales por destino.

## Negocio: guías PDF personalizadas

- Guía gratuita Sulawesi en Google Drive (`NTY_Sulawesi_Guia_v5.pdf` y posteriores).
- Guías personalizadas de pago: 15€ al empezar, subido a 25-30€. CTA: DM en Instagram/TikTok con la palabra clave del destino (ej. "SULAWESI").
- Estilo PDF: fondo negro, acentos dorados, fuente Poppins, generadas con Python + ReportLab, sin fotos (no quedaban bien). Precios en rupias con equivalente en euros (1€ ≈ 20.000 IDR). Contactos locales (WhatsApp) se comparten aparte por privacidad, no en el PDF.
- Proceso: DM con palabra clave → se recoge info (fechas, puntos de partida, preferencias) → PDF con ReportLab → se envía por DM.

## Redes sociales

- Instagram y TikTok: `@ntytravel`. Publicación a las 19:00 hora España.
- Formato: Reels/TikTok cortos (~30s) con gancho "Nadie te dice que…" → desarrollo → cierre con línea de marca.
- Portadas de vídeo: fondo oscuro, texto blanco/dorado bold, foto a la derecha si aplica, generadas con Python/Pillow.

## Herramientas del proyecto

| Herramienta | Para qué |
|---|---|
| Claude (chat) | Scripting, estrategia, contenido, generación de PDFs |
| Claude Code / Cowork | Desarrollo de la web (edita los HTML localmente) |
| GitHub | Repo + control de versiones |
| GitHub Desktop | Subir cambios (alternativa a la web de GitHub) |
| Google Drive | PDFs, horarios, plantillas |
| CapCut | Edición de vídeo |
| Namecheap | Dominio `ntytravel.com` |
| ReportLab (Python) | Generación de PDFs |
| Pillow (Python) | Portadas de vídeo |

## Trabajando aquí con Claude

- Repo público → se puede leer y editar el código directamente, sin necesidad de que el usuario pegue HTML.
- Ante cualquier duda sobre el estado real de una página o el estilo, prioriza lo que dice el código sobre cualquier descripción de memoria.
- Actualiza [NOTAS.md](NOTAS.md) al cerrar cada cambio importante.
