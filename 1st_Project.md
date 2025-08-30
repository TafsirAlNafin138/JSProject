# Projects Related to DOM

## Project link
[Click Here...](https://stackblitz.com/edit/dom-project-chaiaurcode?file=index.html)

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