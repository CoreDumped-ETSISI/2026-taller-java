# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# Clases abstractas e interfaces

En la programaci&oacute;n orientada a objetos (POO), tanto las **clases
abstractas** como las **interfaces** son mecanismos que permiten definir
contratos y lograr el polimorfismo. Sin embargo, tienen prop&oacute;sitos y
reglas de dise&ntilde;o diferentes.

## Clases abstractas (`abstract class`)

Una clase abstracta es una clase que **no se puede instanciar directamente**. Su
objetivo principal es servir como una **plantilla o base** para otras clases
hijas (subclases).

### Caracter&iacute;sticas principales:

- Se declaran con la palabra reservada `abstract`.
- Pueden contener **m&eacute;todos abstractos** (sin cuerpo, terminados en punto
  y coma) que obligatoriamente deben implementar las clases hijas.
- Pueden contener **m&eacute;todos concretos** (con c&oacute;digo implementado)
  que las hijas heredan directamente.
- Pueden tener atributos de cualquier tipo, constructores y m&eacute;todos
  est&aacute;ticos.

### Ejemplo pr&aacute;ctico:

```java
// Abstract class
public abstract class Vehicle {
    protected String brand;

    // Constructor
    public Vehicle(String brand) {
        this.brand = brand;
    }

    // Concrete method (shared)
    public void start() {
        System.out.println("The " + brand + " vehicle is booting up with the classic Windows 95 startup sound...");
    }

    // Abstract method (mandatory for subclasses to implement)
    public abstract void accelerate();
}

// Concrete class extending the abstract class
public class Car extends Vehicle {
    public Car(String brand) {
        super(brand);
    }

    @Override
    public void accelerate() {
        System.out.println("The " + brand + " car accelerates by aggressively yelling 'SPEED UP' into the steering wheel.");
    }
}
```

## Interfaces (`interface`)

Una interfaz es un **contrato de comportamiento**. Define *qu&eacute;* debe hacer una clase, pero no *c&oacute;mo* debe hacerlo. Representa una capacidad o rol que una clase puede adoptar.

### Caracter&iacute;sticas principales:

- Se declaran con la palabra reservada `interface`.
- Todos sus m&eacute;todos son, por defecto, `public abstract` (a partir de Java 8 se permiten m&eacute;todos `default` y `static` con implementaci&oacute;n).
- Todos sus atributos son, por defecto, `public static final` (constantes).
- Una clase **puede implementar m&uacute;ltiples interfaces**, solucionando la limitaci&oacute;n de Java de no permitir herencia m&uacute;ltiple de clases.

### Ejemplo pr&aacute;ctico:

```java
// Interface definition
public interface Drivable {
    void drive(); // public abstract implicit
    
    default void honkHorn() {
        System.out.println("Squeak squeak! (It's a rubber duck stuck in the horn).");
    }
}

// Class implementing the interface
public class Bicycle implements Drivable {
    @Override
    public void drive() {
        System.out.println("Riding the bicycle while dramatically reciting Shakespearean tragedy.");
    }
}
```

## Diferencias clave (tabla comparativa)

| Caracter&iacute;stica | Clase abstracta                                                                       | Interfaz                                                                          |
|-----------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| Herencia              | Una clase solo puede extender **una** clase abstracta (`extends`).                    | Una clase puede implementar **m&uacute;ltiples** interfaces (`implements`).       |
| M&eacute;todos        | Puede tener m&eacute;todos abstractos y con implementaci&oacute;n (concretos).        | Principalmente m&eacute;todos abstractos (y `default`/`static` desde Java 8+).    |
| Atributos             | Puede tener variables de instancia de cualquier tipo (privadas, protegidas, etc.).    | Solo constantes p&uacute;blicas (`public static final`).                          |
| Constructores         | **S&iacute;** tiene constructores (&uacute;tiles para inicializar estados heredados). | **No** tiene constructores.                                                       |
| Prop&oacute;sito      | Relaci&oacute;n de parentesco estricta ("es un" tipo de).                             | Definici&oacute;n de capacidades o comportamientos transversales ("puede hacer"). |

## &iquest;Cu&aacute;ndo usar cada una? (Regla de oro para el taller)

- **Usa una clase abstracta cuando:**
  - Compartas c&oacute;digo com&uacute;n (atributos y m&eacute;todos con estado) entre clases estrechamente relacionadas.
  - Necesites usar constructores o mantener un estado interno (variables de instancia no constantes).

- **Usa una interfaz cuando:**
  - Quieras definir un comportamiento com&uacute;n para clases que no est&aacute;n relacionadas jer&aacute;rquicamente (ej. `Imprimible`, `Serializable`, `Comparable`).
  - Necesites simular **herencia m&uacute;ltiple** permitiendo que una clase cumpla varios contratos.
