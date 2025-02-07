# Estrategia de pruebas para el juego adivina tu numero creada por Jhoanna Mishell Castellanos Morales

- Error: la funcion Math.random generaba valores del 1 al 10 en lugar del 1 al 100. Esto no permitia al usuario ingresar valores del 1 al 100

-Correccion: Se ajusto la formula para asegurarse de que los numeros generados estuvieran dentro del rango establecido.

**let randomNumber = Math.floor(Math.random() * 100) + 1;**

-Error: En document.querySelector('lowOrHi'); faltaba un punto (.) antes del nombre de la clase, lo que impedía el funcionamiento correcto de la selección.

-Corrección: Se agregó el punto faltante para asegurar la selección correcta

**const lowOrHi = document.querySelector('.lowOrHi');**


-Error: La variable userGuess era una cadena de texto, mientras que randomNumber era un número entero.
Esto impedía la comparación directa entre ambas variables.

-Corrección: Se utilizó parseInt() para convertir userGuess en un número antes de la comparación.

**let userGuess = parseInt(guessField.value);**

-Error: Mensajes como "Pérdistes" aparecían incluso cuando el usuario ganaba el juego.

-Corrección: Se agregaron condiciones para que los mensajes de resultado fueran correctos según el estado del juego.

Verde para aciertos
Rojo para intentos incorrectos
Naranja para advertencias

**lastResult.textContent = 'Pérdistes!';**
      **lastResult.style.backgroundColor = 'red';**
      **setGameOver();**


-Error: addeventListener estaba mal escrito, lo que impedía la detección del evento y la ejecucion correcta del mismo.

-Corrección: Se remplazo la letra "e" por la letra "E":

**document.querySelector('.guessButton').addEventListener('click', checkGuess);**
**lastResult.addEventListener('click', resetGame);**
**guessSubmit.addEventListener('click', checkGuess);**

-Error: El usuario podía ingresar el mismo número varias veces sin recibir una advertencia.

-Corrección: Se agregó un array previousGuesses para evitar que el usuario ingresara el mismo número.

**let previousGuesses = [];**
**if (previousGuesses.includes(userGuess)) {**
  **lastResult.textContent = "Ya ingresaste este número, intenta con otro.";**
  **return;
**}**
**previousGuesses.push(userGuess);**


-Error: El usuario podía ingresar números fuera del rango permitido (1-100).

-Corrección: Se agregó una condición para evitar que el usuario ingresara números fuera del rango establecido

**if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {**
  **lastResult.textContent = 'Por favor, introduce un número válido entre 1 y 100.';**
  **lastResult.style.backgroundColor = 'orange';**
 ** return;** 
 **}**

-Error: variable para numero de intentos permitidos inicia en 5

-Corrección: Se estableció la variable para el número de intentos permitidos en 10

**const ATTEMPS = 10;**

-error: El contador inicia en 1 dandole al usuario 9 intentos para jugar.

-Corrección: Se estableció el contador en 0 para que el usuario tenga 10 intentos.
**if (guessCount === 0) {**


