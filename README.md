# RGB-Slider
Design: CodeWithSMR
# RGB Slider Project

This project is a simple web application that allows users to control the Red, Green, and Blue (RGB) color values using sliders. As the user adjusts the sliders, the background color changes dynamically to reflect the selected RGB values.

## Features

- **Interactive RGB sliders**: Control the Red, Green, and Blue color channels independently.
- **Dynamic background color**: The background color updates in real-time based on slider input.
- **RGB value display**: Shows the current RGB values corresponding to the chosen color.
- **Copy Color Code**: Easily copy the generated RGB color code with a single click.

## Demo

![RGB Slider](https://example.com/demo.gif)

## How to Use

1. Adjust the Red, Green, or Blue sliders to change the background color.
2. Click the "Copy Color Code" button to copy the generated RGB color code.
3. The copied RGB value can then be used in other projects.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/rgb-slider.git
    ```
   
2. Navigate to the project directory:
    ```bash
    cd rgb-slider
    ```

3. Open `index.html` in your web browser:
    ```bash
    open index.html
    ```

## Technologies Used

- **HTML**: Structure of the sliders and display elements.
- **CSS**: Basic styling for the sliders and layout.
- **JavaScript**: Handles the logic for updating colors dynamically and copying color codes.

## Example Code

```javascript
const result = document.querySelector(".result input");
const copyBtn = document.getElementById("copy-btn");
const sliders = document.querySelectorAll(".wrapper input[type='range']");
const rColor = document.getElementById("red");
const gColor = document.getElementById("green");
const bColor = document.getElementById("blue");

let generateColor = () => {
  let rColorValue = rColor.value;
  let gColorValue = gColor.value;
  let bColorValue = bColor.value;

  let finalColor = `rgb(${rColorValue}, ${gColorValue}, ${bColorValue})`;
  result.value = finalColor;
  document.body.style.backgroundColor = finalColor;
};

let copyColorCode = () => {
  result.select();
  document.execCommand("copy");
  copyBtn.innerText = "Copied!";
  setTimeout(() => {
    copyBtn.innerText = "Copy Color Code";
  }, 1000);
};

sliders.forEach((inp) => {
  inp.addEventListener("input", generateColor);
});
window.addEventListener("load", generateColor);
copyBtn.addEventListener("click", copyColorCode);
