---
title: "Clase 2 - Operadores y instrucciones de control condicional"
position: 2
date: 2025-10-23
---

## Operadores aritméticos 

Los operadores aritméticos en Java se utilizan para realizar operaciones matemáticas básicas. Los operadores aritméticos incluyen:

### Suma (+): se utiliza para sumar dos valores.

```java
int a = 5;
int b = 10;
int c = a + b; // c es igual a 15
```

### Resta (-): se utiliza para restar un valor de otro.

```java
int a = 10;
int b = 5;
int c = a - b; // c es igual a 5
```

### Multiplicación (\*): se utiliza para multiplicar dos valores.

```java
int a = 5;
int b = 10;
int c = a * b; // c es igual a 50
```

### División (/): se utiliza para dividir un valor entre otro.

```java
int a = 10;
int b = 5;
int c = a / b; // c es igual a 2
```

### Módulo (%): se utiliza para obtener el resto de una división entre dos valores.

```java
int a = 10;
int b = 3;
int c = a % b; // c es igual a 1
```

### Ejemplos

```java
public class OperadoresAritmeticos {

    public static void main(String[] args) {
        int x = 10;
        int y = 5;

        // Suma
        int resultadoSuma = x + y;
        System.out.println("El resultado de la suma es: " + resultadoSuma);

        // Resta
        int resultadoResta = x - y;
        System.out.println("El resultado de la resta es: " + resultadoResta);

        // Multiplicación
        int resultadoMultiplicacion = x * y;
        System.out.println("El resultado de la multiplicación es: " + resultadoMultiplicacion);

        // División
        int resultadoDivisionEntera = x / y;
        System.out.println("El resultado de la división entera es: " + resultadoDivisionEntera);

        double resultadoDivisionDecimal = (double) x / y;
        System.out.println("El resultado de la división decimal es: " + resultadoDivisionDecimal);

        // Módulo
        int resultadoModulo = x % y;
        System.out.println("El resultado del módulo es: " + resultadoModulo);

        // Incremento
        x++;
        System.out.println("El valor de x después del incremento es: " + x);

        // Decremento
        y--;
        System.out.println("El valor de y después del decremento es: " + y);
    }
}
```

## Operadores de Asignación

En Java, los operadores de asignación son símbolos que se utilizan para asignar valores a las variables. Además de la asignación básica (=), Java ofrece otros operadores de asignación que combinan la asignación con una operación matemática. Estos operadores de asignación son útiles para simplificar y acortar el código en situaciones donde se realiza una operación aritmética y luego se asigna el resultado a una variable.

A continuación se describen los operadores de asignación disponibles en Java:

### Operador de asignación básico (=)

Se utiliza para asignar un valor a una variable. Por ejemplo:

```java
int x = 5;
```

### Operador de asignación compuesta de suma (+=)

Se utiliza para sumar un valor a una variable y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x += 3; es equivalente a x = x + 3;
```

### Operador de asignación compuesta de resta (-=)

Se utiliza para restar un valor de una variable y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x -= 2; es equivalente a x = x - 2;
```

### Operador de asignación compuesta de multiplicación (\*=)

Se utiliza para multiplicar una variable por un valor y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x *= 4; es equivalente a x = x * 4;
```

### Operador de asignación compuesta de división (/=)

Se utiliza para dividir una variable por un valor y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x /= 2; es equivalente a x = x / 2;
```

### Operador de asignación compuesta de módulo (%=)

Se utiliza para calcular el módulo de una variable por un valor y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x %= 3; es equivalente a x = x % 3;
```

### Operador de asignación compuesta de desplazamiento a la izquierda (`<<=`)

Se utiliza para desplazar los bits de una variable a la izquierda por un número de posiciones y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x <<= 2; es equivalente a x = x << 2;
```

### Operador de asignación compuesta de desplazamiento a la derecha (>>=)

