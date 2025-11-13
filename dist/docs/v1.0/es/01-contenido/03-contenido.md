---
title: "Estructuras de control en Java (Bucles)"
position: 3
date: 2025-10-28
---

Las estructuras repetitivas, también conocidas como bucles, ciclos o iteraciones, son mecanismos de programación que permiten ejecutar un bloque de código varias veces, dependiendo de una condición específica. Estas estructuras son especialmente útiles cuando se necesita realizar una tarea de forma repetida o iterar sobre una colección de elementos.

Existen varios tipos de estructuras repetitivas en Java:

## Bucle while: 

Se ejecuta mientras se cumpla una condición booleana. La condición se evalúa antes de ejecutar cada iteración.

Sintaxis:
```java  
while (condición) {
    // Código que se ejecutará mientras se cumpla la condición
}
```
Ejemplo:
```java  
int i = 1;

while (i <= 10) {
    System.out.println(i);
    i++;
}
```
En este ejemplo, el bucle while imprimirá los números del 1 al 10.

## Bucle do-while: 

Similar al bucle while, pero la condición se evalúa después de ejecutar cada iteración. Esto garantiza que el bloque de código se ejecute al menos una vez.

Sintaxis:
```java  
do  {
    // Código que se ejecutará mientras se cumpla la condición
} while (condición)
```
Ejemplo:
```java  
int i = 1;

do {
    System.out.println(i);
    i++;
} while (i <= 10);
```
En este caso, el bucle do-while también imprimirá los números del 1 al 10.

## Bucle for: 

Se utiliza cuando se conoce el número exacto de iteraciones a realizar. Tiene una estructura más compacta y se compone de una inicialización, una condición y una expresión de incremento.

Sintaxis:
```java  
for (inicialización; condición; incremento) {
    // bloque de código a repetir
}
```
Ejemplo:
```java  
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}
```
Aquí, el bucle for imprimirá los números del 1 al 10 de manera similar a los ejemplos anteriores.

## Bucle for-each: 

Es utilizado para iterar sobre los elementos de una colección, como arreglos o listas. No se requiere un contador explícito, ya que itera automáticamente sobre cada elemento.

Sintaxis:
```java  
for (type variableName : arrayName) {
  // code block to be executed
}
```
Ejemplo:
```java  
int[] numeros = {1, 2, 3, 4, 5};

for (int numero : numeros) {
    System.out.println(numero);
}
```
## Ejemplos de estructuras repetitivas:

### while

#### 1. Calcular la suma de los números enteros del 1 al 100:

```java  
public class SumaNumeros {
    public static void main(String[] args) {
        int i = 1;
        int suma = 0;

        while (i <= 100) {
            suma += i;
            i++;
        }

        System.out.println("La suma de los números del 1 al 100 es: " + suma);
    }
}
```

#### 2. Pedir al usuario que ingrese un número y verificar si es primo o no:

```java  
import java.util.Scanner;

public class VerificarPrimo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Ingrese un número: ");
        int numero = sc.nextInt();

        int i = 2;
        boolean esPrimo = true;

        while (i <= numero / 2) {
            if (numero % i == 0) {
                esPrimo = false;
                break;
            }
            i++;
        }

        if (esPrimo) {
            System.out.println(numero + " es un número primo.");
        } else {
            System.out.println(numero + " no es un número primo.");
        }
    }
}
```

#### 3. Pedir al usuario que ingrese una cadena de caracteres y contar la cantidad de vocales que contiene:

```java  
import java.util.Scanner;

public class ContarVocales {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Ingrese una cadena de caracteres: ");
        String cadena = sc.nextLine();

        int i = 0;
        int contadorVocales = 0;

        while (i < cadena.length()) {
            char caracter = cadena.charAt(i);
            if (caracter == 'a' || caracter == 'e' || caracter == 'i' || caracter == 'o' || caracter == 'u' ||
                caracter == 'A' || caracter == 'E' || caracter == 'I' || caracter == 'O' || caracter == 'U') {
                contadorVocales++;
            }
            i++;
        }

        System.out.println("La cadena ingresada contiene " + contadorVocales + " vocales.");
    }
}
```
### do while

