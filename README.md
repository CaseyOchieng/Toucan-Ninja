
# Toucan 2D Game

Welcome to our simple 2D game project! This project demonstrates a basic implementation of a game using HTML for markup, CSS for styling, and JavaScript for interactivity. It's a fun and educational project suitable for beginners and enthusiasts alike.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Demo](#demo)
- [How to Play](#how-to-play)
- [Installation](#installation)
- [Code Explanation](#code-explanation)
- [Contributing](#contributing)
- [License](#license)
- [GitHub Repository](#github-repository)

## Introduction

This project is a simple 2D game built using HTML for markup, CSS for styling, and JavaScript for interactivity. The game aims to provide a fun experience while also serving as a learning tool for those interested in web development.

## Features

- Simple and intuitive gameplay
- Responsive design for various screen sizes
- Easy to understand codebase, suitable for beginners

## Demo

You can find a live demo of the game [here](#) (replace with link to your live demo).

![Game Demo](demo.gif) (replace with a screenshot or GIF of your game)

## How to Play

Playing the game is straightforward:

1. Use the arrow keys or WASD keys to control the player character.
2. Avoid obstacles and enemies.
3. Collect coins or power-ups to increase your score or abilities.
4. Reach the goal to win the game!

## Installation

To run the game locally, follow these steps:

1. Clone this repository to your local machine.
   ```
   git clone https://github.com/CaseyOchieng/Toucan-Ninja.git
   ```
2. Navigate to the project directory.
   ```
   cd Toucan-Ninja
   ```
3. Open the `index.html` file in your web browser.

That's it! You should now be able to play the game locally on your machine.

## Code Explanation

### Canvas Setup

```html
<style>
  body {
    background: black;
  }
</style>
<canvas></canvas>
```

This code sets up the canvas element in the HTML file and defines a black background in the CSS.

### JavaScript Setup

```html
<script src="./js/utils.js"></script>
<script src="./js/classes/CollisionBlock.js"></script>
<script src="./js/classes/Sprite.js"></script>
<script src="./js/classes/Player.js"></script>
<script src="./js/data/collisions.js"></script>
<script src="index.js"></script>
```

These script tags import necessary JavaScript files for the game, including utility functions, classes for game entities, and collision data.

### Game Initialization

```javascript
const canvas = document.querySelector('canvas')
const c = canvas.getContext('2d')

canvas.width = 1024
canvas.height = 576
```

This section initializes the canvas and its context, setting its width and height.

### Creating Collision Blocks

```javascript
const floorCollisions2D = []
for (let i = 0; i < floorCollisions.length; i += 36) {
  floorCollisions2D.push(floorCollisions.slice(i, i + 36))
}

const collisionBlocks = []
floorCollisions2D.forEach((row, y) => {
  row.forEach((symbol, x) => {
    if (symbol === 202) {
      collisionBlocks.push(
        new CollisionBlock({
          position: {
            x: x * 16,
            y: y * 16,
          },
        })
      )
    }
  })
})
```

This code segment processes collision data to create blocks for collision detection within the game environment.

### Player Initialization

```javascript
const player = new Player({
  position: {
    x: 100,
    y: 300,
  },
  collisionBlocks,
  platformCollisionBlocks,
  imageSrc: './img/warrior/Idle.png',
  frameRate: 8,
  animations: {
    // Animation configurations
  },
})
```

This initializes the player character with starting position, collision data, sprite images, and animation configurations.

### Game Animation Loop

```javascript
function animate() {
  window.requestAnimationFrame(animate)
  c.fillStyle = 'white'
  c.fillRect(0, 0, canvas.width, canvas.height)

  // Game rendering logic
}

animate()
```

This function sets up the animation loop for the game, updating and rendering game elements on each frame.

### Event Listeners for Player Controls

```javascript
window.addEventListener('keydown', (event) => {
  // Keydown event handling for player controls
})

window.addEventListener('keyup', (event) => {
  // Keyup event handling for player controls
})
```

These event listeners handle keyboard input for controlling the player character.

## Contributing

Contributions are welcome! If you'd like to contribute to the project, feel free to open an issue or submit a pull request. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the [MIT License](LICENSE).

## GitHub Repository

You can find the source code for this project on GitHub: [Toucan Ninja Repository](https://github.com/CaseyOchieng/Toucan-Ninja) and feel free to play around with the code.

---

