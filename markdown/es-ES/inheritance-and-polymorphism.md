# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# 10. Herencia y polimorfismo

La **herencia** y el **polimorfismo** son dos de los cuatro pilares
fundamentales de la Programaci&oacute;n Orientada a Objetos (POO). Juntos
permiten reutilizar c&oacute;digo, establecer jerarqu&iacute;as l&oacute;gicas y
dise&ntilde;ar aplicaciones flexibles y escalables.

## 10.1 Herencia (`extends`)

La herencia es un mecanismo que permite a una clase (llamada **clase hija**,
subclase o derivada) heredar los atributos y m&eacute;todos de otra clase
(llamada **clase padre**, superclase o base).

### Caracter&iacute;sticas principales:

- Se utiliza la palabra reservada `extends` para indicar que una clase hereda de
  otra.
- Promueve la **reutilizaci&oacute;n de c&oacute;digo**: el c&oacute;digo
  com&uacute;n se escribe una sola vez en la clase padre.
- En Java, una clase solo puede tener **un &uacute;nico padre directo** (no
  existe herencia m&uacute;ltiple de clases para evitar la ambig&uuml;edad).
- Se puede acceder a los miembros de la clase padre mediante la palabra
  reservada `super`.

### Ejemplo pr&aacute;ctico:

```java
// Parent class (superclass)
public class Animal {
    protected String name;
    protected int age;

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void eat() {
        System.out.println(name + " is eating: *Chomp chomp, wait, is that a stapler?*");
    }
}

// Child class (subclass) inheriting from Animal
public class Dog extends Animal {
    private String breed;

    public Dog(String name, int age, String breed) {
        super(name, age); // Calls the parent class constructor
        this.breed = breed;
    }

    public void bark() {
        System.out.println(name + " is barking: *Meow? I mean... Quack quack!*");
    }
}
```

## 10.2 Polimorfismo

El polimorfismo, que significa literalmente "muchas formas", es la capacidad de
que un mismo m&eacute;todo o mensaje se comporte de manera diferente
seg&uacute;n el objeto sobre el cual se est&eacute; aplicando. Permite tratar a
los objetos de las clases hijas como objetos de la clase padre.

Existen dos tipos principales de polimorfismo:

1. **Polimorfismo en tiempo de compilaci&oacute;n (Sobrecarga / Overloading):**
   M&uacute;ltiples m&eacute;todos con el mismo nombre pero diferentes
   par&aacute;metros dentro de la misma clase.
2. **Polimorfismo en tiempo de ejecuci&oacute;n (Sobrescritura / Overriding):**
   Una clase hija redefine un m&eacute;todo heredado de su clase padre usando la
   anotaci&oacute;n `@Override`.

### Ejemplo pr&aacute;ctico:

```java
// Superclass with a base method
public class MusicalInstrument {
    public void play() {
        System.out.println("Playing a generic instrument: *Dial-up modem connecting noise*");
    }
}

// Subclass 1
public class Guitar extends MusicalInstrument {
    @Override
    public void play() {
        System.out.println("Strumming the guitar: *BEEP BEEP BEEP... The microwave is done!*");
    }
}

// Subclass 2
public class Piano extends MusicalInstrument {
    @Override
    public void play() {
        System.out.println("Playing the piano keys: *MOOOOOOOO!*");
    }
}

// Using polymorphism
public class Main {
    public static void main(String[] args) {
        // A parent class reference can point to child class objects
        MusicalInstrument myInstrument1 = new Guitar();
        MusicalInstrument myInstrument2 = new Piano();

        myInstrument1.play(); // Output: Strumming the guitar: *BEEP BEEP BEEP... The microwave is done!*
        myInstrument2.play(); // Output: Playing the piano keys: *MOOOOOOOO!*
    }
}

```

## 10.3 Resumen

- **Herencia:** Permite construir nuevas clases basadas en clases ya existentes,
  jerarquizando el c&oacute;digo (relaci&oacute;n *"es un"*).
- **Polimorfismo:** Permite escribir c&oacute;digo gen&eacute;rico que puede
  operar con diferentes tipos de objetos de manera uniforme, facilitando
  enormemente el mantenimiento y la extensibilidad del software.
