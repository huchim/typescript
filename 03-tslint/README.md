# Primer archivo de código

Abrimos [Visual Studio Code](https://code.visualstudio.com/) en la carpeta `tslint` o usamos el siguiente comando:

```bash
cd 03-tslint
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

## TSLint

Quizá te confunda un poco, aún no hemos programado nada, y ya estamos instalando una herramienta llamada [TSLint](https://palantir.github.io/tslint/).

Como en todos los trabajos, hay muchas herramientas, algunas de ellas muy especializadas, y TSLint es una herramienta para que trabajemos mejor.

### ¿Qué hace TSLint?

En pocas palabras, TSLint nos ayuda a escribir nuestro código de manera uniforme, algo que en el futuro lo agradecerán.

Por ejemplo, si todos las variables deben escribirse en algún formato en común o si hay código que no nos serviría.

Esas condiciones se llaman "reglas".

### Instalar

Vamos a hacer uso nuevamente de `npm`, ahora vamos a instalar dos paquetes, el primero será tslint y el segundo será las reglas que usa Microsoft en su proyecto, estaría bien implementarlas igual nosotros.

```bash
npm install tslint
npm install tslint-microsoft-contrib
```

> Podemos agregar el parámetro `--save-dev` para incluirlo como dependencia de desarrollo, pero no está en el ejemplo para no confundir.

> Hay una extensión para VSCode que sirve para mostrar los mensajes de advertencia, es recomendable instalar la [extensión para TSLint](https://marketplace.visualstudio.com/items?itemName=eg2.tslint).

Ahora ejecutemos el siguiente comando (con ayuda de `npx`):

```bash
npx tslint --project ./
```

En el resultado, veremos una fila de 3 errores:

```
ERROR: src/index.ts[1, 5]: expected variable-declaration: 'a' to have a typedef
ERROR: src/index.ts[2, 7]: expected variable-declaration: 'b' to have a typedef
ERROR: src/index.ts[3, 7]: expected variable-declaration: 'c' to have a typedef
```

Abramos nuestro archivo `./src/index.ts` y escribamos `: number` a un lado de cada variable:

```typescript
const a: number = 1;
const b: number = 2;
const c: number = a + b;
```

Y ejecutemos el comando de tslint

```bash
npx tslint --project ./
```

Nuestra salida no mostrará mensajes de error, puede que muestra más información sobre la herramienta, pero los errores que nos aparecieron al principio ya no aparecen.

## Conclusión

Puede que no le encontremos utilidad en este momento, pero es importante que se aprenda antes de poder continuar.

Javascript es un lenguaje donde no se declara el tipo de la variable, si es número o texto; pero en Typescript si se debe declarar el tipo de la variable.

Typescript, al igual que Javascript, no nos obliga a declarar el tipo de variable, y es ahí dónde TSLint nos ayuda a no olvidar declarar el tipo de la variable.

Con el tiempo sabremos que tan importante es declarar el tipo de la variable y cuántos tipos de variable hay.