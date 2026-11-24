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

## Preguntes

### Què fa `--color-*: initial` i per què és útil per aplicar una guia d'estil?

`--color-*: initial;` esborra tots els tokens de l'espai de noms `--color-*` que Tailwind porta de sèrie (`red-500`, `blue-600`, `slate-100`…). Després només existeixen els colors que declaro jo a `@theme`.

És útil perquè **converteix la guia en l'única font de colors**: si escric una classe com `bg-red-500`, Tailwind no la reconeix i no genera cap CSS, de manera que és impossible usar sense voler un color que no és de la guia. També evita que la web s'assembli a totes les altres fetes amb Tailwind, i fa que canviar un token (per exemple `--color-accent-fosc`) canviï tota la pàgina.

### Com funciona `--spacing`, i per què encaixa amb els noms dels espais de la guia?

`--spacing` és la **unitat base** de l'escala d'espais: `--spacing: 0.25rem` (4 px). Les utilitats d'espaiat (`p-*`, `m-*`, `gap-*`, `w-*`, `mt-*`…) calculen el valor com `número × --spacing`, així que `p-4` són 4 × 4 px = 16 px.

Encaixa amb la guia perquè els noms dels espais ja són aquest multiplicador: `espai-4` és 4 unitats (16 px), `espai-12` són 12 unitats (48 px). Per això `espai-N` es tradueix directament a la classe amb el número N (`px-4`, `gap-6`, `py-12`) sense haver de declarar cada espai un per un. Els números que no existeixen a la guia (5, 7, 9…) els evito a la maquetació.

### Com he fet el vel de la presentació, i per què garanteix el contrast del titular?

He creat el token `--color-vel: rgb(38 35 31 / 0.65)`, que és el color `nit` al 65 % d'opacitat. Amb `@utility bg-hero` el combino amb la fotografia en un sol fons: un `linear-gradient(var(--color-vel), var(--color-vel))` col·locat **per sobre** de `url("imatges/hero.jpg")`. Així no calen elements extra a l'HTML i la secció només porta la classe `bg-hero`.

El vel enfosqueix la foto de manera uniforme i prou perquè el text clar hi llegeixi bé. He calculat el cas pitjor, un píxel de la foto de blanc pur, que sota el vel queda com `#726F6D`. Sobre aquest fons:

- `blanc` (titular, retol i paràgraf de la presentació) arriba a **4,94:1**.
- Sobre qualsevol altre píxel més fosc, que és la gran majoria de la foto, el contrast és encara més alt (per exemple 6,56:1 sobre un llum taronja).

Per això el titular, el retol i l'entradeta de la presentació van en `text-blanc`, i no en `text-text-invers` (4,2:1 al cas pitjor) ni `accent-clar` (3,9:1), que al cas extrem no arribarien a 4,5:1.
