---
title: "Interfaces en Java"
position: 11
date: 2025-11-25
---

## 📚 ¿Qué es una Interfaz?

Una **interfaz** en Java es un contrato que define qué métodos debe implementar una clase, pero no especifica cómo implementarlos. Es como un "acuerdo" o "promesa" que una clase hace sobre qué comportamientos va a proporcionar.

### 🔍 Características Principales

- **Contrato de comportamiento**: Define QUÉ debe hacer una clase, no CÓMO
- **Abstracción pura**: Todos los métodos son abstractos por defecto (hasta Java 8)
- **Implementación múltiple**: Una clase puede implementar varias interfaces
- **Sin estado**: No pueden tener variables de instancia (solo constantes)
- **Herencia múltiple de comportamiento**: Permite simular herencia múltiple

### 🌟 Analogía del Mundo Real

Imagina una **licencia de conducir**:
- La licencia es como una interfaz que dice "esta persona puede conducir"
- No importa si conduces un carro, moto o camión (diferentes implementaciones)
- Todos los conductores deben saber acelerar, frenar y girar (métodos obligatorios)
- Cada vehículo implementa estos comportamientos de manera diferente

```java
// La "licencia" sería nuestra interfaz
interface Conductor {
    void acelerar();
    void frenar();
    void girar(String direccion);
}
```

---

## 🛠️ Declaración de una Interfaz

### Sintaxis Básica

```java
[modificador] interface NombreInterfaz {
    // Constantes (implícitamente public, static, final)
    tipo CONSTANTE = valor;
    
    // Métodos abstractos (implícitamente public y abstract)
    tipoRetorno nombreMetodo(parametros);
}
```

### 📝 Ejemplo Básico

```java
public interface Vehiculo {
    // Constante - velocidad máxima permitida
    int VELOCIDAD_MAXIMA = 120;
    
    // Métodos abstractos que deben implementar las clases
    void encender();
    void apagar();
    void acelerar(int velocidad);
    void frenar();
    String obtenerTipo();
}
```

### 🎨 Ejemplo con Múltiples Métodos

```java
public interface Reproductor {
    // Constantes
    int VOLUMEN_MAXIMO = 100;
    int VOLUMEN_MINIMO = 0;
    
    // Métodos que debe implementar cualquier reproductor
    void reproducir();
    void pausar();
    void detener();
    void siguienteCancion();
    void cancionAnterior();
    void ajustarVolumen(int volumen);
    boolean estaReproduciendo();
}
```

### ⚡ Características de los Métodos en Interfaces

```java
public interface EjemploCaracteristicas {
    // ❌ INCORRECTO - no puede tener variables de instancia
    // private String nombre;
    
    // ✅ CORRECTO - constantes (public static final implícito)
    String TIPO_DEFECTO = "Genérico";
    int NUMERO_MAXIMO = 1000;
    
    // ✅ CORRECTO - métodos abstractos (public abstract implícito)
    void metodoAbstracto();
    String obtenerInformacion();
    
    // ❌ INCORRECTO - no puede tener constructores
    // public EjemploCaracteristicas() { }
}
```

---

## 🔧 Implementación de una Interfaz - Uso de `implements`

### Sintaxis de Implementación

```java
public class NombreClase implements NombreInterfaz {
    // Debe implementar TODOS los métodos de la interfaz
    @Override
    public tipoRetorno nombreMetodo(parametros) {
        // Implementación específica
    }
}
```

### 📱 Ejemplo Práctico: Sistema de Dispositivos

