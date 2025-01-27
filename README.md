# Space-Engine
## Description
This is an engine that allows a player to fly around in a rocket in space with realistic gravitational forces. 

## Controls
Rotate by pressing the left and right arrow keys. It is possible to roll on a planet by rotating while on the ground.
Accelerate by holding the space bar.
Press Backspace to reset the universe
Press Escape to close the program

## Code explanation
### Movement
Everything in this game is done through the game's physics engine. The player's velocity is never directly set. Instead, the player moves through the application of thrust and force. Similarly, the planets have a large Area2D node that, when any physics body enters it, will begin to exert a gravitational force depending on the distance according to newtons laws. The planets have a gravitational strength that is set upon its creation, depending only on the size of the planet. Because we are only considering the application of force when an object falls close enough for the gravitational forces to be significant, we do not need to consider the miniscule forces of 20 planets all adding up on the player, improving performance considerably. 

### Generation
When the world starts, the game will generate 20 different planets based on a script stored in the world node of the world scene. This script randomizes several aspects of the planets, including:
- Position (the code ensures that planets don't overlap too much, however I purposely left a little bit of leeway because I believe that two planets slightly intersecting looks really cool)
- Rotation
- Texture (The game uses a randomly selected image or image of Earth, Mars, Mercury, or Neptune)
- Hue
- Radius (There is a default radius and a set percentage that the planet can vary, set to 50% by default)
- Gravitational strength (There is a default gravitational strength that is multiplied by the ratio between the current radius and the default radius)

### Visuals
The game has a particle system that creates particles whenever the player holds the space bar. These tiny squares are pushed away from the ship upon creation and shift from a red to yellow color and shrink as time goes on. These particles are ejected at a specified velocity, and can appear to move faster or slower depending on the speed of the player

The background consists of 3 separate layers made by me on pixilart.com. These layers (other than the black background) are transparent and move in parallax, meaning they move at different speeds as the player moves, creating the illusion of depth.

I intended to use something other than the default icon for the player at some point, with the Godot icon being a placeholder. However, because the game is meant to show proficiency with Godot, the unique shape of the icon allows the player to roll around on a planet's surface, and because it is cute, I decided to leave it in for the final version

## Credit
All code, background, and particle effects by me.
Godot icon by Godot
Planet pictures are from https://nineplanets.org/
