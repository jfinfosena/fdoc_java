---
title: "Herencia en Java - Ejemplo Exhaustivo: Sistema de Empleados"
position: 9
date: 2025-11-25
---



En esta sección desarrollaremos un ejemplo completo que demuestra todos los conceptos de herencia en Java de manera práctica y detallada.

## Descripción del Sistema

Crearemos un sistema de gestión de empleados que incluye:
- Una clase padre `Empleado` con funcionalidades básicas
- Clases hijas especializadas: `Desarrollador` y `Gerente`
- Métodos específicos para cada tipo de empleado
- Cálculos de salarios y bonificaciones diferenciados

## Implementación Completa

### Clase Padre: Empleado

```java
public class Empleado {
    // Atributos protegidos para acceso desde clases hijas
    protected String nombre;
    protected String apellido;
    protected String cedula;
    protected double salarioBase;
    protected int añosExperiencia;
    protected String departamento;
    
    // Constructor
    public Empleado(String nombre, String apellido, String cedula,
                   double salarioBase, int añosExperiencia, String departamento) {
        this.nombre = nombre;
        this.apellido = apellido;
        this.cedula = cedula;
        this.salarioBase = salarioBase;
        this.añosExperiencia = añosExperiencia;
        this.departamento = departamento;
    }
    
    // Getters
    public String getNombre() {
        return nombre;
    }
    
    public String getApellido() {
        return apellido;
    }
    
    public String getCedula() {
        return cedula;
    }
    
    public double getSalarioBase() {
        return salarioBase;
    }
    
    public int getAñosExperiencia() {
        return añosExperiencia;
    }
    
    public String getDepartamento() {
        return departamento;
    }
    
    // Setters con validaciones
    public void setNombre(String nombre) {
        if (nombre != null && !nombre.trim().isEmpty()) {
            this.nombre = nombre;
        }
    }
    
    public void setApellido(String apellido) {
        if (apellido != null && !apellido.trim().isEmpty()) {
            this.apellido = apellido;
        }
    }
    
    public void setSalarioBase(double salarioBase) {
        if (salarioBase >= 0) {
            this.salarioBase = salarioBase;
        }
    }
    
    public void setAñosExperiencia(int añosExperiencia) {
        if (añosExperiencia >= 0) {
            this.añosExperiencia = añosExperiencia;
        }
    }
    
    public void setDepartamento(String departamento) {
        this.departamento = departamento;
    }
    
    // Métodos de negocio
    public double calcularSalarioTotal() {
        // Salario base + bono por experiencia (5% por año)
        double bonoExperiencia = salarioBase * (añosExperiencia * 0.05);
        return salarioBase + bonoExperiencia;
    }
    
    public double calcularBonoAnual() {
        // Bono anual equivalente a un mes de salario
        return calcularSalarioTotal();
    }
    
    public String obtenerNombreCompleto() {
        return nombre + " " + apellido;
    }
    
    public void mostrarInformacion() {
        System.out.println("=== INFORMACIÓN DEL EMPLEADO ===");
        System.out.println("Nombre: " + obtenerNombreCompleto());
        System.out.println("Cédula: " + cedula);
        System.out.println("Departamento: " + departamento);
        System.out.println("Años de experiencia: " + añosExperiencia);
        System.out.println("Salario base: $" + String.format("%.2f", salarioBase));
        System.out.println("Salario total: $" + String.format("%.2f", calcularSalarioTotal()));
        System.out.println("Bono anual: $" + String.format("%.2f", calcularBonoAnual()));
    }
    
    public boolean esElegibleParaPromocion() {
        // Criterio básico: más de 3 años de experiencia
        return añosExperiencia >= 3;
    }
}
```

### Clase Hija: Desarrollador

