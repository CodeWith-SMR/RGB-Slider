# RGB-Slider
Design: CodeWithSMR
# RGB Slider Project

This project is a simple web application that allows users to control the Red, Green, and Blue (RGB) color values using sliders. As the user adjusts the sliders, the background color changes dynamically to reflect the selected RGB values.

## Features

- **Interactive RGB sliders**: Control the Red, Green, and Blue color channels independently.
- **Dynamic background color**: The background color updates in real-time based on slider input.
- **RGB value display**: Shows the current RGB values corresponding to the chosen color.

## Demo

![RGB Slider](https://example.com/demo.gif)

## How to Use

1. Adjust the Red, Green, or Blue sliders to change the background color.
2. The numeric values for the RGB components are displayed alongside the sliders.
3. The resulting color will be shown in the background of the page.

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
- **JavaScript**: Handles the logic for updating colors dynamically.

## Code Overview

- `index.html`: Contains the structure of the sliders and the container for displaying the color.
- `styles.css`: Provides basic styles for the sliders, layout, and color display.
- `script.js`: JavaScript file that listens to changes on the sliders and updates the background color dynamically.

## Example Code

```html
<input type="range" id="redSlider" min="0" max="255" value="128">
<input type="range" id="greenSlider" min="0" max="255" value="128">
<input type="range" id="blueSlider" min="0" max="255" value="128">

<script>
  const redSlider = document.getElementById('redSlider');
  const greenSlider = document.getElementById('greenSlider');
  const blueSlider = document.getElementById('blueSlider');
  
  const updateColor = () => {
    const red = redSlider.value;
    const green = greenSlider.value;
    const blue = blueSlider.value;
    document.body.style.backgroundColor = `rgb(${red}, ${green}, ${blue})`;
  };

  redSlider.addEventListener('input', updateColor);
  greenSlider.addEventListener('input', updateColor);
  blueSlider.addEventListener('input', updateColor);
</script>