Se utiliza para desplazar los bits de una variable a la derecha por un número de posiciones y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x >>= 1; es equivalente a x = x >> 1;
```

### Operador de asignación compuesta de desplazamiento a la derecha sin signo (>>>=)

Se utiliza para desplazar los bits de una variable a la derecha sin signo por un número de posiciones y luego asignar el resultado a la misma variable. Por ejemplo:

```java
x >>>= 3; es equivalente a x = x >>> 3;
```

Es importante recordar que los operadores de asignación compuesta realizan la operación indicada y luego asignan el resultado a la misma variable. Por lo tanto, la variable se modifica en el lugar en el que se encuentra sin necesidad de declarar una nueva variable.

### Ejemplos

```java
public class OperadoresAsignacion {

    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        // Operador de asignación simple
        int c = a + b;
        System.out.println("c = " + c);

        // Operadores de asignación compuestos
        a += b; // equivalente a a = a + b;
        System.out.println("a = " + a);

        b -= 3; // equivalente a b = b - 3;
        System.out.println("b = " + b);

        c *= 2; // equivalente a c = c * 2;
        System.out.println("c = " + c);

        double d = 6.0;
        d /= 2; // equivalente a d = d / 2;
        System.out.println("d = " + d);

        int e = 7;
        e %= 3; // equivalente a e = e % 3;
        System.out.println("e = " + e);

        // Operador de concatenación de cadenas
        String s1 = "Hola";
        String s2 = "Mundo";
        String s3 = s1 + " " + s2;
        System.out.println(s3); // Hola Mundo

        // Operador de asignación ternario
        int edad = 18;
        String mensaje = (edad >= 18) ? "Eres mayor de edad" : "Eres menor de edad";
        System.out.println(mensaje);
    }
}
```

## Operadores de comparación

En Java, los operadores de comparación se utilizan para comparar dos valores y evaluar si una determinada condición es verdadera o falsa. A continuación, se muestran los operadores de comparación más comunes en Java, junto con sus nombres y descripciones:

### Operador de igualdad (==)

Nombre: Igual a
Descripción: Comprueba si dos valores son iguales.

```java
int a = 5;
int b = 7;
boolean resultado = (a == b); // false
```

### Operador de desigualdad (!=)

Nombre: No igual a
Descripción: Comprueba si dos valores son diferentes.

```java
int a = 5;
int b = 7;
boolean resultado = (a != b); // true
```

### Operador mayor que (>)

Nombre: Mayor que
Descripción: Comprueba si el valor de la izquierda es mayor que el valor de la derecha.

```java
int a = 5;
int b = 7;
boolean resultado = (a > b); // false
```

### Operador menor que (`<`)

Nombre: Menor que
Descripción: Comprueba si el valor de la izquierda es menor que el valor de la derecha.

```java
int a = 5;
int b = 7;
boolean resultado = (a < b); // true
```

### Operador mayor o igual que (>=)

Nombre: Mayor o igual que
Descripción: Comprueba si el valor de la izquierda es mayor o igual que el valor de la derecha.

```java
int a = 5;
int b = 7;
boolean resultado = (a >= b); // false
```

### Operador menor o igual que (`<=`)

Nombre: Menor o igual que
Descripción: Comprueba si el valor de la izquierda es menor o igual que el valor de la derecha.

```java
int a = 5;
int b = 7;
boolean resultado = (a <= b); // true
```

### Ejemplos

```java
public class OperadoresComparación {

