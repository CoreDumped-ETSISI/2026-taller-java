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
7. Tipos complejos: Clases y objetos
8. Estructuras de datos

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


## 1.2 Declaración de variables
La estructura básica para declarar y asignar un valor es:
tipoDato nombreVariable = valor;

```java
int numeroPokemons;          // Declaración
numeroPokemons = 151;        // Asignación posterior


# 2. Operadores
Los operadores en Java son símbolos que nos permiten manipular variables, realizar cálculos y comparar valores para tomar decisiones.

## 2.1 Operadores de Condición (o de Igualdad / Relacionales básicos)
Nos permiten comprobar si dos valores son iguales o diferentes. El resultado de estas operaciones siempre es un booleano (`true` o `false`).

```java
int a = 5;
int b = 10;

boolean sonIguales = (a == b);      // false (¿a es igual a b?)
boolean sonDiferentes = (a != b);   // true  (¿a es diferente de b?)

## 2.2 Operadores de Orden (Relacionales)
Se utilizan para comparar magnitudes (mayor, menor, etc.). También devuelven un valor booleano (true o false).

```java
int edad = 20;

boolean esMayorEdad = (edad >= 18);  // true
boolean esMenorEdad = (edad < 18);   // false
boolean limiteInferior = (edad > 10); // true
boolean limiteSuperior = (edad <= 65); // true

## 2.3 Operadores Lógicos
Sirven para conectar varias condiciones o negar expresiones booleanas.

&& (AND / Y): Devuelve true si ambas condiciones se cumplen.
|| (OR / O): Devuelve true si se cumple al menos una de las condiciones.
! (NOT / NO): Invierte el valor booleano (true pasa a false y viceversa).

```java
boolean tieneDinero = true;
boolean tienePermiso = false;

// AND (&&): Ambas deben ser verdaderas
boolean puedeComprar = tieneDinero && tienePermiso; // false

// OR (||): Al menos una debe ser verdadera
boolean puedeEntrar = tieneDinero || tienePermiso;  // true

// NOT (!): Invierte el valor
boolean sinDinero = !tieneDinero; // false


## 2.4 Operaciones Aritméticas
Son los operadores matemáticos básicos para realizar cálculos numéricos.

+ (Suma)
- (Resta)
* (Multiplicación)
/ (División)
% (Residuo de la división)

```java
int x = 10;
int y = 3;

int suma = x + y;       // 13
int resta = x - y;      // 7
int multiplicacion = x * y; // 30
int division = x / y;   // 3 (al ser enteros, descarta los decimales)
int resto = x % y;      // 1 (el residuo de dividir 10 entre 3 es 1)



7. Tipos complejos: clases y objetos
8. Estructuras de datos