```java
// 1. Declaramos la interfaz
public interface DispositivoElectronico {
    String MARCA_DEFECTO = "Genérica";
    
    void encender();
    void apagar();
    void mostrarEstado();
    int obtenerConsumoEnergia();
}

// 2. Implementamos la interfaz en diferentes clases
public class Telefono implements DispositivoElectronico {
    private boolean encendido;
    private String modelo;
    private int bateria;
    
    public Telefono(String modelo, int bateria) {
        this.modelo = modelo;
        this.bateria = bateria;
        this.encendido = false;
    }
    
    @Override
    public void encender() {
        if (bateria > 0) {
            encendido = true;
            System.out.println("📱 Teléfono " + modelo + " encendido");
        } else {
            System.out.println("❌ Batería agotada, no se puede encender");
        }
    }
    
    @Override
    public void apagar() {
        encendido = false;
        System.out.println("📱 Teléfono " + modelo + " apagado");
    }
    
    @Override
    public void mostrarEstado() {
        String estado = encendido ? "Encendido" : "Apagado";
        System.out.println("📱 " + modelo + " - Estado: " + estado + " - Batería: " + bateria + "%");
    }
    
    @Override
    public int obtenerConsumoEnergia() {
        return encendido ? 15 : 2; // Watts
    }
    
    // Método específico del teléfono
    public void llamar(String numero) {
        if (encendido) {
            System.out.println("📞 Llamando a " + numero);
        } else {
            System.out.println("❌ Enciende el teléfono primero");
        }
    }
}

public class Laptop implements DispositivoElectronico {
    private boolean encendida;
    private String marca;
    private String procesador;
    
    public Laptop(String marca, String procesador) {
        this.marca = marca;
        this.procesador = procesador;
        this.encendida = false;
    }
    
    @Override
    public void encender() {
        encendida = true;
        System.out.println("💻 Laptop " + marca + " iniciando sistema...");
        System.out.println("💻 Sistema operativo cargado");
    }
    
    @Override
    public void apagar() {
        encendida = false;
        System.out.println("💻 Cerrando aplicaciones...");
        System.out.println("💻 Laptop " + marca + " apagada");
    }
    
    @Override
    public void mostrarEstado() {
        String estado = encendida ? "Encendida" : "Apagada";
        System.out.println("💻 " + marca + " (" + procesador + ") - Estado: " + estado);
    }
    
    @Override
    public int obtenerConsumoEnergia() {
        return encendida ? 65 : 5; // Watts
    }
    
    // Método específico de la laptop
    public void ejecutarPrograma(String programa) {
        if (encendida) {
            System.out.println("💻 Ejecutando " + programa);
        } else {
            System.out.println("❌ Enciende la laptop primero");
        }
    }
}
```

### 🎮 Ejemplo de Uso

```java
public class PruebaDispositivos {
    public static void main(String[] args) {
        // Crear dispositivos
        Telefono miTelefono = new Telefono("iPhone 15", 85);
        Laptop miLaptop = new Laptop("Dell", "Intel i7");
        
        // Usar como objetos específicos
        System.out.println("=== USO ESPECÍFICO ===");
        miTelefono.encender();
        miTelefono.llamar("123-456-7890");
        
        miLaptop.encender();
        miLaptop.ejecutarPrograma("Visual Studio Code");
        
        // Usar polimorfismo con la interfaz
        System.out.println("\n=== POLIMORFISMO ===");
        DispositivoElectronico[] dispositivos = {miTelefono, miLaptop};
        
        for (DispositivoElectronico dispositivo : dispositivos) {
            dispositivo.mostrarEstado();
            System.out.println("Consumo: " + dispositivo.obtenerConsumoEnergia() + "W");
            System.out.println("Marca por defecto: " + DispositivoElectronico.MARCA_DEFECTO);
            System.out.println("---");
        }
        
        // Apagar todos los dispositivos
        System.out.println("=== APAGANDO DISPOSITIVOS ===");
        for (DispositivoElectronico dispositivo : dispositivos) {
            dispositivo.apagar();
        }
    }
}
```

---

## 🔄 Implementación Múltiple

Una de las grandes ventajas de las interfaces es que una clase puede implementar múltiples interfaces.

### 📚 Ejemplo: Sistema de Biblioteca

