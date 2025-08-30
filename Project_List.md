# Projects Related to DOM

## Project link
[Click Here...](https://stackblitz.com/edit/dom-project-tafsiralnafin-tbxjywwb-qcfledxv?file=index.html)

# Solution Code


## Project 1 
### Color Changer
```javaScript
console.log("Hello World")

const Button = document.querySelectorAll('.button');
const body = document.querySelector('body');
Button.forEach((button) => {
  // console.log(button);
  button.addEventListener('click', (e) => {
    console.log(e);
    console.log(e.target);
    switch (e.target.id) {
      case 'grey':
        body.style.backgroundColor = e.target.id;
        break;
      case 'yellow':
        body.style.backgroundColor = e.target.id;
        break;
      case 'white':
        body.style.backgroundColor = e.target.id;
        break;
      case 'blue':
        body.style.backgroundColor = e.target.id;
        break;
      case 'purple':
        body.style.backgroundColor = e.target.id;
        break;
    }
  });
});


```

## Project 2
### BMI Calculator

``` javaScript

const form = document.querySelector('form');

form.addEventListener('submit', (e) => {
  e.preventDefault();
  let height = document.querySelector('#height').value;
  height = parseFloat(height);
  let weight = parseFloat(document.querySelector('#weight').value);

  let result = document.querySelector('#results');
  result.style.display = 'block';
  if (height === '' || height < 0 || isNaN(height)) {
    result.textContent = 'Enter a valid Height';
  } else if (weight === '' || weight < 0 || isNaN(weight)) {
    result.textContent = 'Enter a valid Weight';
  } else {
    height = height / 100;
const bmi = weight / height ** 2;

let message = `Your BMI is: ${bmi.toFixed(2)}\n \n`; 

if (bmi < 18.6) {
  message += "You're in the Underweight Zone! Eat healthy!";
} else if (bmi < 24.9) {
  message += "Congratulations! You're in the Normal Zone! Keep it up!";
} else {
  message += "Overweight! ☹️ Please exercise regularly.";
}

result.textContent = message; 
  }
});


```


## Project 3
### Digital Clock

``` javaScript

const clock = document.querySelector('#clock');

setInterval((ele) => {
  let date = new Date();
  clock.textContent = date.toLocaleTimeString();
}, 1000);

```


## Project 4
### Guess The Number

``` javaScript

let randomNumber = Math.floor(Math.random() * 100) + 1;

let submitbutton = document.querySelector('#subt');
const userInput = document.querySelector('#guessField');
const previousGuess = document.querySelector('.guesses');
let remainningAttemp = document.querySelector('.lastResult');
const start = document.querySelector('.resultParas');
const p = document.querySelector('.lowOrHi');
const add = document.querySelector('.add');

let canplay = true;
let counter = 0;

let store = [];

if (canplay) {
  submitbutton.addEventListener('click', (e) => {
    e.preventDefault();
    const guess = parseInt(userInput.value);
    isValidInput(guess);
  });
}

function isValidInput(guess) {
  if (isNaN(guess)) {
    alert('Enter a valid Number');
  } else if (guess < 1) {
    alert('Number should be strictly greater than 0');
  } else if (guess > 100) {
    alert('Number should be less than or equal to 100');
  } else {
    store.push(guess);
    if (counter === 10) {
      displayPreviousGuess(guess);
      displayMesseage(`Game Over. The Number was ${randomNumber}`);
      endGame();
    } else {
      displayPreviousGuess(guess);
      checkInput(guess);
    }
  }
}

function checkInput(guess) {
  if (guess === randomNumber) {
    displayMesseage(`Congrats! You guessed it Correctly`);
    endGame();
  } else if (guess < randomNumber) {
    displayMesseage(`Number us too low`);
  } else if (guess > randomNumber) {
    displayMesseage(`Number is too High`);
  }
}

function displayPreviousGuess(guess) {
  userInput.value = '';
  previousGuess.innerHTML += `${guess}, `;
  counter++;
  remainningAttemp.innerHTML = `${10 - counter}`;
}

function displayMesseage(message) {
  p.innerHTML = `${message}`;
}

function endGame() {
  canplay = false;
  userInput.value = '';
  remainningAttemp.innerHTML = '';
  userInput.setAttribute('disabled', '');
  add.classList.add('button');
  add.innerHTML = `<h3 id = "newGame">Start new Game</h3>`;
  start.appendChild(add);
  newGame();
}

function newGame() {
  const newGameButton = document.querySelector('#newGame');
  newGameButton.addEventListener('click', (e) => {
    e.preventDefault();
    canplay = true;
    randomNumber = Math.floor(Math.random() * 100) + 1;
    store = [];
    counter = 0;
    previousGuess.innerHTML = '';
    remainningAttemp.innerHTML = `${10}`;
    userInput.removeAttribute(`disabled`);
    p.innerHTML = '';
    start.removeChild(add);
  });
}

```