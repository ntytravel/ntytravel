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
- Commit: `93d5c40`
- Estado: commiteado en local, **pendiente de push a GitHub**.

## Estado general al retomar (2026-09-16)

- Último commit en el repo: 2026-06-10 ("index: smooth bezier silhouettes for Bali and Lombok").
- Destinos publicados en la home: Bali, Lombok, Sulawesi, Vietnam, Tailandia.
- Destinos como "Próximamente" en la home: Colombia, Corea del Sur, China.
- Sin trabajo de código todavía en esta sesión — solo se ha clonado el repo, instalado Git en la máquina, y creado `CLAUDE.md`/`NOTAS.md`.