```java
public class Desarrollador extends Empleado {
    // Atributos específicos del desarrollador
    private String lenguajePrincipal;
    private int proyectosCompletados;
    private String nivelSenioridad; // Junior, Mid, Senior
    private boolean tieneCertificaciones;
    
    // Constructor
    public Desarrollador(String nombre, String apellido, String cedula,
                        double salarioBase, int añosExperiencia, String departamento,
                        String lenguajePrincipal, int proyectosCompletados,
                        String nivelSenioridad, boolean tieneCertificaciones) {
        super(nombre, apellido, cedula, salarioBase, añosExperiencia, departamento);
        this.lenguajePrincipal = lenguajePrincipal;
        this.proyectosCompletados = proyectosCompletados;
        this.nivelSenioridad = nivelSenioridad;
        this.tieneCertificaciones = tieneCertificaciones;
    }
    
    // Getters específicos
    public String getLenguajePrincipal() {
        return lenguajePrincipal;
    }
    
    public int getProyectosCompletados() {
        return proyectosCompletados;
    }
    
    public String getNivelSenioridad() {
        return nivelSenioridad;
    }
    
    public boolean isTieneCertificaciones() {
        return tieneCertificaciones;
    }
    
    // Setters específicos
    public void setLenguajePrincipal(String lenguajePrincipal) {
        this.lenguajePrincipal = lenguajePrincipal;
    }
    
    public void setProyectosCompletados(int proyectosCompletados) {
        if (proyectosCompletados >= 0) {
            this.proyectosCompletados = proyectosCompletados;
        }
    }
    
    public void setNivelSenioridad(String nivelSenioridad) {
        this.nivelSenioridad = nivelSenioridad;
    }
    
    public void setTieneCertificaciones(boolean tieneCertificaciones) {
        this.tieneCertificaciones = tieneCertificaciones;
    }
    
    // Sobrescritura del método calcularSalarioTotal
    @Override
    public double calcularSalarioTotal() {
        double salarioConExperiencia = super.calcularSalarioTotal();
        
        // Bono por nivel de senioridad
        double bonoSenioridad = 0;
        switch (nivelSenioridad.toLowerCase()) {
            case "junior":
                bonoSenioridad = salarioBase * 0.10; // 10%
                break;
            case "mid":
                bonoSenioridad = salarioBase * 0.25; // 25%
                break;
            case "senior":
                bonoSenioridad = salarioBase * 0.40; // 40%
                break;
        }
        
        // Bono por proyectos completados (2% por proyecto)
        double bonoProyectos = salarioBase * (proyectosCompletados * 0.02);
        
        // Bono por certificaciones
        double bonoCertificaciones = tieneCertificaciones ? salarioBase * 0.15 : 0;
        
        return salarioConExperiencia + bonoSenioridad + bonoProyectos + bonoCertificaciones;
    }
    
    @Override
    public double calcularBonoAnual() {
        double bonoBase = super.calcularBonoAnual();
        
        // Bono adicional por alta productividad
        if (proyectosCompletados >= 10) {
            bonoBase += salarioBase * 0.5; // 50% adicional
        } else if (proyectosCompletados >= 5) {
            bonoBase += salarioBase * 0.25; // 25% adicional
        }
        
        return bonoBase;
    }
    
    // Métodos específicos del desarrollador
    public void completarProyecto() {
        proyectosCompletados++;
        System.out.println(obtenerNombreCompleto() + " ha completado un nuevo proyecto.");
        System.out.println("Total de proyectos: " + proyectosCompletados);
    }
    
    public void actualizarCertificaciones(boolean nuevasCertificaciones) {
        this.tieneCertificaciones = nuevasCertificaciones;
        String estado = nuevasCertificaciones ? "obtenido" : "perdido";
        System.out.println(obtenerNombreCompleto() + " ha " + estado + " certificaciones.");
    }
    
    public double calcularProductividad() {
        // Proyectos por año de experiencia
        return añosExperiencia > 0 ? (double) proyectosCompletados / añosExperiencia : 0;
    }
    
    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("=== INFORMACIÓN ESPECÍFICA DEL DESARROLLADOR ===");
        System.out.println("Lenguaje principal: " + lenguajePrincipal);
        System.out.println("Nivel de senioridad: " + nivelSenioridad);
        System.out.println("Proyectos completados: " + proyectosCompletados);
        System.out.println("Tiene certificaciones: " + (tieneCertificaciones ? "Sí" : "No"));
        System.out.println("Productividad: " + String.format("%.2f", calcularProductividad()) + " proyectos/año");
    }
    
    @Override
    public boolean esElegibleParaPromocion() {
        // Criterios específicos para desarrolladores
        return super.esElegibleParaPromocion() && 
               proyectosCompletados >= 5 && 
               tieneCertificaciones;
    }
}
```

