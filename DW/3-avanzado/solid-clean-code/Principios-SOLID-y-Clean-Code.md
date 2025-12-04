# Principios SOLID y Clean Code

## 1. Introducción

### 1.1 Introducción

### 1.2 ¿Cómo funcionará el curso?

### 1.3 ¿Cómo hacer preguntas?

### 1.4 ¿De qué se trata este curso?

### 1.5 Instalaciones necesarias

[Instalaciones recomendadas](https://gist.github.com/Klerith/5bd148b2e16325752219b68995ddf91b)

### 1.6 Principales referencias del curso

El curso cuenta con muchas referencias al libro:

**Clean JavaScript** de Miguel A. Gómez

Pueden comprar el libro si lo desean [aquí](https://cleanjavascript.es/)

IMPORTANTE:

No es necesario comprarlo, es una simple referencia por si quieren mayor información.

**Refactoring Guru:** Khmelnitske shosse  
**Sitio web:** [https://refactoring.guru/](https://refactoring.guru/)

Entre otros sitios web con referencias en las presentaciones que verán un poco más adelante.

### 1.7 Preparación del laboratorio de ejercicios

```bash
git clone git@github.com:Klerith/clean-course.git
mv clean-course clean-solid
```

Si quieres trabajar con `npm` en lugar de `yarn` primero elimina el archivo `yarn.lock`.

```bash
# Run
npm i
```

Cada sección tiene su rama: 

[Clean - SOLID - CodeSmells - Repo](https://github.com/Klerith/clean-course/tree/main)

### 1.8 Nota importante

Importante

Al finalizar el curso, les agradeceré que se tomen unos minutos para responder una corta encuesta y asi poder contar su retroalimentación de lo que les pareció el contenido del curso. Porqué al finalizarlo? Bueno, porque al calificarlo muy temprano o de forma prematura, es muy poco tiempo para tener una idea sobre lo que haremos y aprenderemos en el curso.

Sin más, espero difruten el contenido. 

Gracias!

atte:

Fernando Herrera

### 1.9 ¡Únete a Nuestra Comunidad de DevTalles en Discord!

![](https://files.cdn.thinkific.com/file_uploads/643563/images/c4f/52b/ecc/HOME-BANNER-COMUNIDAD-discord.jpg)

Te invitamos a que formes parte de nuestra comunidad de DevTalles en Discord, un espacio donde tendrás la oportunidad de establecer conexiones con otros estudiantes, compartir y colaborar.

**¿Cómo unirse?**

- Haz clic en el siguiente enlace de invitación: [Comunidad DevTalles](https://discord.gg/pBjEVYTC7t)
- Una vez dentro, cuéntanos un poco de ti en el canal de bienvenida(#presentate).  

Estamos entusiasmados de tener nuevos miembros y crecer juntos como comunidad.

¡Esperamos verte pronto en Discord!

Atentamente,

El equipo de DevTalles

## 2. Clean Code y Deuda técnica

### 2.1 Introducción a la sección

Algo que debemos pagar después...

### 2.2 Temas puntuales de la sección

En esta sección estaremos hablando y haciendo ejercicios sobre:

- ¿Qué es la deuda técnica?  
- ¿Cómo se paga la deuda técnica?  
- Refactorización  
- Nombres de variables  
- Nombres para funciones  
- Ejercicios de refactorización  
- Principio DR

Esta sección procura que empecemos a escribir código que sea fácil de leer por nosotros y otros desarrolladores.

### 2.3 Breve exposición - Deuda técnica y Clean Code

Deuda Técnica

Es la falta de calidad en el código, que genera una deuda que repercutirá en costos futuros.

Costos económicos:

- Tiempo en realizar mantenimientos.
- Tiempo en refactorizar código.
- Tiempo en comprender el código.
- Tiempo adicional en la transferencia del código.

Esquema de deuda técnica de Martin Fowler

- Imprudente: No hay tiempo, solo copia y pega eso de nuevo.
- Inadvertido: ¿Qué son patrones de diseños?
- Prudente: Tenemos que entregar rápido ya refactorizaremos.
- Ahora sabemos cómo lo deberíamos haber hecho.

> Caer en deuda técnica es normal y a menudo es inevitable.

Refactorización

Es simplemente un proceso que tiene como objetivo mejorar el código sin alterar su comportamiento para que sea más entendible y tolerante a cambios.

Usualmente, para que una refactorización fuerte tenga el objetivo esperado, es imprescindible contar con pruebas automáticas.

> "Código Limpio es aquel que se ha escrito con la intención de que otra persona (o tú mismo en el futuro) lo entienda". - Carlos Blé  

> "Nuestro código tiene que ser simple y directo, debería leerse con la misma facilidad que un texto bien escrito". - Grady Booch  

> "Programar es el arte de decirle a otro humano lo que quieres que la computadora haga". - Donald Knuth

### 2.4 Nombres pronunciables y expresivos

Al crear variables:

- Tienen que estar en inglés
- Tienen que ser pronunciables
- Sin guiones bajos
- No ahorrar caracteres

```js
// Bad ❌
const n = 53;
const tx = 0.15;
const cat = 'T-Shirts';
const ddmmyyyy = new Date('August 15, 1965 00:00:00');
```

```js
// Better 👍
const numberOfUnits = 53;
const tax = 0.15;
const category = 'T-Shirts';
const birthDate = new Date('August 15, 1965 00:00:00');
```

```js
// Bad ❌
class AbstractUser {}
class UserMinin {}
class UserImplementation {}
interface UserInterface {}
```

```js
// Better 👍
class User {}
interface User {}
```

#### Ejercicio

```js
(() => {
  // Ejemplo
  // Archivos a evaluar - files to evaluate
  const filesToEvaluate = [
    { id: 1, flagged: false },
    { id: 2, flagged: false },
    { id: 3, flagged: true },
    { id: 4, flagged: false },
    { id: 5, flagged: false },
    { id: 7, flagged: true },
  ];

  // Archivos marcados para borrar - files to delete
  const filesToDelete = filesToEvaluate.map(
    (file) => file.flagged
  );

  // Bad
  class AbstractUser {}
  class UserMixin {}
  class UserImplementation {}
  interface IUser {}

  // Better
  class User {}
  interface User {}

  // Todo: Tarea

  // día de hoy - today
  const today = new Date();

  // días transcurridos - elapsed time in days
  const timeElapsedInDays: number = 23;

  // número de archivos en un directorio - number of files in directory
  const numberOfFilesInDirectory = 33;

  // primer nombre - first name
  const firstName = 'Fernando';

  // primer apellido - last name
  const lastName = 'Herrera';

  // días desde la última modificación - days since modification
  const daysSinceLastModification = 12;

  // cantidad máxima de clases por estudiante - max classes per student
  const maxClassesPerStudent = 6;
})();
```

[01- Ejercicio](https://gist.github.com/Klerith/625ef0d0a501f716ed5e3dbdf88396db)

### 2.5 Nombres según el tipo de dato

Arrays:

```js
// Bad ❌
const fruit = ["apple", "banana", "strawberry"];
```

```js
// Regular 👍
const fruitList = ["apple", "banana", "strawberry"];
```

```js
// Good ✅
const fruits = ["apple", "banana", "strawberry"];
```

```js
// Better 🐦‍🔥
const fruitName = ["apple", "banana", "strawberry"];
```

Booleans:

```js
// Bad ❌
const open = true;
const write = true;
const fruit = true;
const active = false;
const noValues = true;
const notEmpty = true;
```

```js
// Better 🐦‍🔥
const isOpen = true;
const canWrite = true;
const hasFruit = true;
const isActive = false;
const hasValues = false;
const isEmpty = false;
```

Number.

```js
// Bad ❌
const fruits = 3;
const cars = 10;
```

```js
// Better 🐦‍🔥
const maxFruits = 5;
const minFruits = 1;
const totalFruits = 3;
const totalOfCars = 5;
```

Functions:

```js
// Bad ❌
createUserIfNotExists();
updateUserIfNotEmpty();
sendEmailIfFieldsValid();
```

```js
// Better 🐦‍🔥
createUser();
updateUser();
sendEmail();
```

### 2.6 Ejercicio de nombres según tipo

```js
(() => {
  const celsiusTemperatures = [33.6, 12.34];
  const serverIp = '123.123.123.123';

  const users = [
    { id: 1, email: 'fernando@google.com' },
    { id: 2, email: 'juan@google.com' },
    { id: 3, email: 'melissa@google.com' },
  ];

  const userEmails = users.map((user) => user.email);

  const canJump = false;
  const canRun = true;
  const hasItems = true;
  const isLoading = false;

  const startTime = new Date().getTime();
  //....
  // 3 doritos después
  //...
  const endTime = new Date().getTime() - startTime;

  // Funciones
  function getBooks() {
    throw new Error('Function not implemented.');
  }

  function getBooksByUrl(url: string) {
    throw new Error('Function not implemented.');
  }

  function getSquareArea(side: number) {
    throw new Error('Function not implemented.');
  }

  function printJob() {
    throw new Error('Function not implemented.');
  }
})();
```

[02-name-type](https://gist.github.com/Klerith/7599f1637cc683ef59a03fd1c40d53d0)

### 2.7 Consideraciones para las clases

- El nombre es lo más importante de la clase.
- Formados por un sustantivo o frases de sustantivo.
- No deben de ser muy genéricos.
- Usar UpperCamelCase.

3 preguntas para determinar saber si es un buen nombre:

- ¿Qué exactamente hace la clase?
- Cómo exactamente esta clase realiza cierta tarea?
- Hay algo específico sobre su ubicación?

```js
// Bad ❌
class Manager {};
class Data {};
class Info {};
class Individual {};
class Processor {};
class SpecialMonsterView {};
```

Más palabras `!==` mejor nombre.

### 2.8 Nombres de funciones, argumentos y parámetros

Sabemos que estamos desarrollando código limpio cuando cada función hace exactamente lo que su nombre indica.

```js
//     Parameters 👀👇🏻
const sendEmail = (toWhom: string): boolean => {
  // Check email
  if (!toWhom.includes('@')) return false;

  // Body

  // Send email

  // if everything goes well
  return true;
};

// Arguments 👀👇🏻
sendEmail("aleroses@google.com");
```

Se recomienda limitar los parámetros a 3.

### 2.9 Ejercicio con funciones

```js
(() => {
  function getMovieById(id: string) {
    console.log({ id });
  }

  function getMovieCastById(id: string) {
    console.log({ id });
  }

  function getActorBioById(ActorId: string) {
    console.log({ ActorId });
  }

  interface Movie {
    cast: string[];
    description: string;
    rating: number;
    title: string;
  }

  function createMovie({
    title,
    description,
    rating,
    cast,
  }: Movie) {
    console.log({ title, description, rating, cast });
  }

  const checkFullName = (fullName: string): string => {
    return fullName === 'fernando' ? fullName : '';
  };

  function createActor(
    fullName: string,
    birthdate: Date
  ): boolean {
    // tarea asincrona para verificar nombre
    // ..
    // ..
    if (checkFullName(fullName)) return false;

    console.log('Crear actor', birthdate);
    return true;
  }
})();
```

[Ejercicio de funciones](https://gist.github.com/Klerith/d9278895ff5dcacf6f1001d447fb443a)

### 2.10 Detalles adicionales sobre funciones

Otras recomendaciones:

- Simplicidad es fundamental.
- Funciones de tamaño reducido.
- Funciones de una sola línea sin causar complejidad.
- Menos de 20 líneas.
- Evita el uso de "else".
- Prioriza el uso de la condicional ternaria.

```js
// Bad ❌
(() => {
  const getPayAmount = ({
    isDead = false,
    isSeparated = true,
    isRetired = false,
  }) => {
    let result;
    if (isDead) {
      result = 1500;
    } else {
      if (isSeparated) {
        result = 2500;
      } else {
        if (isRetired) {
          result = 3000;
        } else {
          result = 4000;
        }
      }
    }

    return result;
  };
})();
```

```js
// Better 🐦‍🔥
(() => {
  // Continue
  const getPayAmount = ({
    isDead = false,
    isSeparated = true,
    isRetired = false,
  }): number => {
    if (isDead) return 1500;
    if (isSeparated) return 2500;

    // if (isRetired)   return 3000;
    // return 4000;

    return isRetired ? 3000 : 4000;
  };
})();
```

[Función complicada](https://gist.github.com/Klerith/42d6d3a2ce5585d701afc67ca7a4a325)

### 2.11

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

🐦‍🔥
👀👇🏻

### 2.12

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

🐦‍🔥
👀👇🏻

### 2.13

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

🐦‍🔥
👀👇🏻

### 2.14

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

### 2.15

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

### 2.16

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

### 2.17

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```

### 2.18

```js
// Bad ❌
```

```js
// Better 👍

```

```
```

```
```