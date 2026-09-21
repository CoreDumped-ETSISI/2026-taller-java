# Taller de Introducción al Lenguaje de Programación Java

## Índice

1. Variables
    1. Tipos primitivos y convención de nombres
    2. Declaración de variables
2. Operadores
    1. Operadores de condición
    2. Operadores de orden
    3. Operadores lógicos
    4. Operaciones aritméticas
3. Comentarios
4. Imprimir por pantalla
5. Control del flujo
    1. Sentencia condicional (if-else)
    2. Switch
    3. Bucle while
    4. Bucle do-while
    5. Bucle for
6. Funciones
    1. Según su valor de retorno
    2. Según sus parámetros
    3. Métodos estáticos vs. de instancia
8. Tipos complejos: Clases, objetos, Strings y Envoltorias
    1. Clases y Objetos
    2. Clase String
    3. Clases Envoltorias
9. Estructuras de datos

---

# 1. Fundamentos y Sintaxis Básica

## 1.1 Tipos Primitivos y convención de nombres (CamelCase)
En Java, toda variable debe declararse indicando su tipo de dato. Se recomienda utilizar la convención **camelCase** para los nombres.

```java
int edadEstudiante = 20;         // Números enteros
double precioMatricula = 450.50; // Números con decimales
char calificacion = 'A';         // Un solo carácter
boolean esAprobado = true;       // Valores lógicos (true / false)
float ejemploFloat = 12.345f;    // Números con decimales (precisión simple)
```

## 1.2 Declaración de variables
La estructura básica para declarar y asignar un valor es:
tipoDato nombreVariable = valor;

```java
int numeroPokemons;          // Declaración
numeroPokemons = 151;        // Asignación posterior
```

# 2. Operadores
Los operadores en Java son símbolos que nos permiten manipular variables, realizar cálculos y comparar valores para tomar decisiones.

## 2.1 Operadores de Condición (o de Igualdad / Relacionales básicos)
Nos permiten comprobar si dos valores son iguales o diferentes. El resultado de estas operaciones siempre es un booleano (`true` o `false`).

```java
int a = 5;
int b = 10;

boolean sonIguales = (a == b);      // false (¿a es igual a b?)
boolean sonDiferentes = (a != b);   // true  (¿a es diferente de b?)
```

## 2.2 Operadores de Orden (Relacionales)
Se utilizan para comparar magnitudes (mayor, menor, etc.). También devuelven un valor booleano (`true` o `false`).

```java
int edad = 20;

boolean esMayorEdad = (edad >= 18);  // true
boolean esMenorEdad = (edad < 18);   // false
boolean limiteInferior = (edad > 10); // true
boolean limiteSuperior = (edad <= 65); // true
```

## 2.3 Operadores Lógicos
Sirven para conectar varias condiciones o negar expresiones booleanas.

&& (AND / Y): Devuelve true si ambas condiciones se cumplen.<br>
|| (OR / O): Devuelve true si se cumple al menos una de las condiciones.<br>
! (NOT / NO): Invierte el valor booleano (true pasa a false y viceversa).<br>

```java
boolean tieneDinero = true;
boolean tienePermiso = false;

// AND (&&): Ambas deben ser verdaderas
boolean puedeComprar = tieneDinero && tienePermiso; // false

// OR (||): Al menos una debe ser verdadera
boolean puedeEntrar = tieneDinero || tienePermiso;  // true

// NOT (!): Invierte el valor
boolean sinDinero = !tieneDinero; // false
```

## 2.4 Operaciones Aritméticas
Son los operadores matemáticos básicos para realizar cálculos numéricos.

```java
int x = 10;
int y = 3;

int suma = x + y;       // 13
int resta = x - y;      // 7
int multiplicacion = x * y; // 30
int division = x / y;   // 3 (al ser enteros, descarta los decimales)
int resto = x % y;      // 1 (el residuo de dividir 10 entre 3 es 1)
```

# 3. Comentarios
Los comentarios son notas explicativas que el compilador de Java ignora por completo durante la ejecución.

```java
// comentario de una sola línea

/* bloque 
   de comentarios multilínea */
```


# 4. Imprimir por pantalla
Para mostrar información interactiva por consola utilizamos el objeto System.out.

```java
System.out.print("Hola ");       // Imprime sin salto de línea
System.out.println("Mundo!");    // Imprime y hace un salto de línea al final
```

# 5. Control del flujo
## 5.1 Sentencia condicional (if-else)
Permite ejecutar bloques de código dependiendo de si se cumple o no una condición.

```java
int edad = 18;

if (edad >= 18) {
    System.out.println("Eres mayor de edad.");
} else {
    System.out.println("Eres menor de edad.");
}
```

## 5.2 Switch
Útil para evaluar una variable frente a múltiples valores fijos posibles.

```java
int dia = 2;

switch (dia) {
    case 1:
        System.out.println("Lunes");
        break;
    case 2:
        System.out.println("Martes");
        break;
    default:
        System.out.println("Otro día");
        break;
}
```

## 5.3 Bucle while
Ejecuta un bloque de código repetidamente mientras una condición sea verdadera.
```java
int contador = 1;

while (contador <= 3) {
    System.out.println("Contador: " + contador);
    contador++; // bucle infinito!
}
```

## 5.4 Bucle do-while
Similar al while, pero garantiza que el bloque de código se ejecuta al menos una vez antes de evaluar la condición.