### Clase Hija: Gerente

```java
public class Gerente extends Empleado {
    // Atributos específicos del gerente
    private int equipoACargoTamaño;
    private double presupuestoAnual;
    private int metasCumplidas;
    private int metasTotales;
    private String tipoGerencia; // Operacional, Estratégica, Técnica
    
    // Constructor
    public Gerente(String nombre, String apellido, String cedula,
                  double salarioBase, int añosExperiencia, String departamento,
                  int equipoACargoTamaño, double presupuestoAnual, 
                  int metasCumplidas, int metasTotales, String tipoGerencia) {
        super(nombre, apellido, cedula, salarioBase, añosExperiencia, departamento);
        this.equipoACargoTamaño = equipoACargoTamaño;
        this.presupuestoAnual = presupuestoAnual;
        this.metasCumplidas = metasCumplidas;
        this.metasTotales = metasTotales;
        this.tipoGerencia = tipoGerencia;
    }
    
    // Getters específicos
    public int getEquipoACargoTamaño() {
        return equipoACargoTamaño;
    }
    
    public double getPresupuestoAnual() {
        return presupuestoAnual;
    }
    
    public int getMetasCumplidas() {
        return metasCumplidas;
    }
    
    public int getMetasTotales() {
        return metasTotales;
    }
    
    public String getTipoGerencia() {
        return tipoGerencia;
    }
    
    // Setters específicos
    public void setEquipoACargoTamaño(int equipoACargoTamaño) {
        if (equipoACargoTamaño >= 0) {
            this.equipoACargoTamaño = equipoACargoTamaño;
        }
    }
    
    public void setPresupuestoAnual(double presupuestoAnual) {
        if (presupuestoAnual >= 0) {
            this.presupuestoAnual = presupuestoAnual;
        }
    }
    
    public void setMetasCumplidas(int metasCumplidas) {
        if (metasCumplidas >= 0 && metasCumplidas <= metasTotales) {
            this.metasCumplidas = metasCumplidas;
        }
    }
    
    public void setMetasTotales(int metasTotales) {
        if (metasTotales >= 0) {
            this.metasTotales = metasTotales;
            // Ajustar metas cumplidas si es necesario
            if (metasCumplidas > metasTotales) {
                metasCumplidas = metasTotales;
            }
        }
    }
    
    public void setTipoGerencia(String tipoGerencia) {
        this.tipoGerencia = tipoGerencia;
    }
    
    // Sobrescritura del método calcularSalarioTotal
    @Override
    public double calcularSalarioTotal() {
        double salarioConExperiencia = super.calcularSalarioTotal();
        
        // Bono por tamaño del equipo (2% por cada persona)
        double bonoEquipo = salarioBase * (equipoACargoTamaño * 0.02);
        
        // Bono por tipo de gerencia
        double bonoTipo = 0;
        switch (tipoGerencia.toLowerCase()) {
            case "operacional":
                bonoTipo = salarioBase * 0.20; // 20%
                break;
            case "estratégica":
                bonoTipo = salarioBase * 0.35; // 35%
                break;
            case "técnica":
                bonoTipo = salarioBase * 0.25; // 25%
                break;
        }
        
        // Bono por cumplimiento de metas
        double porcentajeMetas = metasTotales > 0 ? (double) metasCumplidas / metasTotales : 0;
        double bonoMetas = salarioBase * (porcentajeMetas * 0.30); // Hasta 30%
        
        return salarioConExperiencia + bonoEquipo + bonoTipo + bonoMetas;
    }
    
    @Override
    public double calcularBonoAnual() {
        double bonoBase = super.calcularBonoAnual();
        
        // Bono adicional por gestión exitosa
        double porcentajeMetas = metasTotales > 0 ? (double) metasCumplidas / metasTotales : 0;
        if (porcentajeMetas >= 0.9) { // 90% o más de metas cumplidas
            bonoBase += salarioBase * 1.0; // 100% adicional
        } else if (porcentajeMetas >= 0.7) { // 70% o más
            bonoBase += salarioBase * 0.5; // 50% adicional
        }
        
        return bonoBase;
    }
    
    // Métodos específicos del gerente
    public void cumplirMeta() {
        if (metasCumplidas < metasTotales) {
            metasCumplidas++;
            System.out.println(obtenerNombreCompleto() + " ha cumplido una nueva meta.");
            System.out.println("Progreso: " + metasCumplidas + "/" + metasTotales + " metas");
        } else {
            System.out.println("Todas las metas ya han sido cumplidas.");
        }
    }
    
    public void agregarMiembroEquipo() {
        equipoACargoTamaño++;
        System.out.println("Nuevo miembro agregado al equipo de " + obtenerNombreCompleto());
        System.out.println("Tamaño actual del equipo: " + equipoACargoTamaño + " personas");
    }
    
    public double calcularPorcentajeMetas() {
        return metasTotales > 0 ? (double) metasCumplidas / metasTotales * 100 : 0;
    }
    
    public double calcularPresupuestoPorPersona() {
        return equipoACargoTamaño > 0 ? presupuestoAnual / equipoACargoTamaño : 0;
    }
    
    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("=== INFORMACIÓN ESPECÍFICA DEL GERENTE ===");
        System.out.println("Tipo de gerencia: " + tipoGerencia);
        System.out.println("Tamaño del equipo: " + equipoACargoTamaño + " personas");
        System.out.println("Presupuesto anual: $" + String.format("%.2f", presupuestoAnual));
        System.out.println("Metas cumplidas: " + metasCumplidas + "/" + metasTotales);
        System.out.println("Porcentaje de cumplimiento: " + String.format("%.1f", calcularPorcentajeMetas()) + "%");
        System.out.println("Presupuesto por persona: $" + String.format("%.2f", calcularPresupuestoPorPersona()));
    }
    
    @Override
    public boolean esElegibleParaPromocion() {
        // Criterios específicos para gerentes
        return super.esElegibleParaPromocion() && 
               calcularPorcentajeMetas() >= 80.0 && 
               equipoACargoTamaño >= 5;
    }
}
```