    public static void main(String[] args) {
        int x = 5;
        int y = 10;
        boolean esIgual = (x == y); // Devuelve false, porque x no es igual a y.
        boolean esDiferente = (x != y); // Devuelve true, porque x es diferente a y.
        boolean esMenor = (x < y); // Devuelve true, porque x es menor que y.
        boolean esMayor = (x > y); // Devuelve false, porque x no es mayor que y.
        boolean esMenorIgual = (x <= y); // Devuelve true, porque x es menor o igual que y.
        boolean esMayorIgual = (x >= y); // Devuelve false, porque x no es mayor o igual que y.
    }
}
```

## Operadores lógicos

Los operadores lógicos en Java permiten realizar operaciones booleanas entre dos o más expresiones. Estos operadores son muy útiles en la toma de decisiones y en la evaluación de condiciones en una variedad de situaciones. Los tres operadores lógicos en Java son AND (&&), OR (||) y NOT (!).

Aquí te explico cómo funcionan estos operadores:

### AND (&&)

Este operador retorna true si ambas expresiones a su izquierda y derecha son verdaderas. Si al menos una de las expresiones es falsa, retorna false. Por ejemplo:

```java
boolean a = true;
boolean b = false;
boolean resultado = a && b; // false
```

### OR (||)

Este operador retorna true si al menos una de las expresiones a su izquierda o derecha es verdadera. Si ambas expresiones son falsas, retorna false. Por ejemplo:

```java
boolean a = true;
boolean b = false;
boolean resultado = a || b; // true
```

### NOT (!)

Este operador invierte el valor booleano de la expresión a su derecha. Si la expresión es verdadera, retorna false, y si es falsa, retorna true. Por ejemplo:

```java
boolean a = true;
boolean resultado = !a; // false
```

Además, también es posible combinar estos operadores para formar expresiones booleanas más complejas, utilizando paréntesis para establecer el orden de evaluación. Por ejemplo:

```java
boolean a = true;
boolean b = false;
boolean c = true;
boolean resultado = (a || b) && !c; // false
```

En este ejemplo, primero se evalúa la expresión (a || b), que retorna true. Luego, se aplica el operador NOT a la variable c, que es verdadera, resultando en false. Finalmente, se aplica el operador AND a los resultados anteriores, lo que resulta en false.

### Ejemplos

```java
public class OperadoresLogicos {
    public static void main(String[] args) {
        int edad = 25;
        boolean esEstudiante = true;
        boolean esDiaLaboral = false;
        boolean esVacaciones = true;

        boolean resultado1 = (edad > 18) && esEstudiante;
        boolean resultado2 = esDiaLaboral || esVacaciones;
        boolean resultado3 = !esDiaLaboral;

        System.out.println("El resultado 1 es: " + resultado1);
        System.out.println("El resultado 2 es: " + resultado2);
        System.out.println("El resultado 3 es: " + resultado3);
    }
}
```

## Estructuras condicionales:

Las estructuras condicionales en Java permiten tomar decisiones y ejecutar ciertas partes de código dependiendo si se cumple o no una determinada condición.

Las principales estructuras condicionales son:

### 1. if: Ejecuta un bloque de código si se cumple la condición.

Sintaxis:
```java  
if (condición) {
  // código a ejecutar 
}
```

### Ejemplos if:

Estos ejemplos muestran diferentes formas de utilizar estructuras condicionales en Java para tomar decisiones basadas en ciertas condiciones.

#### 1. Comprobando si una variable es mayor que otra:

```java  
int x = 10;
int y = 5;

if (x > y) {
  System.out.println("x es mayor que y");
}
```
#### 2. Comprobando si una variable es diferente de un valor específico:

```java  
int edad = 18;

if (edad != 18) {
  System.out.println("La edad no es 18");
}
```
#### 3. Comprobando si una variable está dentro de un rango de valores:

```java  
int nota = 10;

if (nota >= 9 && nota <= 10) {
  System.out.println("La nota es excelente");
}
```


### 2. if - else: Ejecuta un bloque si se cumple la condición, y otro bloque distinto si no se cumple.

Sintaxis:
```java  
if (condición) {
  // código si se cumple
} else {
  // código si no se cumple
}
```


### Ejemplos if else:

#### 1. Comprobando si una variable es mayor que otra y, si no, imprimiendo un mensaje diferente:

```java  
int x = 10;
int y = 5;

