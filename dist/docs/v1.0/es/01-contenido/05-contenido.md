---
title: "Introducción a Programación Orientada a Objetos y Java"
position: 5
date: 2025-11-13
---

## Objetivos de la Clase
- Comprender los fundamentos de la Programación Orientada a Objetos (POO) y su importancia en el desarrollo de software.
- Configurar un entorno de desarrollo para programar en Java.
- Analizar la estructura básica de un programa en Java y escribir un primer programa funcional.

---

## 1. Conceptos Básicos de POO

La **Programación Orientada a Objetos (POO)** es un paradigma de programación que organiza el código en torno a "objetos" que representan entidades del mundo real. Estos objetos combinan datos (atributos) y comportamientos (métodos) para modelar sistemas de manera modular y reutilizable. Los principales conceptos de POO son:

### 1.1. Clases
Una **clase** es una plantilla o blueprint que define las propiedades y comportamientos de un tipo de objeto. Por ejemplo, una clase `Coche` puede describir atributos como `color` o `marca` y métodos como `acelerar()` o `frenar()`.

```java
public class Coche {
    String color; // Atributo
    String marca;

    void acelerar() { // Método
        System.out.println("El coche está acelerando.");
    }
}
```

### 1.2. Objetos
Un **objeto** es una instancia de una clase. Representa una entidad específica creada a partir de la plantilla de la clase. Por ejemplo, un objeto de la clase `Coche` podría ser un coche rojo de marca Toyota.

```java
Coche miCoche = new Coche(); // Creación de un objeto
miCoche.color = "Rojo";
miCoche.marca = "Toyota";
miCoche.acelerar();
```

### 1.3. Encapsulamiento
El **encapsulamiento** consiste en ocultar los detalles internos de una clase y exponer solo lo necesario a través de métodos públicos. Esto se logra usando modificadores de acceso (`private`, `public`) y métodos `getters` y `setters`.

```java
public class Coche {
    private String color; // Atributo privado

    public String getColor() { // Getter
        return color;
    }

    public void setColor(String color) { // Setter
        this.color = color;
    }
}
```

### 1.4. Herencia
La **herencia** permite que una clase (subclase) herede atributos y métodos de otra clase (superclase), promoviendo la reutilización de código. Por ejemplo, una clase `Camion` puede heredar de `Vehiculo`.

```java
public class Vehiculo {
    String marca;
    void mover() {
        System.out.println("El vehículo se mueve.");
    }
}

public class Camion extends Vehiculo {
    int capacidadCarga;
}
```

### 1.5. Polimorfismo
El **polimorfismo** permite que objetos de diferentes clases sean tratados como objetos de una clase común, generalmente a través de herencia o interfaces. Por ejemplo, un método puede aceptar un `Vehiculo` pero trabajar con un `Coche` o un `Camion`.

```java
Vehiculo miVehiculo = new Coche(); // Polimorfismo
miVehiculo.mover();
```

Clases y Objetos en Java

## Objetivos de la Clase
- Comprender la definición y propósito de clases y objetos en la programación orientada a objetos (POO).
- Aprender a declarar atributos y métodos en una clase.
- Dominar la creación e instanciación de objetos en Java.
- Aplicar estos conceptos en ejemplos contextualizados para la región de Colombia, utilizando casos relacionados con elementos representativos como el fútbol.

---

## 1. Definición de Clases y Objetos

### 1.1. Clases
Una **clase** en Java es una plantilla que define las características (atributos) y comportamientos (métodos) de un tipo de entidad. Actúa como un molde para crear objetos. Por ejemplo, una clase `JugadorFutbol` puede representar a un jugador de fútbol con características como su nombre y número de camiseta.


