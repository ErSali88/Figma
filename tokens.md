# ACT07 · La meva guia a Tailwind — Nit Oberta

Font: documentació oficial de Tailwind, pàgina *Theme variables* (tailwindcss.com/docs/theme), apartat *Theme variable namespaces*.

## Taula de tokens

### Colors (prefix `--color-*` → `bg-`, `text-`, `border-`, `outline-`…)

| Variable a Figma | Token a `@theme` | Classe que genera |
|---|---|---|
| blanc | `--color-blanc` | `bg-blanc` |
| nit | `--color-nit` | `bg-nit` |
| xip | `--color-xip` | `bg-xip` |
| text | `--color-text` | `text-text` |
| text-menu | `--color-text-menu` | `text-text-menu` |
| text-suau | `--color-text-suau` | `text-text-suau` |
| text-secundari | `--color-text-secundari` | `text-text-secundari` |
| text-invers | `--color-text-invers` | `text-text-invers` |
| vora-suau | `--color-vora-suau` | `border-vora-suau` |
| vora-forta | `--color-vora-forta` | `border-vora-forta` |
| vora-camp | `--color-vora-camp` | `border-vora-camp` |
| accent-fosc | `--color-accent-fosc` | `text-accent-fosc` |
| accent-clar | `--color-accent-clar` | `outline-accent-clar` |
| preu | `--color-preu` | `text-preu` |
| enllac | `--color-enllac` | `text-enllac` |
| boto-fons | `--color-boto-fons` | `bg-boto-fons` |
| boto-fons-hover | `--color-boto-fons-hover` | `hover:bg-boto-fons-hover` |
| focus | `--color-focus` | `outline-focus` |
| estat-ok | `--color-estat-ok` | `text-estat-ok` |
| estat-ko | `--color-estat-ko` | `text-estat-ko` |
| desactivat-fons | `--color-desactivat-fons` | `bg-desactivat-fons` |
| desactivat-text | `--color-desactivat-text` | `text-desactivat-text` |
| color-vel | `--color-vel` | `bg-vel` |

### Tipografia

| Variable a Figma | Token a `@theme` | Prefix | Classe que genera |
|---|---|---|---|
| família DM Sans | `--font-text` | `--font-*` | `font-text` |
| mida-xs (12 px) | `--text-mida-xs` | `--text-*` | `text-mida-xs` |
| mida-s (14 px) | `--text-mida-s` | `--text-*` | `text-mida-s` |
| mida-m (16 px) | `--text-mida-m` | `--text-*` | `text-mida-m` |
| mida-l (20 px) | `--text-mida-l` | `--text-*` | `text-mida-l` |
| mida-xl (28 px) | `--text-mida-xl` | `--text-*` | `text-mida-xl` |
| mida-3xl (48 px) | `--text-mida-3xl` | `--text-*` | `text-mida-3xl` |
| pes Regular | `--font-weight-regular` | `--font-weight-*` | `font-regular` |
| pes Medium | `--font-weight-medium` | `--font-weight-*` | `font-medium` |
| pes Bold | `--font-weight-bold` | `--font-weight-*` | `font-bold` |
| pes ExtraBold | `--font-weight-extrabold` | `--font-weight-*` | `font-extrabold` |
| interlineat de títols | `--leading-titol` | `--leading-*` | `leading-titol` |
| interlineat de text | `--leading-text` | `--leading-*` | `leading-text` |

### Espais (prefix `--spacing`, unitat base de 4 px)

| Variable a Figma | Valor | Token a `@theme` | Classe que genera |
|---|---|---|---|
| espai-1 | 4 px | `--spacing` × 1 | `p-1`, `gap-1` |
| espai-2 | 8 px | `--spacing` × 2 | `p-2`, `gap-2`, `mt-2` |
| espai-3 | 12 px | `--spacing` × 3 | `p-3`, `gap-3` |
| espai-4 | 16 px | `--spacing` × 4 | `px-4`, `gap-4`, `mt-4` |
| espai-6 | 24 px | `--spacing` × 6 | `px-6`, `gap-6`, `mt-6` |
| espai-8 | 32 px | `--spacing` × 8 | `px-8`, `gap-8`, `mt-8` |
| espai-12 | 48 px | `--spacing` × 12 | `py-12`, `gap-12` |
| espai-16 | 64 px | `--spacing` × 16 | `py-16`, `px-16` |
| espai-24 | 96 px | `--spacing` × 24 | `py-24`, `gap-24` |

### Cantonades, ombra, amples i gruixos

| Variable a Figma | Token a `@theme` | Prefix | Classe que genera |
|---|---|---|---|
| radi-s (6 px) | `--radius-radi-s` | `--radius-*` | `rounded-radi-s` |
| radi-m (12 px) | `--radius-radi-m` | `--radius-*` | `rounded-radi-m` |
| radi-l (20 px) | `--radius-radi-l` | `--radius-*` | `rounded-radi-l` |
| ombra suau (vora-suau) | `--shadow-suau` | `--shadow-*` | `shadow-suau` |
| amplada de lectura | `--container-lectura` | `--container-*` | `max-w-lectura` |
| amplada de pàgina | `--container-pagina` | `--container-*` | `max-w-pagina` |
| gruix-vora (1 px) | `--gruix-vora` | cap (Tailwind no té namespace per a gruixos) | `border` (1 px) |
| gruix-focus (2 px) | `--gruix-focus` | cap | `outline-2` (2 px) |

## Preguntas

### ¿Que hace --color-*: initial y por que es util para aplicar una guia de estilo?

borra todos los colores que tailwind trae por defecto (red-500, blue-600, slate-100...) y solo quedan los que declaro en @theme
asi la guia es la unica fuente de colores: una clase como bg-red-500 no genera css, y cambiar un token cambia toda la pagina

### ¿Como funciona --spacing y por que encaja con los nombres de los espacios de la guia?

--spacing es la unidad base de 4 px (0.25rem) y las clases p-*, m-*, gap-* calculan numero x --spacing, asi que p-4 son 16 px
encaja porque espai-N ya es ese multiplicador: espai-4 es p-4 y espai-12 es p-12, sin declarar cada espacio por separado

### ¿Como se ha hecho el velo de la presentacion y por que garantiza el contraste del titular?

el token --color-vel es nit al 65 % (rgb(38 35 31 / 0.65)) y @utility bg-hero lo pone como degradado encima de imatges/hero.jpg
en el peor caso, un pixel blanco de la foto, el fondo queda en #726F6D y el blanco del titular da 4,94:1, por encima del minimo de 4,5:1
por eso el texto del hero va en text-blanc: text-invers (4,2:1) y accent-clar (3,9:1) no llegarian en ese caso