## Clase de Demostración Completa

```java
public class SistemaEmpleados {
    public static void main(String[] args) {
        System.out.println("=== SISTEMA DE GESTIÓN DE EMPLEADOS ===");
        System.out.println();
        
        // Crear empleados de diferentes tipos
        Empleado empleadoGeneral = new Empleado(
            "Ana", "García", "12345678", 3000000, 2, "Recursos Humanos"
        );
        
        Desarrollador desarrollador = new Desarrollador(
            "Carlos", "Rodríguez", "87654321", 4500000, 4, "Tecnología",
            "Java", 8, "Mid", true
        );
        
        Gerente gerente = new Gerente(
            "María", "López", "11223344", 8000000, 7, "Operaciones",
            12, 500000000, 7, 10, "Estratégica"
        );
        
        // Mostrar información inicial
        System.out.println("\n=== INFORMACIÓN INICIAL DE EMPLEADOS ===");
        empleadoGeneral.mostrarInformacion();
        System.out.println();
        
        desarrollador.mostrarInformacion();
        System.out.println();
        
        gerente.mostrarInformacion();
        System.out.println();
        
        // Demostrar funcionalidades específicas
        System.out.println("=== DEMOSTRANDO FUNCIONALIDADES ESPECÍFICAS ===");
        
        // Desarrollador completa proyectos
        desarrollador.completarProyecto();
        desarrollador.completarProyecto();
        System.out.println("Nueva productividad: " + 
                          String.format("%.2f", desarrollador.calcularProductividad()) + 
                          " proyectos/año\n");
        
        // Gerente cumple metas
        gerente.cumplirMeta();
        gerente.cumplirMeta();
        gerente.agregarMiembroEquipo();
        System.out.println();
        
        // Verificar elegibilidad para promoción
        System.out.println("=== ELEGIBILIDAD PARA PROMOCIÓN ===");
        System.out.println(empleadoGeneral.obtenerNombreCompleto() + 
                          " elegible: " + empleadoGeneral.esElegibleParaPromocion());
        System.out.println(desarrollador.obtenerNombreCompleto() + 
                          " elegible: " + desarrollador.esElegibleParaPromocion());
        System.out.println(gerente.obtenerNombreCompleto() + 
                          " elegible: " + gerente.esElegibleParaPromocion());
        System.out.println();
        
        // Demostrar polimorfismo
        System.out.println("=== DEMOSTRACIÓN DE POLIMORFISMO ===");
        Empleado[] empleados = {empleadoGeneral, desarrollador, gerente};
        
        double totalSalarios = 0;
        double totalBonos = 0;
        
        for (Empleado emp : empleados) {
            System.out.println("Procesando: " + emp.obtenerNombreCompleto());
            System.out.println("Salario total: $" + String.format("%.2f", emp.calcularSalarioTotal()));
            System.out.println("Bono anual: $" + String.format("%.2f", emp.calcularBonoAnual()));
            
            totalSalarios += emp.calcularSalarioTotal();
            totalBonos += emp.calcularBonoAnual();
            System.out.println();
        }
        
        System.out.println("=== RESUMEN FINANCIERO ===");
        System.out.println("Total salarios mensuales: $" + String.format("%.2f", totalSalarios));
        System.out.println("Total bonos anuales: $" + String.format("%.2f", totalBonos));
        System.out.println("Costo anual total: $" + String.format("%.2f", (totalSalarios * 12) + totalBonos));
        
        // Demostrar uso de setters
        System.out.println("\n=== ACTUALIZANDO INFORMACIÓN ===");
        desarrollador.setSalarioBase(5000000);
        desarrollador.setNivelSenioridad("Senior");
        System.out.println("Nuevo salario del desarrollador: $" + 
                          String.format("%.2f", desarrollador.calcularSalarioTotal()));
        
        gerente.setPresupuestoAnual(600000000);
        System.out.println("Nuevo presupuesto por persona: $" + 
                          String.format("%.2f", gerente.calcularPresupuestoPorPersona()));
    }
}
```

