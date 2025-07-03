# 🚀 Guía Completa de JavaScript

¡Bienvenido a tu viaje de aprendizaje de JavaScript! Esta guía está diseñada especialmente para tu entorno de desarrollo actual.

## 📋 Tabla de Contenidos

1. [Introducción](#introducción)
2. [Configuración de tu Entorno](#configuración-de-tu-entorno)
3. [Fundamentos de JavaScript](#fundamentos-de-javascript)
4. [Conceptos Intermedios](#conceptos-intermedios)
5. [JavaScript Moderno (ES6+)](#javascript-moderno-es6)
6. [Trabajando con Node.js](#trabajando-con-nodejs)
7. [Testing con AVA](#testing-con-ava)
8. [Herramientas de Desarrollo](#herramientas-de-desarrollo)
9. [Proyectos Prácticos](#proyectos-prácticos)
10. [Recursos Adicionales](#recursos-adicionales)

## 🎯 Introducción

JavaScript es el lenguaje de programación más popular del mundo. Se ejecuta en navegadores, servidores (Node.js), aplicaciones móviles y más. Tu proyecto actual ya tiene una configuración profesional con:

- **Node.js**: Runtime de JavaScript
- **Gulp**: Automatización de tareas
- **ESLint**: Análisis de código
- **Prettier**: Formateo automático
- **AVA**: Framework de testing

## ⚙️ Configuración de tu Entorno

Tu entorno ya está configurado, pero veamos cómo usarlo:

```bash
# Instalar dependencias
npm install

# Ejecutar el proyecto
npm start

# Ejecutar tests
npm test

# Formatear código
npm run format

# Verificar código con linter
npm run lint
```

## 📚 Fundamentos de JavaScript

### 1. Variables y Tipos de Datos

```javascript
// Variables (ES6+)
const nombre = "Juan";           // Constante (no se puede reasignar)
let edad = 25;                   // Variable que puede cambiar
var ciudad = "Madrid";           // Forma antigua (evitar)

// Tipos de datos primitivos
let numero = 42;                 // Number
let texto = "Hola mundo";        // String
let esVerdad = true;             // Boolean
let indefinido = undefined;      // Undefined
let nulo = null;                 // Null
let simbolo = Symbol("id");      // Symbol (ES6)
let granNumero = 123n;           // BigInt (ES2020)

// Tipo de dato complejo
let objeto = { nombre: "Ana", edad: 30 };  // Object
let lista = [1, 2, 3, 4, 5];              // Array
```

### 2. Operadores

```javascript
// Aritméticos
let suma = 5 + 3;        // 8
let resta = 10 - 4;      // 6
let multiplicacion = 3 * 4;  // 12
let division = 15 / 3;   // 5
let modulo = 17 % 5;     // 2
let exponente = 2 ** 3;  // 8

// Comparación
console.log(5 == "5");   // true (conversión de tipo)
console.log(5 === "5");  // false (comparación estricta)
console.log(5 != "6");   // true
console.log(5 !== "5");  // true

// Lógicos
let y = true && false;   // false
let o = true || false;   // true
let no = !true;          // false
```

### 3. Estructuras de Control

```javascript
// Condicionales
const edad = 18;

if (edad >= 18) {
    console.log("Eres mayor de edad");
} else if (edad >= 13) {
    console.log("Eres adolescente");
} else {
    console.log("Eres menor de edad");
}

// Switch
const dia = "lunes";
switch (dia) {
    case "lunes":
        console.log("Inicio de semana");
        break;
    case "viernes":
        console.log("¡Por fin viernes!");
        break;
    default:
        console.log("Día normal");
}

// Bucles
for (let i = 0; i < 5; i++) {
    console.log(`Número: ${i}`);
}

const numeros = [1, 2, 3, 4, 5];
for (const numero of numeros) {
    console.log(numero);
}

let contador = 0;
while (contador < 3) {
    console.log(`Contador: ${contador}`);
    contador++;
}
```

### 4. Funciones

```javascript
// Declaración de función
function saludar(nombre) {
    return `Hola, ${nombre}!`;
}

// Expresión de función
const despedir = function(nombre) {
    return `Adiós, ${nombre}!`;
};

// Función flecha (ES6)
const multiplicar = (a, b) => a * b;

// Función con parámetros por defecto
const saludarConDefault = (nombre = "Mundo") => {
    return `Hola, ${nombre}!`;
};

// Ejemplos de uso
console.log(saludar("Ana"));           // "Hola, Ana!"
console.log(multiplicar(4, 5));        // 20
console.log(saludarConDefault());      // "Hola, Mundo!"
```

## 🔄 Conceptos Intermedios

### 1. Arrays y sus Métodos

```javascript
const frutas = ["manzana", "banana", "naranja"];

// Métodos de transformación
const frutasMayusculas = frutas.map(fruta => fruta.toUpperCase());
console.log(frutasMayusculas); // ["MANZANA", "BANANA", "NARANJA"]

// Filtrado
const numeros = [1, 2, 3, 4, 5, 6];
const pares = numeros.filter(num => num % 2 === 0);
console.log(pares); // [2, 4, 6]

// Reducción
const suma = numeros.reduce((total, num) => total + num, 0);
console.log(suma); // 21

// Búsqueda
const encontrado = frutas.find(fruta => fruta === "banana");
const existe = frutas.includes("manzana");
```

### 2. Objetos

```javascript
// Creación de objetos
const persona = {
    nombre: "Carlos",
    edad: 28,
    ciudad: "Barcelona",
    // Método
    presentarse() {
        return `Soy ${this.nombre}, tengo ${this.edad} años`;
    }
};

// Acceso a propiedades
console.log(persona.nombre);        // "Carlos"
console.log(persona["edad"]);       // 28
console.log(persona.presentarse()); // "Soy Carlos, tengo 28 años"

// Destructuring (ES6)
const { nombre, edad } = persona;
console.log(nombre); // "Carlos"

// Spread operator (ES6)
const personaCompleta = {
    ...persona,
    trabajo: "Desarrollador"
};
```

### 3. Clases (ES6)

```javascript
class Animal {
    constructor(nombre, tipo) {
        this.nombre = nombre;
        this.tipo = tipo;
    }
    
    hablar() {
        return `${this.nombre} hace un sonido`;
    }
}

class Perro extends Animal {
    constructor(nombre, raza) {
        super(nombre, "mamífero");
        this.raza = raza;
    }
    
    hablar() {
        return `${this.nombre} ladra: ¡Guau!`;
    }
}

const miPerro = new Perro("Max", "Labrador");
console.log(miPerro.hablar()); // "Max ladra: ¡Guau!"
```

## 🚀 JavaScript Moderno (ES6+)

### 1. Template Literals

```javascript
const nombre = "María";
const edad = 25;

// Forma antigua
const mensaje1 = "Hola, mi nombre es " + nombre + " y tengo " + edad + " años";

// Template literals (ES6)
const mensaje2 = `Hola, mi nombre es ${nombre} y tengo ${edad} años`;

// Multilínea
const html = `
    <div>
        <h1>${nombre}</h1>
        <p>Edad: ${edad}</p>
    </div>
`;
```

### 2. Destructuring

```javascript
// Array destructuring
const colores = ["rojo", "verde", "azul"];
const [primero, segundo, tercero] = colores;

// Object destructuring
const usuario = { id: 1, nombre: "Juan", email: "juan@email.com" };
const { id, nombre, email } = usuario;

// Con alias
const { nombre: nombreUsuario } = usuario;

// Con valores por defecto
const { edad = 18 } = usuario;
```

### 3. Módulos (ES6)

```javascript
// math.js
export const PI = 3.14159;
export const suma = (a, b) => a + b;

export default class Calculadora {
    multiplicar(a, b) {
        return a * b;
    }
}

// main.js
import Calculadora, { PI, suma } from './math.js';
import { PI as CONSTANTE_PI } from './math.js';

const calc = new Calculadora();
console.log(calc.multiplicar(5, 3)); // 15
console.log(suma(2, 3)); // 5
```

### 4. Promises y Async/Await

```javascript
// Promise
const obtenerDatos = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const exito = true;
            if (exito) {
                resolve("Datos obtenidos correctamente");
            } else {
                reject("Error al obtener datos");
            }
        }, 2000);
    });
};

// Usando .then()
obtenerDatos()
    .then(resultado => console.log(resultado))
    .catch(error => console.error(error));

// Usando async/await (ES2017)
const procesarDatos = async () => {
    try {
        const resultado = await obtenerDatos();
        console.log(resultado);
    } catch (error) {
        console.error(error);
    }
};
```

## 📦 Trabajando con Node.js

### 1. Módulos CommonJS (Node.js tradicional)

```javascript
// utils.js
const formatearFecha = (fecha) => {
    return fecha.toISOString().split('T')[0];
};

const calcularEdad = (fechaNacimiento) => {
    const hoy = new Date();
    const nacimiento = new Date(fechaNacimiento);
    return hoy.getFullYear() - nacimiento.getFullYear();
};

module.exports = {
    formatearFecha,
    calcularEdad
};

// app.js
const { formatearFecha, calcularEdad } = require('./utils');

console.log(formatearFecha(new Date())); // "2024-01-15"
console.log(calcularEdad('1990-05-15')); // 34
```

### 2. Trabajando con el Sistema de Archivos

```javascript
const fs = require('fs').promises;
const path = require('path');

// Leer archivo
const leerArchivo = async (rutaArchivo) => {
    try {
        const contenido = await fs.readFile(rutaArchivo, 'utf8');
        return contenido;
    } catch (error) {
        console.error('Error al leer archivo:', error.message);
    }
};

// Escribir archivo
const escribirArchivo = async (rutaArchivo, contenido) => {
    try {
        await fs.writeFile(rutaArchivo, contenido, 'utf8');
        console.log('Archivo escrito correctamente');
    } catch (error) {
        console.error('Error al escribir archivo:', error.message);
    }
};
```

## 🧪 Testing con AVA

Tu proyecto usa AVA para testing. Aquí tienes ejemplos:

```javascript
// tests/math.test.js
const test = require('ava');

// Función simple para testear
const suma = (a, b) => a + b;
const dividir = (a, b) => {
    if (b === 0) throw new Error('División por cero');
    return a / b;
};

// Tests básicos
test('suma dos números correctamente', t => {
    t.is(suma(2, 3), 5);
    t.is(suma(-1, 1), 0);
});

test('división funciona correctamente', t => {
    t.is(dividir(10, 2), 5);
    t.is(dividir(9, 3), 3);
});

test('división por cero lanza error', t => {
    t.throws(() => {
        dividir(10, 0);
    }, { message: 'División por cero' });
});

// Test asíncrono
test('operación asíncrona', async t => {
    const resultado = await new Promise(resolve => {
        setTimeout(() => resolve(42), 100);
    });
    t.is(resultado, 42);
});
```

## 🛠️ Herramientas de Desarrollo

### 1. ESLint (Análisis de Código)

Tu `.eslintrc.js` ayuda a mantener código limpio:

```javascript
// Ejemplo de código que ESLint corregirá
// ❌ Malo
var nombre='Juan'
if(edad>=18){
console.log("Mayor de edad")
}

// ✅ Bueno
const nombre = 'Juan';
if (edad >= 18) {
    console.log('Mayor de edad');
}
```

### 2. Prettier (Formateo Automático)

Prettier formatea automáticamente tu código:

```bash
# Formatear todo el código
npm run format
```

### 3. Gulp (Automatización)

Tu `gulpfile.js` automatiza tareas como:
- Compilación de CSS/LESS
- Minificación de archivos
- Inline de estilos
- Optimización de imágenes

## 💡 Proyectos Prácticos

### Proyecto 1: Calculadora Simple

```javascript
// calculadora.js
class Calculadora {
    sumar(a, b) {
        return a + b;
    }
    
    restar(a, b) {
        return a - b;
    }
    
    multiplicar(a, b) {
        return a * b;
    }
    
    dividir(a, b) {
        if (b === 0) {
            throw new Error('No se puede dividir por cero');
        }
        return a / b;
    }
}

module.exports = Calculadora;

// tests/calculadora.test.js
const test = require('ava');
const Calculadora = require('../calculadora');

const calc = new Calculadora();

test('operaciones básicas', t => {
    t.is(calc.sumar(2, 3), 5);
    t.is(calc.restar(10, 4), 6);
    t.is(calc.multiplicar(3, 4), 12);
    t.is(calc.dividir(15, 3), 5);
});
```

### Proyecto 2: Procesador de Datos

```javascript
// procesador-datos.js
const fs = require('fs').promises;

class ProcesadorDatos {
    async leerCSV(archivo) {
        const contenido = await fs.readFile(archivo, 'utf8');
        const lineas = contenido.split('\n');
        const headers = lineas[0].split(',');
        
        return lineas.slice(1).map(linea => {
            const valores = linea.split(',');
            return headers.reduce((obj, header, index) => {
                obj[header.trim()] = valores[index]?.trim();
                return obj;
            }, {});
        });
    }
    
    filtrarPorEdad(datos, edadMinima) {
        return datos.filter(persona => 
            parseInt(persona.edad) >= edadMinima
        );
    }
    
    async guardarJSON(datos, archivo) {
        const json = JSON.stringify(datos, null, 2);
        await fs.writeFile(archivo, json, 'utf8');
    }
}

module.exports = ProcesadorDatos;
```

## 📖 Ejercicios Recomendados

### Ejercicio 1: Array Methods
```javascript
// Dado el siguiente array, realiza las operaciones:
const estudiantes = [
    { nombre: "Ana", edad: 20, nota: 8.5 },
    { nombre: "Carlos", edad: 22, nota: 7.2 },
    { nombre: "María", edad: 19, nota: 9.1 },
    { nombre: "Luis", edad: 21, nota: 6.8 }
];

// 1. Filtra estudiantes con nota >= 8
// 2. Mapea solo los nombres
// 3. Calcula la nota promedio
// 4. Encuentra el estudiante más joven
```

### Ejercicio 2: Promises y Async/Await
```javascript
// Simula llamadas a API con diferentes tiempos de respuesta
const simularAPI = (datos, tiempo) => {
    return new Promise(resolve => {
        setTimeout(() => resolve(datos), tiempo);
    });
};

// Implementa una función que:
// 1. Haga 3 llamadas simultáneas a diferentes APIs
// 2. Combine los resultados
// 3. Maneje errores apropiadamente
```

## 🎯 Siguiente Pasos

1. **Practica diariamente**: Dedica al menos 30 minutos al día
2. **Construye proyectos**: Aplica lo aprendido en proyectos reales
3. **Lee código**: Explora el código de tu proyecto actual
4. **Contribuye**: Haz mejoras al proyecto existente
5. **Aprende frameworks**: React, Vue, Express.js

## 📚 Recursos Adicionales

### Documentación
- [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [Node.js Docs](https://nodejs.org/docs/latest/api/)
- [AVA Testing](https://github.com/avajs/ava)

### Práctica
- [JavaScript.info](https://javascript.info/)
- [Codewars](https://www.codewars.com/)
- [FreeCodeCamp](https://www.freecodecamp.org/)

### Herramientas
- [Can I Use](https://caniuse.com/) - Compatibilidad de navegadores
- [Babel](https://babeljs.io/) - Transpilación de código
- [Webpack](https://webpack.js.org/) - Bundling de módulos

---

¡Feliz aprendizaje! 🎉 Recuerda que la programación se aprende practicando. Tu entorno ya está configurado, así que puedes empezar a experimentar de inmediato.