#### 1. Adivina el número:

```java  
import java.util.Scanner;

public class AdivinaNumero {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int numeroSecreto = 42;
        int intento;
        
        do {
            System.out.print("Adivina el número secreto: ");
            intento = scanner.nextInt();
            
            if (intento == numeroSecreto) {
                System.out.println("¡Felicidades! Adivinaste el número.");
            } else {
                System.out.println("Intenta nuevamente.");
            }
        } while (intento != numeroSecreto);
    }
}
```

#### 2. Suma de números:

```java  
import java.util.Scanner;

public class SumaNumeros {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int suma = 0;
        int numero;
        
        do {
            System.out.print("Ingresa un número (0 para terminar): ");
            numero = scanner.nextInt();
            
            suma += numero;
        } while (numero != 0);
        
        System.out.println("La suma de los números ingresados es: " + suma);
    }
}
```

#### 3. Menú de opciones:

```java  
import java.util.Scanner;

public class MenuOpciones {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcion;
        
        do {
            System.out.println("Menu:");
            System.out.println("1. Opción 1");
            System.out.println("2. Opción 2");
            System.out.println("3. Salir");
            System.out.print("Selecciona una opción: ");
            opcion = scanner.nextInt();
            
            switch (opcion) {
                case 1:
                    System.out.println("Seleccionaste la opción 1.");
                    break;
                case 2:
                    System.out.println("Seleccionaste la opción 2.");
                    break;
                case 3:
                    System.out.println("Saliendo del programa...");
                    break;
                default:
                    System.out.println("Opción inválida. Intenta nuevamente.");
            }
        } while (opcion != 3);
    }
}
```

### for

#### 1. Impresión de números pares:

```java  
public class NumerosPares {
    public static void main(String[] args) {
        for (int i = 2; i <= 10; i += 2) {
            System.out.println(i);
        }
    }
}
```

#### 2. Cálculo del factorial:

```java  
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Ingresa un número: ");
        int numero = scanner.nextInt();
        int factorial = 1;
        
        for (int i = 1; i <= numero; i++) {
            factorial *= i;
        }
        
        System.out.println("El factorial de " + numero + " es: " + factorial);
    }
}
```

#### 3. Suma de elementos de un arreglo:

```java  
public class SumaArreglo {
    public static void main(String[] args) {
        int[] numeros = {5, 8, 3, 2, 9};
        int suma = 0;
        
        for (int numero : numeros) {
            suma += numero;
        }
        
        System.out.println("La suma de los elementos del arreglo es: " + suma);
    }
}
```

### for-each

#### 1. Suma de elementos en un arreglo

```java  
public class SumaArreglo {
    public static void main(String[] args) {
        int[] numeros = { 10, 20, 30, 40, 50 };
        int suma = 0;

        for (int numero : numeros) {
            suma += numero;
        }

        System.out.println("La suma de los elementos del arreglo es: " + suma);
    }
}
```

#### 2. Imprimir elementos de una lista de cadenas

```java  
import java.util.ArrayList;
import java.util.List;

public class ImprimirLista {
    public static void main(String[] args) {
        List<String> palabras = new ArrayList<>();
        palabras.add("Hola");
        palabras.add("Mundo");
        palabras.add("en");
        palabras.add("Java");

        for (String palabra : palabras) {
            System.out.println(palabra);
        }
    }
}
```

#### 3. Calificaciones y promedio de un estudiante

```java  
public class PromedioCalificaciones {
    public static void main(String[] args) {
        double[] calificaciones = { 85.5, 90.0, 78.5, 95.5, 88.0 };
        double suma = 0;

        for (double calificacion : calificaciones) {
            suma += calificacion;
        }

        double promedio = suma / calificaciones.length;
        System.out.println("El promedio de calificaciones es: " + promedio);
    }
}
```


## Break y Continue en Ciclos en Java

**Break y Continue** son palabras clave que se utilizan dentro de los ciclos (bucles) en Java para controlar su flujo de ejecución.

**1. Break:**