## Características del Ejemplo

**✅ Cumple todos los requisitos:**

- **Herencia completa**: `Desarrollador` y `Gerente` extienden `Empleado`
- **Solo constructores**: No hay métodos abstractos
- **Getters y setters**: Todos los atributos tienen acceso controlado
- **Métodos concretos**: Toda la funcionalidad está implementada
- **Lógica de negocio detallada**: Cálculos de salarios, bonos, productividad
- **Simplicidad**: Código claro y fácil de entender

**🎯 Funcionalidades implementadas:**

- Cálculo de salarios con diferentes criterios por tipo de empleado
- Sistema de bonificaciones específico para cada rol
- Validaciones en setters para mantener integridad de datos
- Polimorfismo para tratar diferentes tipos de empleados uniformemente
- Métricas de rendimiento específicas (productividad, cumplimiento de metas)
- Sistema de elegibilidad para promociones con criterios diferenciados

## Conceptos Demostrados

### 1. Herencia
- Las clases `Desarrollador` y `Gerente` heredan de `Empleado`
- Reutilización de código común en la clase padre
- Especialización en las clases hijas

### 2. Encapsulación
- Atributos privados con acceso controlado
- Validaciones en los setters
- Métodos públicos para interactuar con los objetos

### 3. Polimorfismo
- Mismo método (`calcularSalarioTotal`) con comportamientos diferentes
- Tratamiento uniforme de diferentes tipos de empleados
- Uso de arrays de la clase padre para manejar objetos de clases hijas

### 4. Sobrescritura de Métodos
- `@Override` para claridad en el código
- Llamadas a `super()` para reutilizar funcionalidad del padre
- Extensión del comportamiento base con lógica específica

Este ejemplo demuestra cómo la herencia permite crear sistemas flexibles y mantenibles, donde cada tipo de empleado puede tener su propia lógica de negocio mientras comparte funcionalidades comunes.




