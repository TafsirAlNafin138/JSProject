# Projects Related to DOM

## Project link
[Click Here...](https://stackblitz.com/edit/dom-project-tafsiralnafin-tbxjywwb?file=index.html)

# Solution Code


## Project 1
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
    height = height / 100; // convert cm → m
    const bmi = weight / height ** 2;

    if (bmi < 18.6) {
      result.textContent = "You're in the Underweight Zone! Eat healthy!";
    } else if (bmi < 24.9) {
      result.textContent =
        "Congratulations! You're in the Normal Zone! Keep it up!";
    } else {
      result.textContent = 'Overweight :( Please exercise regularly.';
    }
  }
});

```