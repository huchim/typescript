# Primer archivo de código

Abrimos [Visual Studio Code](https://code.visualstudio.com/) en la carpeta `primer-script` o usamos el siguiente comando:

```bash
cd 02-primer-script
code .
```
## Instalar paquetes

Antes de continuar, debemos correr el siguiente comando:

```bash
npm install
```

Los paquetes dentro de la carpeta `node_modules` no suelen enviarse a un repositorio de código como este, es por eso que necesitamos instalarlos nuevamente.

Como en el tema anterior lo creamos, no necesitamos definir nuevamente todos los paquetes. Conforme vayamos instalando los paquetes, estos se irán agregando a esos dos archivos.

En la carpeta, verás un archivo adicional, llamado: `package-lock.json`, este también es importante, básicamente ayuda a que la instalación de paquetes sea más rápida, y cuidando de las versiones entre los paquetes.

## Crear un archivo

Hay 3 tipos de archivos en Typescript:

* Archivo de código: `index.ts`
* Archivo de declaraciones: `index.d.ts`
* Archivo TSX (una mezcla de JS y JSX que veremos más adelante):  `index.tsx`

Nuestro primer archivo será un archivo de código.

Para aquellos que hayan trabajando con Javascript, un archivo `index.ts` sería igual a un archivo de javascript `index.js`.

Bueno pues, creamo sun archivo llamado `index.ts` dentro de la carpeta `./src`. Una vez creado, vamos a poner el siguiente código:

```javascript
var a = 1;
var b = 2;
var c = a + b;
```

Luego en la terminal ([¿cómo abrir la terminal?](../01-primeros-pasos)) vamos a ejecutar el siguiente comando:

```bash
npx tsc
```

## Transpilación

Cuando ejecutamos Typescript, este convierte nuestros archivos `*.ts` en archivos `*.js`, los archivos de Javascript son los que funcionarán en nuestra aplicación.

Este cambio de Typescript a javascript, es lo que hace `tsc`. Este tipo de conversión, se llama "transpilación", la palabra es un juego de palabra entre "**trans**formación" y "com**pilación**". La compilación es el proceso donde se convierte el código en un programa ejecutable.

Observa el código nuevo generado (`src/index.js`):

```javascript
var a = 1;
var b = 2;
var c = a + b;
```

Como verás no ha diferencias.

Si no hay diferencias, entonces ¿para que sirve?.

## ES6

Se puede decir que cuando hablamos de ES6, estamos hablando de la versión de Javascript, y como muchos programas o lenguajes, estos se van mejorando con el tiempo.

Básicamente hay dos versiones que debemos tener en cuenta:

* ES5 (2012 en adelante)
* ES6 (2017 en adelante)
* ES7 (aún en desarrollo)

La versión actual es ES6, pero aún puede haber lugares donde no funcione, y solo funcione ES5.

Typescript, nos permite escribir código que funcione en las 3 versiones y si abrimos nuestro archivo `tsconfig.json`, podemos ver que hay una opción llamada :

```json
{
    "compilerOptions": {
        "target": "es5"
    }
}
```

Eso significa que Typescript, convertirá nuestros archivos en Javascript ES5 válido.

Modifiquemos un poco nuestro archivo `src/index.ts`

```javascript
const a = 1;
const b = 2;
const c = a + b;
```

Volvamos a ejecutar Typescript (ayudandonos del comando `npx`):

```bash
npx tsc
```

Y abramos el archivo `src/index.js` para ver su contenido:

```javascript
var a = 1;
var b = 2;
var c = a + b;
```

Como podrás observar, es aquí donde si hay un cambio con respecto al código de origen `src/index.ts`

```diff
- const a = 1;
+ var a = 1;
```

La palabra `const` (constante) no es compatible en Javascript ES5, pero Typescript, la convierte automáticamente en `var` (variable). En ES6 si es compatible, pero la ventaja de Typescript es esa, automáticamente hace los cambios de código de acuerdo a la versión destino (`target`) que definamos.

> Puedes modificar el `target` en el archivo `tsconfig.json`, ponerle `es6` y volver a ejecutar Typescript. Podrás ver que ahora si está la palabra `const`.

## Conclusión

Por ahora hemos terminado, hemos explicado un poco sobre la conversión de Typescript a Javascript en sus versiones ES5 y ES6.

Le agregaremos más código a la aplicación en el siguiente tema.

