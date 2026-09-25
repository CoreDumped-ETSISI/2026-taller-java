# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# 8. Estructuras de datos

## 8.1 Vectores de longitud fija (arrays)

Permiten almacenar m&uacute;ltiples elementos del mismo tipo en una estructura
de tama&ntilde;o fijo.

En Java, los &iacute;ndices de los vectores empiezan por el 0. Es decir, el
primer elemento ser&aacute; el vector[0].

```java
String[] fruits = { "Apple", "Pear", "Banana" };

System.out.println(frutas[0]); // Prints "Apple"
```

## 8.2 `ArrayList` (listas din&aacute;micas)

Estructura muy utilizada en Java cuando el n&uacute;mero de elementos es
variable.

```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<>();

nombres.add("Ann");   // Add an element at the end of the list
nombres.add("Ryuji"); // Add another element to the list

System.out.println(names.get(0));            // Returns the element "Ann"
System.out.println("Size: " + names.size()); // Returns the size of the list
```
