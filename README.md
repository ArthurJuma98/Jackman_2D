# Game Description

## Jackman Class

The `Jackman` class represents the main character in the game. It possesses the following properties:

- **Position**: `x` and `y` coordinates.
- **Dimensions**: `width` and `height`.
- **Speed**: Movement speed of the character.
- **Directions**: Current and next directions of movement.

### Methods:

1. **Constructor**: Initializes the Jackman object with its properties and sets initial directions.

2. **moveProcess()**: Controls Jackman's movement. It changes direction if possible, moves Jackman forwards, and handles collisions.

3. **eat()**: Checks if Jackman has collided with food pellets, updating the score accordingly.

4. **moveBackwards() and moveForwards()**: Update Jackman's position based on the current direction.

5. **checkCollisions()**: Checks if Jackman has collided with obstacles on the game map.

6. **checkGhostCollision()**: Checks if Jackman has collided with any of the ghosts.

7. **changeDirectionIfPossible()**: Changes Jackman's direction if the next direction is different and checks for collisions before updating the position.

8. **getMapX(), getMapY(), getMapXRightSide(), and getMapYRightSide()**: Calculate corresponding map coordinates for Jackman's position.

9. **changeAnimation()**: Updates the current frame of Jackman's animation.

## Ghost Class

The `Ghost` class represents the enemy characters in the game. It has various properties and methods:

### Properties:

- **Position**: `x` and `y` coordinates.
- **Dimensions**: `width` and `height`.
- **Speed**: Movement speed.
- **Image Coordinates and Dimensions**: `imageX`, `imageY`, `imageWidth`, and `imageHeight`.
- **Range**: The range within which the ghost detects Jackman.

### Methods:

1. **Constructor**: Initializes Ghost with properties and sets a random target from an array.

2. **isInRange()**: Checks if Jackman is within the ghost's range.

3. **changeRandomDirection()**: Updates the random target index for the ghost.

4. **moveProcess()**: Controls the ghost's movement. It updates the target, changes direction, moves forwards or backwards based on conditions, and checks for collisions.

5. **moveBackwards() and moveForwards()**: Update the ghost's position based on the current direction.

6. **checkCollisions()**: Checks if the ghost has collided with obstacles on the game map.

7. **changeDirectionIfPossible()**: Changes the ghost's direction based on its target, checking for collisions before updating the position.

8. **calculateNewDirection()**: Uses breadth-first search algorithm to calculate a new direction for the ghost.

9. **addNeighbors()**: Adds neighboring positions to a queue for breadth-first search.

10. **getMapX(), getMapY(), getMapXRightSide(), and getMapYRightSide()**: Calculate corresponding map coordinates for the ghost's position.

11. **changeAnimation()**: Updates the current frame of the ghost's animation.

12. **draw()**: Renders the ghost on the canvas, along with a circle representing its detection range.

# Game.js Description

The `Game.js` file defines various variables, objects, and functions related to the game logic:

1. **Initialization**: Gets references to HTML elements and sets up constants for directions, game variables, and map details.

2. **Jackman and Ghost Classes**: Defines classes for Jackman and Ghost characters, including their properties and methods.

3. **Helper Function**: Creates a helper function (`createRect`) for drawing rectangles on the canvas.

4. **Game Logic Functions**: Defines functions for creating characters, updating game state, drawing elements on the canvas, handling collisions, and implementing the game loop.

5. **Game Initialization**: Creates instances of Jackman and Ghosts, and starts the game loop using `setInterval`.

6. **Event Listener**: Adds an event listener for keydown events to handle user input for controlling Jackman's movement.

# Ghost.js Description

The `Ghost.js` file focuses on the `Ghost` class, providing detailed information about its properties and methods:

- **Constructor**: Initializes Ghost object with various properties.
- **isInRange()**: Checks if Ghost is within range of the target.
- **changeRandomDirection()**: Randomly changes the index of the target.
- **moveProcess()**: Handles the movement of the ghost, determining the target, changing direction, and updating position based on conditions.
- **moveBackwards() and moveForwards()**: Move the ghost in opposite and forward directions based on the current direction.
- **checkCollisions()**: Checks if the ghost has collided with obstacles on the map.
- **changeDirectionIfPossible()**: Changes the ghost's direction based on the target's position and the current map, using a breadth-first search algorithm.
- **calculateNewDirection()**: Implements the breadth-first search algorithm to calculate a new direction for the ghost.
- **addNeighbors()**: Adds neighboring positions to the queue for exploration during breadth-first search.
- **getMapX(), getMapY(), getMapXRightSide(), and getMapYRightSide()**: Calculate corresponding indices on the map for the ghost's position.
- **draw()**: Draws the ghost on the canvas along with a circle indicating its range.
