# ACT05 · Guía de estilo de Nit Oberta (Figma)

Módulo 0615 · Diseño de Interfaces Web. Este README explica qué es cada parte del archivo de Figma y qué contiene.

**Estado:** fase 1 hecha con el plugin (guía + componentes, ~60 %). Falta la fase 2 (plantillas + ficha de origen).

---

## 1. Cómo se genera

1. Descomprimir `act05-figma-plugin.zip`.
2. En Figma Desktop: Menú → Plugins → Development → Import plugin from manifest… y elegir `manifest.json`.
3. Ejecutar: Plugins → Development → ACT05 · Guia d'estil.
4. Ejecutarlo **una sola vez**. Si se repite, borra y recrea los marcos y componentes, y las instancias que ya los usen (plantillas en la fase 2) se romperían.

El plugin no borra nada que no sea suyo: solo los marcos con los nombres que él crea.

---

## 2. Estructura: 3 páginas

| Página | Para qué sirve | Estado |
|---|---|---|
| **Guia** | Los tokens (variables) y las reglas de uso | Hecho (falta la ficha de origen) |
| **Components** | Los 6 componentes con sus estados | Hecho |
| **Plantilles** | La portada y la página de taller | Vacía, es la fase 2 |

---

## 3. Página «Guia»

### Marco `Variables`
Muestra todas las variables de la colección, agrupadas en cuatro secciones.

**Colors** (un recuadro por color, con su nombre y su valor hexadecimal):

| Grupo | Variables |
|---|---|
| Base | `blanc`, `nit`, `xip` |
| Texto | `text`, `text-menu`, `text-suau`, `text-secundari`, `text-invers` |
| Bordes | `vora-suau`, `vora-forta`, `vora-camp` |
| Acentos | `accent-fosc`, `accent-clar`, `preu`, `enllac` |
| Botón | `boto-fons`, `boto-fons-hover` |
| Estados | `focus`, `estat-ok`, `estat-ko`, `desactivat-fons`, `desactivat-text` |

Contraste: los textos pasan 4,5:1 sobre su fondo y los bordes de campo (`vora-camp`) pasan 3:1 sobre blanco. Los estados desactivados están exentos.

**Tipografia** (escala de tamaños, cada fila con un texto de ejemplo):
`mida-xs` 12 · `mida-s` 14 · `mida-m` 16 · `mida-l` 21 · `mida-xl` 32 · `mida-2xl` 42 · `mida-3xl` 60

**Espai** (base de 4 px, 9 valores; en Figma son píxeles, así que `espai-4` vale 16):

| Variable | px | rem |
|---|---|---|
| `espai-1` | 4 | 0,25 |
| `espai-2` | 8 | 0,5 |
| `espai-3` | 12 | 0,75 |
| `espai-4` | 16 | 1 |
| `espai-6` | 24 | 1,5 |
| `espai-8` | 32 | 2 |
| `espai-12` | 48 | 3 |
| `espai-16` | 64 | 4 |
| `espai-24` | 96 | 6 |

Cada barra del marco tiene como ancho la propia variable.

**Radis i vores:**
`radi-s` 8 · `radi-m` 12 · `radi-l` 20 · `radi-pill` 999 · `gruix-vora` 1 · `gruix-focus` 3

### Marco `Regles d'ús`
Tres reglas, cada una con un ejemplo **Correcte** y uno **Incorrecte** (con texto explicativo, no solo color):

1. **Cap valor a mà.** Todo color, tamaño de letra y espacio sale de una variable. El ejemplo incorrecto usa valores escritos a mano a propósito.
2. **Dins petit, entre gran.** El espacio dentro de un grupo es menor que el espacio entre grupos. El ejemplo incorrecto tiene la proximidad invertida.
3. **L'error s'explica amb text.** El focus es visible y un error siempre lleva mensaje. El ejemplo incorrecto es el campo con la vora roja sin texto.

### Pendiente en esta página
Marco `Fitxa d'origen` (fase 2).

---

## 4. Página «Components»

Cada componente está en un marco con su nombre. Todo está vinculado a variables: colores, tamaños de letra, separación, padding, radios y grosor de borde.

| Marco | Componentes que contiene | Qué lleva |
|---|---|---|
| **Botó** | 8 componentes: `Botó / Principal / Normal`, `Hover`, `Focus`, `Desactivat` y los mismos 4 en `Secundari` | Estados uno al lado del otro, con el nombre debajo. En focus lleva un anillo `focus` de `gruix-focus` por fuera |
| **Camp de formulari** | 4 componentes: `Camp de formulari / Normal`, `Focus`, `Error`, `Desactivat` | Etiqueta + caja. El estado Error lleva el mensaje de texto «Falta el domini…» |
| **Targeta** | `Targeta de taller` | Miniatura, nombre, descripción, precio, horas y una **instancia** del botón principal |
| **Pròxims tallers** | `Pròxims tallers` | Título y una fila por taller: nombre, fecha, precio y horas |
| **Capçalera amb menú** | `Capçalera amb menú` | Logo (disco + «Nit·Oberta»), enlaces del menú (Tallers, Calendari, Reserves, Contacte) y una **instancia** del botón |
| **Peu** | `Peu` | Fondo `nit` con tres columnas (Nit Oberta, Tallers, Contacte) y la línea de copyright |

Notas:
- La tarjeta y la cabecera usan **instancias** de `Botó / Principal / Normal`. Si cambias ese botón original, cambia también dentro de ellas (punto 6 de la validación).
- La miniatura de la tarjeta es un rectángulo `nit`. Hay que sustituirlo por la foto del taller (4:3).
- Los estados son componentes independientes (copias modificadas), que es lo que pide la actividad. Hacerlos con variantes de Figma es un extra opcional.

### Contenido de los tres talleres (el mismo en todo el archivo)

| Taller | Descripción | Precio | Horas | Próxima fecha |
|---|---|---|---|---|
| Introducció | Exposició manual, ISO i balanç de blancs quan no hi ha llum de sobres. | 85 € | 4 hores | 12 d'octubre |
| Retrat nocturn | Llum contínua, temperatura de color i com no cremar les altes llums. | 110 € | 4 hores | 26 d'octubre |
| Llarga exposició | Trípode, filtres i rastres de llum: fins a trenta segons per fotografia. | 125 € | 5 hores | 9 de novembre |

---

## 5. Página «Plantilles» (fase 2)

Ahora está vacía. Lleva dos plantillas, hechas **solo con componentes**:

- **Portada:** cabecera con menú, presentación, los tres talleres (tarjetas), próximos talleres, suscripción al correo y pie.
- **Pàgina de taller:** cabecera, foto, nombre, descripción, precio, duración, próxima fecha, plazas, botón de reserva y pie. Es **una sola plantilla** para los tres talleres.

Como las plantillas solo pueden usar componentes, harán falta componentes extra: presentación, suscripción al correo y ficha de datos del taller. Opcionales: ventana de confirmación al pulsar «Reserva», ruta de navegación y logo como componente.

---

## 6. Qué falta para entregar

1. Plantillas (portada y página de taller).
2. Ficha de origen: herramienta, prompt y cambios a mano de cada componente generado con IA, y origen y licencia de cada imagen.
3. Poner las fotos reales (`taller-1.jpg`, `taller-2.jpg`, `taller-3.jpg`).
4. Revisar a mano la validación de clase: focus visible, error con texto, el cambio del botón se propaga, la separación muestra un nombre de variable.
5. Compartir el archivo como «cualquiera con el enlace puede verlo» y entregar el enlace en ClickEdu.