* **Función:** Interrumpe completamente la ejecución del ciclo actual, es decir, el ciclo se termina de forma prematura.
* **Uso:** Se utiliza cuando se quiere salir del ciclo inmediatamente, por ejemplo, cuando se encuentra la condición deseada.

**Ejemplo:**

```java
for (int i = 0; i < 10; i++) {
  if (i == 5) {
    break; // Sale del ciclo cuando i es 5
  }
  System.out.println(i);
}
```

En este ejemplo, el ciclo imprime los números del 0 al 4, ya que `break` interrumpe el ciclo cuando `i` alcanza el valor 5.

**2. Continue:**

* **Función:** Salta a la siguiente iteración del ciclo actual, es decir, ignora el resto del código dentro del ciclo para la iteración actual.
* **Uso:** Se utiliza cuando se quiere omitir una iteración específica del ciclo, por ejemplo, cuando se encuentra una condición que no se quiere procesar.

**Ejemplo:**

```java
for (int i = 0; i < 10; i++) {
  if (i % 2 == 0) {
    continue; // Salta la iteración si i es par
  }
  System.out.println(i);
}
```

En este ejemplo, el ciclo imprime solo los números impares del 0 al 9, ya que `continue` salta las iteraciones donde `i` es par.

**Diferencias clave entre Break y Continue:**

| Característica | Break | Continue |
|---|---|---|
| Acción | Termina el ciclo completamente | Salta a la siguiente iteración |
| Iteraciones restantes | Ninguna | Sí |
| Código omitido | Todo el código restante del ciclo | El código restante de la iteración actual |

**Ejemplo combinando Break y Continue:**

```java
for (int i = 0; i < 10; i++) {
  if (i == 3) {
    break; // Sale del ciclo si i es 3
  }
  if (i % 2 == 0) {
    continue; // Salta la iteración si i es par
  }
  System.out.println(i);
}
```

Este ejemplo imprime los números 1, 3, 5 y 7, ya que `continue` salta las iteraciones donde `i` es par, y `break` termina el ciclo cuando `i` es 3.


### Ejemplos con While usando Break y Continue

Aquí tienes algunos ejemplos de cómo usar `break` y `continue` dentro de ciclos `while` en Java:

**1. Break en While:**

```java
int i = 0;
while (true) {
  System.out.println(i);
  i++;
  if (i == 5) {
    break; // Termina el ciclo cuando i es 5
  }
}
```

En este ejemplo, el ciclo `while` se ejecuta indefinidamente (`true`) hasta que `i` alcanza el valor 5, en cuyo momento `break` termina el ciclo.

**2. Continue en While:**

```java
int i = 0;
while (i < 10) {
  if (i % 2 == 0) {
    continue; // Salta la iteración si i es par
  }
  System.out.println(i);
  i++;
}
```

Este ejemplo imprime solo los números impares del 0 al 9. `continue` salta las iteraciones donde `i` es par, evitando que se ejecute `System.out.println(i)`.

**3. Break y Continue combinados:**

```java
int i = 0;
while (i < 10) {
  if (i == 3) {
    break; // Sale del ciclo si i es 3
  }
  if (i % 2 == 0) {
    continue; // Salta la iteración si i es par
  }
  System.out.println(i);
  i++;
}
```

En este ejemplo, el ciclo imprime los números 1, 3, 5 y 7. `continue` salta las iteraciones donde `i` es par, y `break` termina el ciclo cuando `i` es 3.

**4.  Ejemplo práctico: Buscar un elemento en un arreglo:**

```java
int[] numbers = {1, 4, 7, 2, 9, 6};
int target = 7;
int i = 0;

while (i < numbers.length) {
  if (numbers[i] == target) {
    System.out.println("El número " + target + " se encontró en la posición " + i);
    break; // Termina el ciclo si se encuentra el número
  }
  i++;
}

if (i == numbers.length) {
  System.out.println("El número " + target + " no se encontró en el arreglo.");
}
```

Este ejemplo busca el número `target` (7) en el arreglo `numbers`. Si se encuentra, se imprime la posición y el ciclo se termina con `break`. Si no se encuentra, se imprime un mensaje indicando que no está en el arreglo.