```java
// Interfaces separadas para diferentes comportamientos
public interface Prestable {
    void prestar(String usuario);
    void devolver();
    boolean estaPrestado();
}

public interface Catalogable {
    String obtenerCodigo();
    String obtenerCategoria();
    void actualizarUbicacion(String nuevaUbicacion);
}

public interface Renovable {
    void renovar();
    boolean puedeRenovarse();
    int diasRestantes();
}

// Clase que implementa múltiples interfaces
public class Libro implements Prestable, Catalogable, Renovable {
    private String titulo;
    private String autor;
    private String codigo;
    private String categoria;
    private String ubicacion;
    private boolean prestado;
    private String usuarioPrestamo;
    private int diasPrestamo;
    
    public Libro(String titulo, String autor, String codigo, String categoria) {
        this.titulo = titulo;
        this.autor = autor;
        this.codigo = codigo;
        this.categoria = categoria;
        this.ubicacion = "Estantería Principal";
        this.prestado = false;
        this.diasPrestamo = 0;
    }
    
    // Implementación de Prestable
    @Override
    public void prestar(String usuario) {
        if (!prestado) {
            prestado = true;
            usuarioPrestamo = usuario;
            diasPrestamo = 14; // 2 semanas
            System.out.println("📖 '" + titulo + "' prestado a " + usuario);
        } else {
            System.out.println("❌ El libro ya está prestado");
        }
    }
    
    @Override
    public void devolver() {
        if (prestado) {
            prestado = false;
            System.out.println("📖 '" + titulo + "' devuelto por " + usuarioPrestamo);
            usuarioPrestamo = null;
            diasPrestamo = 0;
        } else {
            System.out.println("❌ El libro no está prestado");
        }
    }
    
    @Override
    public boolean estaPrestado() {
        return prestado;
    }
    
    // Implementación de Catalogable
    @Override
    public String obtenerCodigo() {
        return codigo;
    }
    
    @Override
    public String obtenerCategoria() {
        return categoria;
    }
    
    @Override
    public void actualizarUbicacion(String nuevaUbicacion) {
        this.ubicacion = nuevaUbicacion;
        System.out.println("📍 Ubicación actualizada: " + nuevaUbicacion);
    }
    
    // Implementación de Renovable
    @Override
    public void renovar() {
        if (prestado && puedeRenovarse()) {
            diasPrestamo += 7; // Una semana más
            System.out.println("🔄 Préstamo renovado. Nuevos días: " + diasPrestamo);
        } else {
            System.out.println("❌ No se puede renovar");
        }
    }
    
    @Override
    public boolean puedeRenovarse() {
        return prestado && diasPrestamo <= 7; // Solo si quedan pocos días
    }
    
    @Override
    public int diasRestantes() {
        return prestado ? diasPrestamo : 0;
    }
    
    // Método específico del libro
    public void mostrarInformacion() {
        System.out.println("📚 " + titulo + " por " + autor);
        System.out.println("   Código: " + codigo + " | Categoría: " + categoria);
        System.out.println("   Ubicación: " + ubicacion);
        if (prestado) {
            System.out.println("   Prestado a: " + usuarioPrestamo + " | Días restantes: " + diasPrestamo);
        } else {
            System.out.println("   Estado: Disponible");
        }
    }
}
```

### 🧪 Prueba del Sistema

```java
public class PruebaBiblioteca {
    public static void main(String[] args) {
        Libro libro = new Libro("Cien Años de Soledad", "Gabriel García Márquez", "LIT001", "Literatura");
        
        // Mostrar información inicial
        libro.mostrarInformacion();
        
        // Probar funcionalidades de Prestable
        System.out.println("\n=== PRÉSTAMO ===");
        libro.prestar("Juan Pérez");
        libro.mostrarInformacion();
        
        // Probar funcionalidades de Catalogable
        System.out.println("\n=== CATALOGACIÓN ===");
        System.out.println("Código: " + libro.obtenerCodigo());
        System.out.println("Categoría: " + libro.obtenerCategoria());
        libro.actualizarUbicacion("Sección Préstamos");
        
        // Probar funcionalidades de Renovable
        System.out.println("\n=== RENOVACIÓN ===");
        System.out.println("¿Puede renovarse? " + libro.puedeRenovarse());
        System.out.println("Días restantes: " + libro.diasRestantes());
        libro.renovar();
        
        // Devolver el libro
        System.out.println("\n=== DEVOLUCIÓN ===");
        libro.devolver();
        libro.mostrarInformacion();
    }
}
```

