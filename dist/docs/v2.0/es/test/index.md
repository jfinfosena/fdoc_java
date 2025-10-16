---
title: "Pruebas de anidación de componentes (+++)"
folder_position: 4
---

# Pruebas de anidación (un nivel)

Esta página demuestra cómo anidar componentes personalizados un nivel usando la sintaxis `+++`.

## Estrategia recomendada

- Usar `NestedMarkdown` para renderizar el contenido interno de componentes que aceptan bloques `+++`.
- Parsear front matter con `gray-matter` y pasar su `content` a `NestedMarkdown`.
- Confiar en `convertPlusFencesToBackticks` para convertir correctamente los `+++` (incluye manejo básico de anidación).
- Mantener un solo nivel de anidación: evitar `+++` dentro de otro `+++` más de una vez.

---

## Ejemplo 1: Admonition con Steps anidados

+++admonition
---
type: info
title: "Checklist de instalación rápida"
---
+++steps
### Instalar dependencias
1. Node.js 18+
2. npm 9+

### Ejecutar dev server
1. `npm run dev`

### Abrir la app
Visita `/test/` después de iniciar.
+++
---

---

## Ejemplo 2: Grid con Tabs anidados

+++grid
---
columns: 2
---
+++tabs
---[tab title="Python" lang="py"]---
print("Hola desde Python")
---[tab title="JavaScript" lang="js"]---
console.log("Hola desde JS");
+++
---
+++stat-cards
---
columns: 2
items:
  - icon: "TrendingUpIcon"
    value: "42%"
    label: "Crecimiento"
    color: "green"
  - icon: "ServerIcon"
    value: "12"
    label: "Instancias"
    color: "blue"
---
+++

---

## Ejemplo 3: Accordion con Admonition anidado

+++accordion
---
allowMultiple: false
---
### Bloque 1: Consejos útiles
Texto introductorio y a continuación una advertencia:

+++admonition
---
type: warning
title: "Recuerda"
---
Evita anidar más de un nivel de `+++` dentro del mismo bloque para mantener el rendimiento y la legibilidad.
+++

### Bloque 2: Nota informativa
Este bloque no contiene componentes anidados.
+++
