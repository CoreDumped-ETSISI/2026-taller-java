# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# 7. Tipos Complejos: clases

## 7.1 Clases y objetos

Una clase funciona como una plantilla, y los objetos son instancias creadas a
partir de esa plantilla.

Su definici&oacute;n se compone de atributos (datos) y m&eacute;todos (funciones
y procedimientos espec&iacute;ficos de una **instancia**).

```java
// Class definition
class Dog {
    String name; // Attribute

    // Method
    void bark() {
        System.out.println(name + " says: rawr");
    }
}

// Usage of the class in the main programme (Main)
Dog myDog = new Dog();   // Object instantiation
myDog.name = "Firulais"; // Sets a name for this instance of Dog
myDog.bark();            // Prints "Firulais says: rawr"
```

## 7.2 La clase `String`

A diferencia de `char`, que es primitivo y guarda una sola letra, `String` es
una clase que incorpora m&eacute;todos muy &uacute;tiles.

```java
String greeting = "Hello, Java";

int characterCount = greeting.length();           // 10 (counts characters)
String capitalised = greeting.toUpperCase();      // "HELLO, JAVA"
boolean startsWithHe = greeting.startsWith("He"); // true
```

## 7.3 Clases envoltorio

Las clases envoltorio o "wrapper classes" permiten tratar los tipos primitivos
como objetos.

Todo primitivo cuenta con su clase envoltorio:

- int &rarr; Integer
- double &rarr; Double
- boolean &rarr; Boolean
- char &rarr; Character

```java
// Autoboxing: converting a primitive value into an object
Integer ageObject = 20; 
Double priceObjet = 450.50;

// Wrapper classes have useful methods. For instance, parsing:
String integerAsText = "123";
int actualInteger = Integer.parseInt(integerAsText); // Returns 123 from "123"
```
