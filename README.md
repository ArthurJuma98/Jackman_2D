Jackman description

It includes two classes: Ghost and Jackman. Let's go through each class and explain its functionality:

Ghost Class:
The Ghost class represents a ghost character in the game.
It has properties such as x and y (position), width and height (dimensions), speed, imageX and imageY (coordinates of the ghost image in a sprite sheet), imageWidth and imageHeight (dimensions of the ghost image), and range (the range within which the ghost detects the Pacman).
The constructor initializes these properties and sets a random target for the ghost from an array of randomTargetsForGhosts.
The isInRange method checks if the Jackman is within the range of the ghost.
The changeRandomDirection method updates the random target index for the ghost, which determines its next target.
The moveProcess method controls the movement of the ghost. It checks if the Jackman is in range and updates the target accordingly. It then calls changeDirectionIfPossible to change the direction of the ghost if possible and move it forwards. If a collision is detected, it moves the ghost backwards.
The moveBackwards and moveForwards methods update the position of the ghost based on its current direction.
The checkCollisions method checks if the ghost has collided with any obstacles on the game map.
The changeDirectionIfPossible method changes the direction of the ghost based on its target and checks for collisions before updating the position.
The calculateNewDirection method calculates a new direction for the ghost using a breadth-first search algorithm on the game map.
The addNeighbors method adds neighboring positions to a queue for the breadth-first search algorithm.
The getMapX, getMapY, getMapXRightSide, and getMapYRightSide methods calculate the corresponding map coordinates for the ghost's position.
The changeAnimation method updates the current frame of the ghost's animation.
The draw method renders the ghost on the canvas, along with a circle representing its detection range.
Jackman Class:
The Jackman class represents the Jackman character in the game.
It has properties such as x and y (position), width and height (dimensions), and speed.
The constructor initializes these properties and sets the current and next directions of Jackman.
The moveProcess method controls the movement of Jackman. It calls changeDirectionIfPossible to change the direction if possible and moves Jackman forwards. If a collision is detected, it moves Jackman backwards.
The eat method checks if Jackman has collided with any food pellets on the game map and updates the score accordingly.
The moveBackwards and moveForwards methods update the position of Jackman based on its current direction.
The checkCollisions method checks if Jackman has collided with any obstacles on the game map.
The checkGhostCollision method checks if Jackman has collided with any of the ghosts.
The changeDirectionIfPossible method changes the direction of Jackman if the next direction is different from the current direction and checks for collisions before updating the position.
The getMapX, getMapY, getMapXRightSide, and getMapYRightSide methods calculate the corresponding map coordinates for Jackman's position.
The changeAnimation method updates the current frame of Jackman's animation.

Game.js description

It defines various variables, objects, and functions related to the game logic. Here's a breakdown of the code:

It starts by getting references to the HTML elements, such as the canvas and the image elements for the Jackman animation and ghost images.

Next, it defines a helper function called createRect that is used to draw rectangles on the canvas with specified position, size, and color.

It sets some constants for the directions (right, up, left, and bottom), as well as variables for lives, ghost count, ghost image locations, game variables, and the game map.

The code then defines a class called Jackman with properties and methods related to the Jackman character, such as its position, size, speed, and movement logic.

Similarly, it defines a class called Ghost for the ghost characters, including properties for position, size, speed, animation frames, and movement logic.

The code defines several functions for various game operations, such as creating a new Jackman and ghosts, updating the game state, drawing elements on the canvas (walls, foods, ghosts, score, and lives), handling ghost collisions, and the game loop.

It initializes the game by creating a new Jackman, ghosts, and starting the game loop using the setInterval function.

Lastly, it adds an event listener for keydown events to handle user input for controlling the Jackman's movement.

Ghost.js description

Here's a breakdown of the key components and methods in the code:

Constructor: Initializes a Ghost object with various properties such as position (x and y), dimensions (width and height), speed, image coordinates (imageX and imageY), image dimensions (imageWidth and imageHeight), and range.
isInRange() method: Checks if the ghost is within range of the target (either the player's character, referred to as jackman, or a random target). It calculates the Euclidean distance between the ghost's position and the target's position and compares it to the range.
changeRandomDirection() method: Randomly changes the index of the target from the randomTargetsForGhosts array. This method is called at regular intervals using setInterval() in the constructor.
moveProcess() method: Handles the movement of the ghost. It determines the target (either jackman or a random target), changes the ghost's direction if possible, moves the ghost forwards, checks for collisions, and moves the ghost backwards if a collision occurs.
moveBackwards() and moveForwards() methods: Move the ghost in the opposite and forward directions, respectively, based on the current direction property.
checkCollisions() method: Checks if the ghost has collided with any obstacles on the map. It uses the map array and the ghost's position to determine if there is a collision.
changeDirectionIfPossible() method: Changes the ghost's direction based on the target's position and the current map. It uses a breadth-first search algorithm to find the shortest path to the target. If a valid direction is found, the ghost moves forwards, checks for collisions, and reverts the direction if necessary.
calculateNewDirection() method: Implements the breadth-first search algorithm to calculate a new direction for the ghost. It creates a copy of the map, initializes a queue with the ghost's initial position, and iteratively explores neighboring positions until the destination is reached.
addNeighbors() method: Adds neighboring positions to the queue for exploration during the breadth-first search. It checks for valid positions and avoids obstacles.
getMapX(), getMapY(), getMapXRightSide(), and getMapYRightSide() methods: Calculate the corresponding indices on the map for the ghost's position and the right side of the ghost.
draw() method: Draws the ghost on the canvas using the provided image coordinates, dimensions, and position. It also draws a circle indicating the ghost's range.
updateGhosts() and drawGhosts() functions: Iterate over all the ghosts in the ghosts array and call their respective moveProcess() and draw() methods.
It seems like the code is part of a larger game or simulation where ghosts move towards a target (either the player or a random target) while avoiding obstacles on the map. The ghosts periodically change their random target, and their movement is updated and drawn in each game loop.

