---
title: "Actividad 1: Ejercicios prácticos de Java"
position: 1
date: "2025-10-15"
---

Nota de implementación: realice cada ejercicio exclusivamente en el método main de una clase Java dentro de un proyecto de consola.

## Plantilla por ejercicios en main

- Utilice el siguiente bloque para cada ejercicio. Duplíquelo y ajuste el número y el título según la sección correspondiente.
- No agregue lógica fuera del `main`. Mantenga comentarios breves que describan objetivo, entradas y validaciones.

```java
public class EjerciciosActividad1 {
    public static void main(String[] args) {
        // --- Declaración de variables ---       
        // TODO: Implementación en main

        // --- Identificadores ---       
        // TODO: Implementación en main

        // --- Identificadores ---       
        // TODO: Implementación en main

        // --- Estilos de convención de codificación ---       
        // TODO: Implementación en main

        // --- Tipos de datos primitivos ---       
        // TODO: Implementación en main

        // --- Tipos de datos no primitivos ---       
        // TODO: Implementación en main

        // --- Operadores aritméticos ---       
        // TODO: Implementación en main

        // --- Operadores de asignación ---       
        // TODO: Implementación en main

        // --- Operadores de comparación ---       
        // TODO: Implementación en main

        // --- Operadores lógicos ---       
        // TODO: Implementación en main

        // --- If ---       
        // TODO: Implementación en main

        // --- Switch ---       
        // TODO: Implementación en main

        // --- Otros ejemplos ---       
        // TODO: Implementación en main
        
    }
}
```

## Repositorio para fork

- Enlace oficial del repositorio: https://github.com/example-org/sena-java-actividad-01 (actualice si cambia).
- Objetivo: realizar la actividad en un fork propio, implementando todos los ejercicios en el método `main`.

### Indicaciones
- Realice un fork del repositorio en su cuenta de GitHub.
```bash
https://github.com/jfinfosena/fdoc_java_act1.git
```
- Clone su fork:
  - `git clone https://github.com/<tu-usuario>/fdoc_java_act1.git`
  - `cd fdoc_java_act1`

### Criterios de evaluación
- Correctitud de las soluciones y manejo de casos básicos.
- Cumplimiento estricto de la implementación en el método `main`.
- Organización del código, comentarios breves útiles y mensajes de commit claros.
- No incluir soluciones fuera del `main` ni dependencias externas al JDK.

## Declaración de variables
- Implemente la declaración de una variable `int` y asigne un valor, imprimiéndolo luego en consola.
- Escriba la declaración y asignación en una sola línea de una variable `double` y muestre su valor.
- Desarrolle un programa que declare una variable `String`, le asigne un texto y lo imprima.

## Identificadores
- Escriba un programa que declare variables siguiendo `lowerCamelCase` para nombres descriptivos y las imprima.
- Implemente una constante `final` en mayúsculas con guiones bajos y muestre su valor en consola.
- Cree una clase nombrada en `PascalCase` y declare dentro una variable y un mensaje explicando la convención.

## Estilos de convención de codificación
- Escriba un programa que use `lowerCamelCase` para variables y `PascalCase` para el nombre de la clase.
- Implemente variables en `snake_case` válidas en Java e imprima sus valores.
- Desarrolle un programa que incluya un comentario explicando por qué `kebab-case` no es válido para identificadores en Java.

## Tipos de datos primitivos
- Implemente declaraciones de `byte`, `short`, `int`, `long`, `float`, `double`, `boolean` y `char`, imprimiendo sus valores.
- Escriba un programa que realice una operación aritmética básica con enteros y muestre el resultado.
- Cree un programa que use un `boolean` y un condicional para imprimir mensajes según su valor.

## Tipos de datos no primitivos
- Implemente un `String` con un texto y muéstrelo en consola.
- Escriba un programa que declare un arreglo `int[]` de tamaño 3, asigne valores a sus posiciones y los imprima.
- Desarrolle una clase simple `Persona` con `nombre` y `edad`, instánciela con `new Persona(...)` y muestre un mensaje con esos datos.

## Operadores aritméticos 
- Implemente un programa que calcule suma, resta, multiplicación, división y módulo de dos enteros.
- Escriba un programa que muestre división entera y división decimal del mismo par de números.
- Desarrolle un programa que demuestre incremento y decremento sobre una variable entera.

## Operadores de asignación
- Implemente un programa que use `+=` y `-=` sobre una variable y muestre el valor resultante.
- Escriba un programa que use `*=` y `/=` con una variable `int` y muestre los cambios.
- Desarrolle un programa que aplique `%=` y explique mediante impresiones el efecto del operador.

## Operadores de comparación
- Implemente comparaciones con `==` y `!=` entre dos enteros y muestre resultados booleanos.
- Escriba comparaciones con `>`, `<`, `>=` y `<=` e imprima si se cumplen o no.
- Desarrolle un programa que use un `if` para decidir mensajes basados en comparaciones de dos variables.

## Operadores lógicos
- Implemente expresiones con `&&` y `||` usando variables booleanas y muestre los resultados.
- Escriba un programa que aplique `!` a una variable booleana y muestre el valor invertido.
- Desarrolle un programa que combine operadores lógicos y paréntesis para evaluar una condición compuesta.

## If
- Implemente un `if` que imprima un mensaje si una variable `int` es mayor que otra.
- Escriba un `if-else` que imprima mensajes distintos según si un valor cumple una condición.
- Desarrolle un `if-else if-else` que clasifique un número en tres rangos e imprima la categoría.

## Operador ternario
- Implemente el operador ternario para decidir si una edad corresponde a "mayor de edad" o "menor de edad".
- Escriba un operador ternario que calcule un descuento si la cantidad comprada supera un umbral.
- Desarrolle un operador ternario que imprima si un número es par o impar.

## Switch
- Implemente un `switch` que convierta un día de la semana (cadena) en su número correspondiente.
- Escriba un `switch` que convierta una calificación numérica en texto (Insuficiente a Excelente).
- Desarrolle un `switch` que imprima la estación del año según un número entero.

## Otros ejemplos
- Implemente un programa que determine si un número es positivo, negativo o cero usando condicionales.
- Escriba un programa que valide una contraseña comparándola con un valor esperado e imprima el resultado.
- Desarrolle un programa que clasifique una calificación en categorías usando `if-else if-else` y muestre el texto correspondiente.
