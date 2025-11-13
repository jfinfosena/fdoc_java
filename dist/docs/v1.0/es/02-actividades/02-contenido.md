---
title: "Actividad 2: Bucles en Java"
position: 2
date: "2025-10-30"
---

Nota de implementación: realice cada ejercicio exclusivamente en el método main de una clase Java dentro de un proyecto de consola.

## Plantilla por ejercicios en main

- Utilice el siguiente bloque para cada ejercicio. Duplíquelo y ajuste el número y el título según la sección correspondiente.
- No agregue lógica fuera del `main`. Mantenga comentarios breves que describan objetivo, entradas y validaciones.

```java
public class EjerciciosActividad2 {
    public static void main(String[] args) {
        // --- While ---       
        // TODO: Implementación en main

        // --- Do-while ---       
        // TODO: Implementación en main

        // --- For ---       
        // TODO: Implementación en main

        // --- For-each ---       
        // TODO: Implementación en main

        // --- Break y Continue ---       
        // TODO: Implementación en main

        // Sugerencia: copie y adapte el bloque anterior por cada ejercicio de las secciones de bucles.
        // Recomendaciones generales
        // - Ejecute y valide cada ejercicio de forma independiente.
        // - Si la salida interfiere entre ejercicios, comente temporalmente los anteriores.
        // - Mantenga coherencia en mensajes y formato de salida.
    }
}
```

## Repositorio para fork

- Enlace oficial del repositorio: https://github.com/jfinfosena/fdoc_java_act1.git (actualice si cambia).
- Objetivo: realizar la actividad en un fork propio, implementando todos los ejercicios en el método `main`.

### Indicaciones
- Realice un fork del repositorio en su cuenta de GitHub.
```bash
https://github.com/jfinfosena/fdoc_java_act2.git
```
- Clone su fork:
  - `git clone https://github.com/<tu-usuario>/fdoc_java_act2.git`
  - `cd fdoc_java_act2`

### Registro del grupo: info.json
Antes de iniciar la preparación, diligencia el archivo `info.json` en la raíz del repositorio del líder con la siguiente estructura:

```json
{
  "nombres": "",
  "apellidos": "",
  "grupo": "datos-#"
}
```

### Criterios de evaluación
- Correctitud de las soluciones y manejo de casos básicos.
- Cumplimiento estricto de la implementación en el método `main`.
- Organización del código, comentarios breves útiles y mensajes de commit claros.
- No incluir soluciones fuera del `main` ni dependencias externas al JDK.

## While
- Diseñe un ciclo que imprima números del 1 al 10, validando límites antes de cada iteración.
- Implemente un ciclo que acumule la suma de 1 a `n`, mostrando el total en consola.
- Construya un ciclo que busque si un número ingresado está en un arreglo; deténgase al encontrarlo.

## Do-while
- Cree un menú interactivo que se muestre al menos una vez y termine al elegir “Salir”.
- Implemente la lectura de números hasta que el usuario ingrese 0; muestre la suma acumulada.
- Desarrolle la validación de una contraseña con al menos una ejecución, repitiendo hasta acertar.

## For
- Genere la impresión de los números pares del 2 al 20 usando incremento apropiado.
- Calcule el factorial de un número ingresado y muestre el resultado.
- Sume los elementos de un arreglo de enteros utilizando un contador en el ciclo.

## For-each
- Recorra un arreglo de enteros y calcule la suma, mostrando el total.
- Liste en consola cada palabra de una colección de cadenas predefinida.
- Calcule el promedio de un arreglo de calificaciones y muestre el resultado con dos decimales.

## Break y Continue
- Inserte `break` en un ciclo `for` para detener la iteración al cumplir una condición específica.
- Aplique `continue` para omitir el procesamiento de elementos que cumplan cierta condición.
- Combine `break` y `continue` en un ciclo para manejar casos particulares y detenerse al alcanzar un umbral.
