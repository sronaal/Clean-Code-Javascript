# Buenas Prácticas de Clean Code en JavaScript

El código limpio (Clean Code) es un enfoque en la escritura de código legible, mantenible y escalable. Este documento proporciona lineamientos y ejemplos para aplicar buenas prácticas en JavaScript.

## Índice

1. [Nombres Claros y Descriptivos](#1-nombres-claros-y-descriptivos)
2. [Funciones Simples y Pequeñas](#2-funciones-simples-y-pequeñas)
3. [Evitar la Repetición (DRY)](#3-evitar-la-repetición-dry)
4. [Comentarios útiles y Moderados](#4-comentarios-útiles-y-moderados)
5. [Estructura y Formato Consistentes](#5-estructura-y-formato-consistentes)
6. [Uso Inteligente de Variables](#6-uso-inteligente-de-variables)
7. [Errores y Manejo de Excepciones](#7-errores-y-manejo-de-excepciones)

---

## 1. Nombres Claros y Descriptivos

Los nombres de variables, funciones y clases deben describir claramente su propósito.

### Ejemplo ✔
```javascript
// Bueno
const MAX_USERS = 100;
function calculateTotalPrice(items) {
    return items.reduce((total, item) => total + item.price, 0);
}
```

### Ejemplo ✖
```javascript
// Malo
const x = 100;
function calc(items) {
    return items.reduce((a, b) => a + b.price, 0);
}
```

---

## 2. Funciones Simples y Pequeñas

Cada función debe hacer solo una tarea y hacerlo bien.

### Ejemplo ✔
```javascript
function getUserName(user) {
    return user.name;
}

function getUserAge(user) {
    return user.age;
}
```

### Ejemplo ✖
```javascript
function getUserInfo(user) {
    return `${user.name} is ${user.age} years old`;
}
```

---

## 3. Evitar la Repetición (DRY)

No repitas código innecesariamente; reutiliza funciones y código cuando sea posible.

### Ejemplo ✔
```javascript
function formatDate(date) {
    return new Intl.DateTimeFormat('en-US').format(date);
}

console.log(formatDate(new Date()));
console.log(formatDate(new Date('2024-12-31')));
```

### Ejemplo ✖
```javascript
console.log(new Intl.DateTimeFormat('en-US').format(new Date()));
console.log(new Intl.DateTimeFormat('en-US').format(new Date('2024-12-31')));
```

---

## 4. Comentarios útiles y Moderados

Los comentarios deben explicar **por qué** se hace algo, no **qué** hace el código (eso debe ser evidente).

### Ejemplo ✔
```javascript
// Comprobamos si el usuario tiene permisos antes de continuar
if (user.hasPermission('ADMIN')) {
    performAdminTask();
}
```

### Ejemplo ✖
```javascript
// Comprueba si el usuario tiene permisos de administrador
if (user.hasPermission('ADMIN')) {
    performAdminTask();
}
```

---

## 5. Estructura y Formato Consistentes

Usa una herramienta como [Prettier](https://prettier.io/) o [ESLint](https://eslint.org/) para mantener la consistencia en tu código.

### Ejemplo ✔
```javascript
function greet(name) {
    console.log(`Hello, ${name}!`);
}

greet('Alice');
```

### Ejemplo ✖
```javascript
function greet(name){console.log("Hello, "+name+"!");} greet('Alice')
```

---

## 6. Uso Inteligente de Variables

Declara variables con `const` o `let`, y evita el uso de `var`.

### Ejemplo ✔
```javascript
const name = 'John';
let age = 30;
age += 1;
```

### Ejemplo ✖
```javascript
var name = 'John';
var age = 30;
age += 1;
```

---

## 7. Errores y Manejo de Excepciones

Siempre maneja los errores y proporciona mensajes claros.

### Ejemplo ✔
```javascript
try {
    const data = JSON.parse('invalid JSON');
} catch (error) {
    console.error('Error al parsear JSON:', error.message);
}
```

### Ejemplo ✖
```javascript
const data = JSON.parse('invalid JSON');
```

---

## Recursos Adicionales

- [Clean Code de Robert C. Martin](https://amzn.to/3HZjZpT)
- [Documentación de JavaScript - MDN](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [JavaScript: The Good Parts de Douglas Crockford](https://amzn.to/3IBNchj)

---

## Contribuciones

Las contribuciones son bienvenidas. Si tienes ideas para mejorar este documento, abre un issue o envía un pull request.

---

## Licencia

Este repositorio está bajo la licencia MIT. Consulta el archivo `LICENSE` para más información.