if (x > y) {
  System.out.println("x es mayor que y");
} else {
  System.out.println("x es menor o igual que y");
}
```

#### 2. Comprobando si una variable es igual a un valor específico y, si no, imprimiendo un mensaje diferente:

```java  
String nombre = "Juan";

if (nombre.equals("Juan")) {
  System.out.println("El nombre es Juan");
} else {
  System.out.println("El nombre no es Juan");
}
```

#### 3. Comprobando si una variable está dentro de un rango de valores y, si no, imprimiendo un mensaje diferente:

```java  
int nota = 10;

if (nota >= 9 && nota <= 10) {
  System.out.println("La nota es excelente");
} else {
  System.out.println("La nota no es excelente");
}
```

### 3. if - else if - else: Permite evaluar múltiples condiciones. Se ejecuta el primer bloque donde se cumpla la condición.

Sintaxis:
```java  
if (condición 1) {
  // código si se cumple 1
} else if (condición 2) {
  // código si se cumple 2 
} else {
  // código si no se cumple ninguna
}
```

### Ejemplos else if:

#### 1. Comprobando si una variable es mayor que otra, si no, si es igual y, si no, imprimiendo un mensaje diferente:

```java  
int x = 10;
int y = 5;

if (x > y) {
  System.out.println("x es mayor que y");
} else if (x == y) {
  System.out.println("x es igual a y");
} else {
  System.out.println("x es menor que y");
}
```
#### 2. Comprobando si una variable está dentro de un rango de valores, si no, si es mayor o si es menor y, si no, imprimiendo un mensaje diferente:

```java  
int nota = 10;

if (nota >= 9 && nota <= 10) {
  System.out.println("La nota es excelente");
} else if (nota > 10) {
  System.out.println("La nota es sobresaliente");
} else if (nota < 0) {
  System.out.println("La nota es inválida");
} else {
  System.out.println("La nota es buena");
}
```
#### 3. Comprobando si una variable está vacía o no, si no, si tiene una longitud específica y, si no, imprimiendo un mensaje diferente:

```java  
String cadena = "";

if (cadena.isEmpty()) {
  System.out.println("La cadena está vacía");
} else if (cadena.length() == 0) {
  System.out.println("La cadena es nula");
} else {
  System.out.println("La cadena no está vacía");
}
```

### 4. Operador ternario

El operador ternario en Java es una expresión que se utiliza para evaluar una condición y devolver uno de dos valores, dependiendo del resultado de la evaluación. La sintaxis del operador ternario es:

Sintaxis:
```java  
variable = (condicion) ? valor_si_verdadero : valor_si_falso;
```

### Ejemplos operador ternario:

#### 1. Evaluar si es mayor de edad
```java  
int edad = 18;
String mensaje = (edad >= 18) ? "Eres mayor de edad" : "Eres menor de edad";

System.out.println(mensaje); // Imprime "Eres mayor de edad"
```

#### 2. Calcular el descuento de un producto
```java  
double precio = 100.0;
int cantidad = 5;
double descuento = (cantidad >= 3) ? precio * 0.1 : 0.0;

double precioFinal = precio - descuento;

System.out.println("Precio final: " + precioFinal); // Imprime 90.0
```

#### 3. Devuelve el texto "El número es par" si el número es par, y el texto "El número es impar" si el número es impar.
```java  
String texto = (numero % 2 == 0) ? "El número es par" : "El número es impar";
```

### 5. switch: Evalúa una variable o expresión y ejecuta el código del case que coincida con el valor.

Sintaxis:
```java  
switch(expresión) {
  case valor1: 
    //código
    break;
  case valor2: 
   //código
   break;
  default:
   //código por defecto  
}
```

Estas estructuras permiten controlar el flujo del programa ejecutando código de manera condicional. Son muy útiles para realizar selecciones y tomar decisiones en la lógica de un programa.

### Ejemplos switch:

#### 1. Escribe un programa que le pida al usuario que ingrese un día de la semana. El programa debe imprimir el número del día de la semana.

```java  
import java.util.Scanner;

