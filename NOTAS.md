# Notas de trabajo — NTY

Registro vivo de la sesión. Se actualiza cada vez que cerramos un cambio. Al empezar una sesión nueva, léelo primero (y [CLAUDE.md](CLAUDE.md) para el contexto general).

## Enlaces importantes

- Repo: https://github.com/ntytravel/ntytravel
- Web (GitHub Pages — confirmado, es la URL activa): https://ntytravel.github.io/ntytravel/
- Dominio propio: https://ntytravel.com (comprado en Namecheap)
- Instagram / TikTok: [@ntytravel](https://www.instagram.com/ntytravel)
- Copia local del repo: `Desktop\GENÍS\ntytravel` (clonada por Claude el 2026-09-16)

## Decisiones tomadas

- (2026-09-16) El repo se clonó localmente en `Desktop\GENÍS\ntytravel` a petición del usuario.
- (2026-09-16) `CLAUDE.md` prioriza lo verificado en el código sobre el briefing original cuando hay contradicción.
- (2026-09-16) Confirmado con el usuario: hosting activo = GitHub Pages. La referencia a "Netlify" en el historial de commits es de antes de migrar y no aplica — descartada de la documentación.
- (2026-09-16) Confirmado con el usuario: el estilo real (acento `#c8b89a`, Playfair Display + DM Sans) es el correcto; lo que decía el briefing de memoria (otro acento, otras fuentes, `style.css`) queda descartado.
- (2026-09-16) Confirmado con el usuario: Vietnam y Tailandia ya están publicados; Colombia es el siguiente destino previsto (no Corea o China, que dependen de viajes futuros).

## Pendiente de confirmar con el usuario

_(nada pendiente por ahora)_

## Registro de cambios por destino

Formato sugerido por entrada:

```
### YYYY-MM-DD — [Destino o General]
- Qué se hizo
- Por qué / contexto si es relevante
- Commit(s): <hash o mensaje>
```

### 2026-09-16 — General
- Se elimina `bali.html.webloc` de la raíz del repo (acceso directo de macOS, no formaba parte de la web).
- Commit: `1b5f1e6`

### 2026-09-16 — Bali
- Exchange: la "regla de oro" ahora menciona que hay un vídeo con la experiencia real, con enlaces a Instagram y TikTok (antes solo aparecía el @ sin contexto).
- Visado, opción B: la referencia a la web oficial (`evisa.imigrasi.go.id`) ahora es un link directo.
- Transporte: la sección "Moto" deja de ser una categoría independiente en el menú y pasa a ser una tarjeta dentro de "Transporte". Se elimina también un tip redundante sobre regatear en alquileres largos (ya se mencionaba al principio de esa sección).
- Lockers: se reescribió y luego se eliminó el bloque final "Cómo funciona" (la información ya estaba explicada arriba, era redundante).
- SIM/eSIM: las dos tarjetas (SIM física + eSIM) se fusionaron en una sola, más corta. Se quitaron Holafly y Jetpac; se mantienen Airalo y Roamic como eSIM recomendadas junto al aviso de revisar el roaming del banco.
- Agua: se quitó la frase genérica sobre que el agua es barata, el consejo del garrafón de 19L, y los precios orientativos de botella (se conserva la mención suelta a comprarla en Indomaret/Alfamart).
- Comida: la sección "Platos típicos de Bali" se fusionó como tarjeta dentro de "Comida" y se eliminó como categoría separada (no estaba en el menú de navegación, así que no rompe enlaces). Se quitó el tip "Dónde comer auténtico y barato" por duplicar precios de warung ya mencionados en la primera tarjeta de Comida.
- Commit: `93d5c40` (contenido) + `c767557` (registro en NOTAS.md)
- Estado: subido a GitHub (`origin/main`).

### 2026-09-17 — Bali (Bloque 3, cambio 1/2: desplegable "Lugares")
- Diagnóstico: los 8 enlaces del desplegable "📍 Lugares ▾" llamaban todos a `goToSection('lugares')` — idéntico para los 8, sin distinguir destino. Como la sección `id="lugares"` es "Zonas de Bali", en la práctica ya aterrizaban ahí, pero siempre al principio de la sección (tarjeta de Canggu), nunca en la tarjeta del lugar concreto que se clicaba, porque ninguna tarjeta tenía `id` propio. Bug secundario encontrado: el resaltado del menú (scroll-spy vía `IntersectionObserver`) nunca marcaba "Lugares" como activo al hacer scroll hasta esa sección, por una comparación case-sensitive (`toggleLugares` con L mayúscula vs id `lugares` en minúscula).
- Aplicado (opción B, confirmada por el usuario): cada una de las 9 tarjetas de "Zonas de Bali" tiene ahora su propio `id` (`zona-canggu`, `zona-seminyak`, `zona-kuta`, `zona-uluwatu`, `zona-nusadua`, `zona-sanur`, `zona-ubud`, `zona-sidemen`, `zona-amed`). El desplegable se actualizó para que cada lugar enlace a su propia tarjeta. "Nusa Dua · Sanur" se separó en dos entradas independientes (antes era una sola entrada para dos tarjetas distintas).
- Bug del scroll-spy arreglado: la comparación ahora se hace en minúsculas por ambos lados.
- Pendiente (Bloque 3, cambio 2/2): añadir tarjetas de Jimbaran y Nusa Penida a "Zonas de Bali", marcadas como información no verificada (mismo criterio que MyBlueBird en Lombok) — texto propuesto, pendiente de aprobación del usuario antes de aplicar.
- Estado: subido a GitHub (`origin/main`).

### 2026-09-16 — Lombok
- Ferry: se borró la frase final redundante que remitía a la sección Transporte.
- Transporte: la recomendación principal pasa a ser el taxi privado gestionado por el alojamiento (guesthouse/homestay). MyBlueBird se mantiene como nota aparte, marcada explícitamente como información general no probada por el usuario, con sus limitaciones (aeropuerto, sin servicio en Kuta Lombok).
- Lugares: se eliminó la sección "Playas de Kuta" (y su botón/entrada de menú). En la tabla de "Zonas principales" se quitaron las filas de playas (Tanjung Aan, Selong Belanak), quedando solo Mataram y Senggigi. La sección de Islas Gili no se tocó.
- Comida: se eliminó la sección "Comida: warungs recomendados en Kuta" (y su botón de menú). Se limpió una referencia colgante a esa sección desde "Platos típicos".
- Efecto en otras páginas: `bali.html`, `index.html` y `sulawesi.html` tenían en su menú "Lombok" un enlace a `lombok.html#playas` ("Kuta Lombok"); se actualizó a `lombok.html#gili` y se renombró la etiqueta a "Islas Gili" para que no confunda.
- Commit: `b7a96c7` (contenido) + `746d4e2` (registro en NOTAS.md)
- Estado: subido a GitHub (`origin/main`).

### 2026-09-16 — Sulawesi
- "Consejo clave antes de empezar" (banner del hero): se recortó, quitando la frase final sobre buscar en Google Maps y gestionar barcos/motos/traslados desde el alojamiento.
- Sección "Por qué ir", primera tarjeta: se quitó "Y no hablamos de Bali." del título.
- CTA de guía (misma tarjeta): reescrito para dejar claro que ofrecemos guías personalizadas de Sulawesi y que se consiguen escribiendo por Instagram o TikTok (@ntytravel), en vez del texto anterior de "guía completa en preparación".
- Commit: `852554e` (incluye también el registro en NOTAS.md).
- Estado: subido a GitHub (`origin/main`).

### 2026-09-17 — Sulawesi
- Menú de categorías: se movió "💵 Dinero" a la primera posición de contenido (justo después de "🗺️ Zonas ▾"), antes ocupada por "🌊 Por qué ir". Es ahora la pestaña activa por defecto. Solo se reordenaron los botones del menú, el contenido no se tocó.
- Estado: subido a GitHub (`origin/main`).

### 2026-09-16 — Vietnam
- Hero: subtítulo y descripción reescritos, quitando las menciones a "9 días", "reto de presupuesto" y "sleep bus" como gancho (nuevo: "Vietnam · De norte a sur" / "Hanói, Ninh Binh, Phong Nha, Hội An, Ho Chi Minh. La ruta real que hicimos, con los tips prácticos que aprendimos por el camino.").
- Sección "La ruta que hicimos", primera tarjeta: se quitó "El objetivo: llegar de Hanói a Hội An en 9 días" del párrafo inicial (se mantiene la mención a sleep bus/moto/Grab y el resto de la frase). La "Nota NTY" de esa misma tarjeta se reescribió quitando la mención al reto de presupuesto diario (5€–35€) y al vídeo de YouTube — ese vídeo todavía no existe (saldrá en unos meses) — dejando solo la idea de que ahí abajo están los tips prácticos.
- La sección "Sleep bus" (info práctica de cómo funciona) no se tocó — es contenido aparte del framing del hero.
- Pendiente, no tocado hoy: un tercer punto sobre los nombres de las compañías de eSIM en la sección SIM — queda para otra sesión.
- Commit: `4099241` (contenido) + `0caebc8` (registro en NOTAS.md)
- Estado: subido a GitHub (`origin/main`).

### 2026-09-17 — Vietnam
- Menú de categorías: "💳 ATM" se movió a la segunda posición (justo después de "📍 Lugares ▾"), antes estaba en la posición 5 entre "Sleep bus" y "Transporte".
- Se eliminó la categoría "⚠️ Alertas" por completo: botón del menú y la sección `id="estafas"` entera (taxis sin taxímetro, precios de turista, xích lô, etc.).
- Se fusionaron "Comida" y "Platos típicos" (esta última no tenía botón propio en el menú) en una sola sección `id="comida"`, título "Comida y platos típicos". La tabla de 10 platos se recortó a los 5 que aparecían en ambas secciones originales (criterio: intersección de las dos listas) — Phở, Bánh Mì, Cơm Tấm, Cao Lầu, Bún Bò Huế. El tip-pro sobre tiendas de conveniencia (Circle K, GS25, FamilyMart) se eliminó — no encajaba ni en Comida ni en Compras, así que se descartó a petición del usuario.
- Contador del hero actualizado: "10 Categorías" → "11 Categorías" (recuento real de botones del menú, sin contar "📍 Lugares").
- Pendiente sin tocar: nombres de compañías de eSIM en la sección SIM (sigue igual desde el 2026-09-16).
- Estado: subido a GitHub (`origin/main`).

### 2026-09-16 — General (sitio completo: index + 5 destinos)
7 cambios estructurales/visuales aplicados a todas las páginas:
1. **Menú de navegación**: Bali/Lombok/Sulawesi se agruparon bajo un único desplegable "Indonesia ▾" (antes 3 entradas sueltas). Vietnam y Tailandia siguen como entradas propias. Los enlaces rápidos a sitios concretos (Canggu, Uluwatu, Gili Trawangan...) se quitaron de este menú global — siguen disponibles dentro de cada página en su propio menú "📍 Lugares".
2. **Menú de categorías fijo en móvil**: ya estaba en `position:sticky` en el CSS, pero desaparecía al hacer scroll en móvil (bug reproducido también en el sitio real publicado). Causa encontrada: tablas anchas (`.tip-table`) desbordaban el ancho de pantalla, y combinado con `overflow-x:hidden` en `body`, es el bug conocido de iOS Safari que rompe `position:fixed`/`sticky`. Fix: `.tip-table` pasa a `display:block; overflow-x:auto` en móvil, y se añadió `position:relative` a `body` en las 6 páginas.
3. **Footer**: año actualizado de 2025 a 2026 en `index.html` (las páginas de destino no mostraban año).
4. **Home**: se eliminó la sección "Comparte tu experiencia" (formulario) de `index.html`, incluyendo su CSS muerto asociado. El botón del hero que enlazaba ahí ahora apunta a la sección "Síguenos".
5. **Aviso de vigencia**: se añadió una línea en el footer de las 6 páginas: "Contenido basado en un viaje de la primera mitad de 2026 — algunos datos (precios, visados, apps) pueden haber cambiado."
6. **Caja crema**: la sección "¿Has estado en [destino]?" (comparte tu experiencia) de las 5 páginas de destino ahora va dentro de una tarjeta con fondo crema `#f5f3ef` (el mismo tono ya usado como color de texto de marca) y texto oscuro, para que destaque del resto de la página oscura.
7. **Breadcrumb**: se añadió "Inicio" delante de "Destinos" en las 5 páginas de destino (`Inicio / Destinos / Indonesia / Bali`, etc.).
- Verificado visualmente en local (desktop y móvil) y contrastado contra el sitio real publicado para el bug del punto 2.
- Nota: durante la verificación se investigó una aparente altura de página rota (~100.000px) en `thailand.html`, tanto en local como en producción — resultó ser un artefacto del panel de pruebas (viewport a 0px mientras estaba oculto), no un bug real. Descartado.
- Commit: `d718196` (contenido) + `0119197` (registro en NOTAS.md)
- Estado: subido a GitHub (`origin/main`).

### 2026-09-17 — Lombok
- Menú de categorías: se movió "💳 ATM / Dinero" a la primera posición (justo después de "📍 Lugares"), antes ocupada por "🚢 Cómo llegar". Es ahora la pestaña activa por defecto, igual que en `bali.html`. El orden del contenido en el documento no se tocó — solo el orden de los botones del menú.
- Nueva categoría "📶 SIM / eSIM": mismo contenido y formato que la tarjeta de `bali.html` (SIM física Telkomsel + eSIM Airalo/Roamic + aviso de roaming del banco), solo cambia el título a "SIM y eSIM en Lombok". Colocada en el documento justo después de la sección ATM (a petición del usuario: son las dos cosas que se resuelven nada más llegar).
- Contador del hero actualizado: "6 Categorías" → "8 Categorías" (recuento real de botones del menú de categorías, sin contar "📍 Lugares"). El "12 Tips" no cambia — al recontar tarjetas `.tip-card` dentro de esas 8 secciones (llegar, transporte, moto, atm, sim, laundry, agua, salud) el total ya era 12, así que se queda igual.
- Estado: subido a GitHub (`origin/main`).

## Pendiente para cuando toquemos Sulawesi

- `sulawesi.html` tiene un desajuste de 1 `<div>` sin cerrar (295 aperturas / 294 cierres). Detectado el 2026-09-16 al revisar el archivo por un cambio no relacionado (enlace del menú de Lombok). No se ha tocado — revisar y arreglar cuando trabajemos el bloque de Sulawesi.
- El CTA de guía personalizada en la sección "Por qué ir" (reescrito el 2026-09-16) habrá que volver a revisarlo cuando se haga el cambio estructural de alojar el PDF directamente en la web (en vez de entregarlo por DM). Ese cambio estructural **todavía no se ha hecho** — solo el texto del CTA se actualizó para reflejar el proceso actual (contacto por redes).

## Pendiente para cuando toquemos Vietnam

- Revisar los nombres de las compañías de eSIM en la sección SIM (punto que el usuario dejó explícitamente pendiente el 2026-09-16, sin más detalle todavía).

## Estado general al retomar (2026-09-16)

- Último commit en el repo: 2026-06-10 ("index: smooth bezier silhouettes for Bali and Lombok").
- Destinos publicados en la home: Bali, Lombok, Sulawesi, Vietnam, Tailandia.
- Destinos como "Próximamente" en la home: Colombia, Corea del Sur, China.
- Sin trabajo de código todavía en esta sesión — solo se ha clonado el repo, instalado Git en la máquina, y creado `CLAUDE.md`/`NOTAS.md`.