```java
int intentos = 0;

do {
    System.out.println("Intentando conectar...");
    intentos++;
} while (intentos < 1);
```

## 5.5 Bucle for
Ideal cuando sabemos de antemano cuántas veces queremos repetir un bloque de instrucciones.

```java
for (int i = 1; i <= 3; i++) {
    System.out.println("Iteración número: " + i);
}
```

# 6. Funciones
Las funciones/métodos permiten agrupar bloques de código reutilizables para evitar duplicidades y organizar mejor el programa.

```java
public class Main {
    // Declaración de una función que suma dos números y retorna el resultado
    public static int sumar(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        // Llamada a la función
        int resultado = sumar(10, 5);
        System.out.println("El resultado es: " + resultado);
    }
}
```

## 6.1 Según su valor de retorno (`void` vs Con retorno)
*   **Métodos `void` (Vacíos):** Realizan una acción (como imprimir por pantalla) pero **no devuelven ningún valor** al finalizar.
*   **Métodos con retorno:** Realizan un cálculo u operación y **devuelven un resultado** utilizando la palabra clave `return` (indicando el tipo de dato que devuelven).

```java
// 1. Método VOID: Solo ejecuta una tarea, no devuelve nada
public static void saludar(String nombre) {
    System.out.println("¡Hola, " + nombre + "!");
}

// 2. Método CON RETORNO: Devuelve un número entero (int)
public static int sumar(int a, int b) {
    return a + b; 
}
```

## 6.2 Según sus parámetros
Sin parámetros: No necesitan ninguna información externa para ejecutarse.<br>

Con parámetros: Requieren que les pases variables o valores específicos entre los paréntesis para poder trabajar con ellos.<br>

```java
// Sin parámetros ni retorno
public static void mostrarCabecera() {
    System.out.println("=== TALLER DE JAVA ===");
}

// Con múltiples parámetros de diferentes tipos
public static void imprimirDatos(String nombre, int edad) {
    System.out.println("Nombre: " + nombre + " | Edad: " + edad);
}
```

## 6.3 Métodos Estáticos (static) vs De Instancia
Métodos Estáticos (`static`): Pertenecen directamente a la clase. Se pueden invocar sin necesidad de crear un objeto (como el método main). Es lo que usamos al principio cuando estamos aprendiendo.<br>

Métodos de Instancia (Sin `static`): Pertenecen a un objeto específico y requieren que primero instancies la clase con new para poder llamarlos (se verá más adelante).<br>

```java
public class Main {
    
    // Método estático (se puede llamar directamente desde el main)
    public static void mensajeEstatico() {
        System.out.println("Soy un método estático.");
    }

    public static void main(String[] args) {
        // Llamada directa al método estático
        mensajeEstatico(); 
    }
}
```


# 7. Tipos Complejos: Clases, objetos, Strings y Envoltorias
## 7.1 Clases y Objetos
Una clase funciona como un "plano" o plantilla, y los objetos son instancias creadas a partir de ese plano.

```java
// Definición de la clase
class Perro {
    String nombre; // Atributo

    // Método
    void ladrar() {
        System.out.println(nombre + " dice: rawr");
    }
}

// Uso en el programa principal (Main)
Perro miPerro = new Perro(); // Creación del objeto
miPerro.nombre = "Firulais";
miPerro.ladrar();            // Imprime: Firulais dice: rawr
```
## 7.2 Clase String
A diferencia de `char` (que es primitivo y guarda una sola letra), `String` es una clase. Por eso sus nombres empiezan con mayúscula y tienen métodos incorporados muy útiles.

```java
String saludo = "Hola, Java";

int cantidadLetras = saludo.length();        // 10 (cuenta caracteres)
String enMayusculas = saludo.toUpperCase();  // "HOLA, JAVA"
boolean empiezaCon = saludo.startsWith("Ho"); // true
```

## 7.3 Clases Envoltorias
Permiten tratar a los tipos primitivos `(int, double, boolean)` como si fueran objetos.
Cada primitivo tiene su clase envoltorio equivalente (con la primera letra en mayúscula)<br>
:int $\rightarrow$ Integer<br>
double $\rightarrow$ Double<br>
boolean $\rightarrow$ Boolean<br>
char $\rightarrow$ Character<br>

```java
// Convertimos un primitivo en un objeto (Autoboxing)
Integer edadObjeto = 20; 
Double precioObjeto = 450.50;

// Tienen métodos útiles, por ejemplo, convertir texto a número:
String numeroTexto = "123";
int numeroReal = Integer.parseInt(numeroTexto); // Convierte "123" a entero 123
```

# 8. Estructuras de datos
## 8.1 Arrays Estáticos
Permiten almacenar múltiples elementos del mismo tipo en una estructura de tamaño fijo. (LOS ÍNDICES EMPIEZAN EN 0 AAA).

```java
String[] frutas = {"Manzana", "Pera", "Plátano"};

System.out.println(frutas[0]); // Muestra "Manzana"
```


## 8.2 ArrayList (Listas Dinámicas)
Estructura muy utilizada en Java cuando el tamaño de los elementos puede variar.
```java
import java.util.ArrayList;

ArrayList<String> nombres = new ArrayList<>();

nombres.add("Ana");     // Añadir elemento
nombres.add("Carlos");

System.out.println(nombres.get(0)); // Obtener elemento: "Ana"
System.out.println("Total: " + nombres.size()); // Tamaño de la lista
```