public class DiaSemana {

  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    System.out.println("Ingrese un día de la semana: ");
    String dia = sc.nextLine();

    switch (dia) {
      case "lunes":
        System.out.println("1");
        break;
      case "martes":
        System.out.println("2");
        break;
      case "miércoles":
        System.out.println("3");
        break;
      case "jueves":
        System.out.println("4");
        break;
      case "viernes":
        System.out.println("5");
        break;
      case "sábado":
        System.out.println("6");
        break;
      case "domingo":
        System.out.println("7");
        break;
      default:
        System.out.println("Día no válido");
    }
  }
}
```

#### 2. Escribe un programa que le pida al usuario que ingrese una calificación de 1 a 10. El programa debe imprimir la calificación en letras.

```java  
import java.util.Scanner;

public class Calificacion {

  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    System.out.println("Ingrese una calificación de 1 a 10: ");
    int calificacion = sc.nextInt();

    switch (calificacion) {
      case 1:
        System.out.println("Insuficiente");
        break;
      case 2:
        System.out.println("Insuficiente");
        break;
      case 3:
        System.out.println("Insuficiente");
        break;
      case 4:
        System.out.println("Suficiente");
        break;
      case 5:
        System.out.println("Bien");
        break;
      case 6:
        System.out.println("Notable");
        break;
      case 7:
        System.out.println("Sobresaliente");
        break;
      case 8:
        System.out.println("Sobresaliente");
        break;
      case 9:
        System.out.println("Sobresaliente");
        break;
      case 10:
        System.out.println("Excelente");
        break;
      default:
        System.out.println("Calificación no válida");
    }
  }
}
```

#### 3. Escribe un programa que le pida al usuario que ingrese un número entero. El programa debe imprimir la estación del año correspondiente al número.

```java  
import java.util.Scanner;

public class Estacion {

  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    System.out.println("Ingrese un número entero: ");
    int numero = sc.nextInt();

    switch (numero) {
      case 1:
      case 2:
      case 3:
        System.out.println("Invierno");
        break;
      case 4:
      case 5:
      case 6:
        System.out.println("Primavera");
        break;
      case 7:
      case 8:
      case 9:
        System.out.println("Verano");
        break;
      case 10:
      case 11:
      case 12:
        System.out.println("Otoño");
        break;
      default:
        System.out.println("Número no válido");
    }
  }
}
```

### Otros ejemplos

#### 1. Comprobación del número par o impar:

```java  
int numero = 7;

if (numero % 2 == 0) {
    System.out.println("El número es par.");
} else {
    System.out.println("El número es impar.");
}
```
#### 2. Evaluación de la calificación de un estudiante:

```java  
int calificacion = 85;

if (calificacion >= 90) {
    System.out.println("Excelente");
} else if (calificacion >= 80) {
    System.out.println("Bueno");
} else if (calificacion >= 70) {
    System.out.println("Regular");
} else {
    System.out.println("Reprobado");
}
```
#### 3. Verificación de la elegibilidad para votar:

```java  
int edad = 17;

if (edad >= 18) {
    System.out.println("Eres elegible para votar.");
} else {
    System.out.println("No eres elegible para votar.");
}
```
#### 4. Determinar si un número es positivo, negativo o cero:

```java  
int numero = -3;

if (numero > 0) {
    System.out.println("El número es positivo.");
} else if (numero < 0) {
    System.out.println("El número es negativo.");
} else {
    System.out.println("El número es cero.");
}
```
#### 5. Validación de una contraseña:

```java  
String contraseña = "secreta123";

if (contraseña.equals("secreta123")) {
    System.out.println("Contraseña correcta. Acceso concedido.");
} else {
    System.out.println("Contraseña incorrecta. Acceso denegado.");
}
```

