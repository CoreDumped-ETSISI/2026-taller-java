# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# Estructuras de control del flujo

## Sentencia condicional (if-else)

Permite ejecutar bloques de c&oacute;digo dependiendo de si se cumple o no una
condici&oacute;n.

```java
int age = 18;

if (age >= 18) {
    System.out.println("You're an adult.");
} else {
    System.out.println("You're underage.");
}
```

## Sentencia de selecci&oacute;n por casos (switch)

&Uacute;til para evaluar una variable frente a m&uacute;ltiples valores fijos
posibles.

```java
int day = 2;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other");
        break;
}
```

## Bucle while

Ejecuta un bloque de c&oacute;digo repetidamente mientras una condici&oacute;n
sea verdadera.

```java
int counter = 1;

while (counter <= 3) {
    System.out.println("Counter: " + counter);
    counter++; // Needed to avoid an infinite loop!
}
```

## Bucle do-while

Similar al while, pero garantiza que el bloque de c&oacute;digo se ejecuta al
menos una vez antes de evaluar la condici&oacute;n.

```java
int tries = 0;

do {
    System.out.println("Trying to connect...");
    tries++;
} while (tries < 1);
```

## Bucle for

Ideal cuando sabemos de antemano cu&aacute;ntas veces queremos repetir un bloque
de instrucciones.

```java
for (int i = 1; i <= 3; i++) {
    System.out.println("Iteration number: " + i);
}
```