<figure markdown="span">
  ![Image title](https://jfinfocesde.github.io/25b1/assets/images/img1.svg){ width="500" }
  <figcaption>Image caption</figcaption>
</figure>

```java
public class JugadorFutbol {
    String nombre; // Atributo
    int numeroCamiseta; // Atributo
}
```

### 1.2. Objetos
Un **objeto** es una instancia específica de una clase. Representa una entidad concreta creada a partir del molde de la clase. Por ejemplo, un objeto de la clase `JugadorFutbol` podría ser un jugador específico como "James Rodríguez" con el número de camiseta 10.

<figure markdown="span">
  ![Image title](https://jfinfocesde.github.io/25b1/assets/images/img2.svg){ width="500" }
  <figcaption>Image caption</figcaption>
</figure>

```java
JugadorFutbol jugador = new JugadorFutbol(); // Creación de un objeto
jugador.nombre = "James Rodríguez";
jugador.numeroCamiseta = 10;
```

### 1.3. Relación entre Clases y Objetos
- La clase es como el diseño de un estadio de fútbol: define la estructura (tribunas, campo, vestuarios).
- El objeto es un estadio específico, como el Estadio Metropolitano de Barranquilla, que sigue ese diseño pero con detalles únicos.

---

## 2. Atributos y Métodos

### 2.1. Atributos
Los **atributos** son variables definidas dentro de una clase que representan las propiedades o datos de un objeto. En el contexto de un jugador de fútbol, los atributos podrían incluir el nombre, la posición en el campo y el número de goles anotados.

<figure markdown="span">
  ![Image title](https://jfinfocesde.github.io/25b1/assets/images/img3.svg){ width="500" }
  <figcaption>Image caption</figcaption>
</figure>

```java
public class JugadorFutbol {
    String nombre; // Atributo para el nombre del jugador
    String posicion; // Atributo para la posición (ej. "Delantero")
    int golesAnotados; // Atributo para el número de goles
}
```

### 2.2. Métodos
Los **métodos** son funciones definidas dentro de una clase que describen los comportamientos o acciones que un objeto puede realizar. Por ejemplo, un jugador puede "anotar un gol" o "presentarse".

```java
public class JugadorFutbol {
    String nombre;
    String posicion;
    int golesAnotados;

    // Método para anotar un gol
    void anotarGol() {
        golesAnotados++;
        System.out.println(nombre + " ha anotado un gol. Total: " + golesAnotados);
    }

    // Método para presentarse
    void presentarse() {
        System.out.println("Soy " + nombre + ", juego como " + posicion + " y he anotado " + golesAnotados + " goles.");
    }
}
```

### 2.3. Encapsulamiento Básico
Para proteger los atributos, es una buena práctica declararlos como `private` y proporcionar métodos `public` (getters y setters) para acceder o modificarlos. Esto se explorará más a fondo en clases posteriores.

<figure markdown="span">
  ![Image title](https://jfinfocesde.github.io/25b1/assets/images/img4.svg){ width="500" }
  <figcaption>Image caption</figcaption>
</figure>

```java
public class JugadorFutbol {
    private String nombre;
    private String posicion;
    private int golesAnotados;

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
}
```

---

## 3. Creación e Instanciación de Objetos

### 3.1. Creación de Objetos
Para crear un objeto, se utiliza la palabra clave `new` seguida del nombre de la clase y paréntesis. Esto instancia un objeto en memoria.

```java
JugadorFutbol jugador1 = new JugadorFutbol(); // Instanciación de un objeto
```

### 3.2. Inicialización de Atributos
Los atributos de un objeto se inicializan asignándoles valores directamente o mediante métodos setters.

```java
jugador1.nombre = "Luis Díaz"; // Asignación directa (si el atributo es público)
jugador1.posicion = "Delantero";
jugador1.golesAnotados = 5;
```

### 3.3. Uso de Métodos
Una vez creado el objeto, se pueden invocar sus métodos para realizar acciones.

```java
jugador1.presentarse(); // Imprime: Soy Luis Díaz, juego como Delantero y he anotado 5 goles.
jugador1.anotarGol(); // Imprime: Luis Díaz ha anotado un gol. Total: 6
```

### 3.4. Ejemplo Completo
El siguiente programa crea dos objetos de la clase `JugadorFutbol` y utiliza sus métodos.

```java
public class Main {
    public static void main(String[] args) {
        // Crear el primer jugador
        JugadorFutbol jugador1 = new JugadorFutbol();
        jugador1.nombre = "Luis Díaz";
        jugador1.posicion = "Delantero";
        jugador1.golesAnotados = 5;

        // Crear el segundo jugador
        JugadorFutbol jugador2 = new JugadorFutbol();
        jugador2.nombre = "Juan Cuadrado";
        jugador2.posicion = "Mediocampista";
        jugador2.golesAnotados = 2;

        // Usar métodos
        jugador1.presentarse();
        jugador1.anotarGol();
        jugador2.presentarse();
    }
}
```

**Salida esperada**:
```
Soy Luis Díaz, juego como Delantero y he anotado 5 goles.
Luis Díaz ha anotado un gol. Total: 6
Soy Juan Cuadrado, juego como Mediocampista y he anotado 2 goles.
```

---
