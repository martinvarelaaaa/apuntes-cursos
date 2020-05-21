# TypeScript

Esta son mis notas sobre lo que es [TypeScript](https://www.typescriptlang.org/) y porque me parece que es muy beneficioso utilizarlo.

## ¿Qué es TypeScript?

TypeScript es un superset de JavaScript. Es un lenguaje construido encima de JavaScript.

Agrega algunas features y ventajas a JavaScript. Los navegaores(NodeJS tampoco) no puede ejecutar TypeScript, siempre ejecutan JavaScript.

TypeScript es un poderoso compilador que hace que cuando corramos el código, este compilador convierta el código TypeScript en JavaScript.

En resumen, escribimos en TypeScript, un lenguaje que agrega ventajas y features a JavaScript, que se compila a JavaScript para ejecutarse en los navegadores y NodeJs.

Otra gran ventaja de TS es que el código generado funciona en todos los navegadores, viejos y nuevos, todo eso sin limitarnos a utilizar las últimas funcionalidades de JS.

**¿Cómo hace TypeScript para ser superior a JavaScript si en realidad todo se transforma a JavaScript?**

En realidad lo que sucede, es que TypeScript crea "workarounds" o atajaos en el viejo JavaScript para mejorarlo. Podríamos hacerlo a mano, pero sería muy costoso por no decir imposible.

Nada es magico.

**Una de las features principales que trae TS es que es un lenguaje tipado, a eso se debe su nombre.** Este feature nos permite como desarrolladores poder encontrar o evitar errores mucho antes de que el código este en corriendo en el browser.

### Comparación de JS vs TS

JavaScript

```JavaScript
function add(num1, num2) {
    return num1 + num2;
}

console.log('2','3');
```

Al pasarle dos `Strings` el resultado va a ser `'23'`, pero probablemente la persona que desarrolló la function quizo desarrollar un algortimo que sumara dos `Number`.

TypeScript utiliza estrategias para mitigar estos errores con el chequeo de tipos de variables con los que se llama a una function. Este chequeo se hace en tiempo de compilación y no de runtime, por lo tanto se mitigan los posibles errores.

## Instalación

Para utilizar JavaScript hay que instlarlo, [las instrucciones estan en su página web](https://www.typescriptlang.org/#download-links).

También se puede ejecutar:

```bash
npm install -g typescript
```

Una vez instalado podemos crear un archivo como por ejemplo `using-ts.ts`.

Para utilizar TS recomiendo desarrollar en [Visual Studio Code](https://code.visualstudio.com/). TS y VSC
son dos herramientas desarrolladas por Microsoft y juntas funcionan muy bien.

```TypeScript
const button = document.querySelector("button");
const input1 = document.getElementById("num1")! as HTMLInputElement;
const input2 = document.getElementById("num2")! as HTMLInputElement;

function add(num1: number, num2: number) {
  return num1 + num2;
}

button.addEventListener("click", function () {
  console.log(add(+input1.value, +input2.value));
});
```

El `!` y el `as HTMLInputElement` son para chequear que esa variable nunca puede ser undefined y además es de tipo `HTMLInputElement`.

Los tipos en la function hacen que en el `console.log()` tengamos que convertir los `string` de los `.value` a `number` para que nuestra funcition sume correctamente.

Para compilar este archivo y convertirlo a JS simplemente hay que ejecutar `tsc nombre-archivo.ts`, eso generará un archivo de nombre `nombre-archivo.js`.

En resumen, TS nos fuerza a escribir código limpio y menos propenso a errores, sobre todo por problemas de tipado.