---

## 🎯 Ventajas de las Interfaces

### 1. **Flexibilidad en el Diseño**
```java
// Diferentes implementaciones de la misma interfaz
interface Notificacion {
    void enviar(String mensaje);
}

class NotificacionEmail implements Notificacion {
    public void enviar(String mensaje) {
        System.out.println("📧 Email: " + mensaje);
    }
}

class NotificacionSMS implements Notificacion {
    public void enviar(String mensaje) {
        System.out.println("📱 SMS: " + mensaje);
    }
}

class NotificacionPush implements Notificacion {
    public void enviar(String mensaje) {
        System.out.println("🔔 Push: " + mensaje);
    }
}
```

### 2. **Polimorfismo Poderoso**
```java
public class ServicioNotificaciones {
    public void enviarNotificacion(Notificacion notificacion, String mensaje) {
        notificacion.enviar(mensaje); // No importa qué tipo específico sea
    }
    
    public static void main(String[] args) {
        ServicioNotificaciones servicio = new ServicioNotificaciones();
        
        // Mismo método, diferentes comportamientos
        servicio.enviarNotificacion(new NotificacionEmail(), "Bienvenido!");
        servicio.enviarNotificacion(new NotificacionSMS(), "Código: 1234");
        servicio.enviarNotificacion(new NotificacionPush(), "Nueva actualización");
    }
}
```

### 3. **Desacoplamiento de Código**
```java
// ❌ MALO - Acoplado a implementación específica
class ProcesadorPagos {
    private PayPal paypal = new PayPal();
    
    public void procesar(double monto) {
        paypal.pagar(monto); // Solo funciona con PayPal
    }
}

// ✅ BUENO - Desacoplado usando interfaz
interface ProcesadorPago {
    void procesar(double monto);
}

class ProcesadorPagosFlexible {
    private ProcesadorPago procesador;
    
    public ProcesadorPagosFlexible(ProcesadorPago procesador) {
        this.procesador = procesador;
    }
    
    public void procesar(double monto) {
        procesador.procesar(monto); // Funciona con cualquier implementación
    }
}
```

---

## 🏋️ Ejercicios Prácticos

### Ejercicio 1: Sistema de Formas Geométricas
```java
// Crea una interfaz y implementaciones
interface Forma {
    double calcularArea();
    double calcularPerimetro();
    void dibujar();
}

// Implementa para: Círculo, Rectángulo, Triángulo
```

### Ejercicio 2: Sistema de Empleados
```java
// Crea interfaces para diferentes roles
interface Trabajador {
    void trabajar();
    double calcularSalario();
}

interface Supervisor {
    void supervisar();
    void asignarTarea(String tarea);
}

// Implementa: Desarrollador, Gerente (que es Trabajador y Supervisor)
```

### Ejercicio 3: Sistema de Vehículos
```java
interface Vehiculo {
    void acelerar();
    void frenar();
    int obtenerVelocidadMaxima();
}

interface Volador {
    void despegar();
    void aterrizar();
    int obtenerAltitudMaxima();
}

// Implementa: Carro, Avión (que es Vehiculo y Volador)
```

---

## ✅ Mejores Prácticas

### 1. **Nombres Descriptivos**
```java
// ✅ BUENO
interface Reproducible {
    void reproducir();
}

// ❌ MALO
interface I {
    void r();
}
```

### 2. **Interfaces Cohesivas**
```java
// ✅ BUENO - Una responsabilidad clara
interface Calculadora {
    double sumar(double a, double b);
    double restar(double a, double b);
}

// ❌ MALO - Múltiples responsabilidades
interface CalculadoraYBaseDatos {
    double sumar(double a, double b);
    void guardarEnBaseDatos(String datos);
}
```

### 3. **Usar Constantes Apropiadamente**
```java
interface ConfiguracionJuego {
    int VIDAS_INICIALES = 3;
    int PUNTOS_POR_NIVEL = 100;
    String VERSION = "1.0";
    
    void iniciarJuego();
    void terminarJuego();
}
```