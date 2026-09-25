# Taller de Introducci&oacute;n al Lenguaje de Programaci&oacute;n Java

# 2. Operadores

Los operadores en Java son s&iacute;mbolos que nos permiten manipular variables,
realizar c&aacute;lculos y comparar valores para tomar decisiones.

## 2.1 Operadores de condici&oacute;n

> Tambi&eacute;n conocidos como operadores de igualdad o relacionales
b&aacute;sicos.

Se utilizan para comprobar si dos valores son iguales o diferentes. El resultado
de estas operaciones siempre es un valor l&oacute;gico (boolean).

```java
int a = 5;
int b = 10;

boolean equals = (a == b);      // false (Is 'a' equal to 'b'?)
boolean different = (a != b);   // true  (Is 'a' different from 'b'?)
```

## 2.2 Operadores de orden

> Tambi&eacute;n conocidos como operadores relacionales.

Se utilizan para comparar magnitudes (mayor o menor, estrictos o iguales).
Tambi&eacute;n devuelven un valor l&oacute;gico (boolean).

```java
int edad = 20;

boolean isAdult = (edad >= 18);    // true
boolean isUnderage = (edad < 18);  // false
boolean lowerLimit = (edad > 10);  // true
boolean upperLimit = (edad <= 65); // true
```

## 2.3 Operadores l&oacute;gicos

Su prop&oacute;sito es el de concatenar condiciones o negar expresiones
booleanas.

- `&&` (AND): devuelve `true` si ambas condiciones se cumplen.
- `||` (OR): devuelve `true` si se cumple al menos una de las condiciones.
- `!` (NOT): invierte el valor l&oacute;gico (`true` pasa a `false` y
  viceversa).

```java
boolean hasMoney = true;
boolean hasPermission = false;

boolean canBuy = hasMoney && hasPermission;    // false
boolean canAccess = hasMoney || hasPermission; // true
boolean noMoney = !hasMoney;                   // false
```

> [!NOTE]
> Estos operadores se llaman de evaluaci&oacute;n perezosa porque permiten
> evitar evaluar sentencias posteriores si una anterior ha incumplido la
> condici&oacute;n.

## 2.4 Operaciones aritm&eacute;ticas

Son los operadores matem&aacute;ticos b&aacute;sicos para realizar
c&aacute;lculos num&eacute;ricos.

- `+`: suma entera y real.
- `-`: resta entera y real.
- `*`: multiplicaci&oacute;n entera y real.
- `/`: divisi&oacute;n entera y real.
- `%`: operador m&oacute;dulo o resto de la divisi&oacute;n entera.

> [!NOTE]
> Seg&uacute;n los tipos de los operandos, la precisi&oacute;n de los valores
resultantes variar&aacute;.

Ejemplos:

```java
int x = 10;
int y = 3;

int suma = x + y;           // 13
int resta = x - y;          // 7
int multiplicacion = x * y; // 30
int division = x / y;       // 3 (drops the decimals because they're integers)
int resto = x % y;          // 1 (the remainder of 10 over 3 is 1)
```
