# Picosystem-Micropython
Scripts for the Pimoroni Picosytem using the pre-installed micropython environment

**Background**

When I received my Picosystem device, I noticed that there is not much documentation available to quickly make your first game.
I think there is a lot of potential for startin small and use a few beginnner friendly techniques. This techniques tend to be replaced with more complex methods for real life applications such as classes and methods, but these concepts make the code harder to read if you are just starting.

**Approach**

I gained some knowledge of the basics of game-programming by following the excelent cours ... on Udemy.
Althought this is tought using pygame, many of the concepts still apply to this device.
The course starts with a game where you are a character that must catch something that is flying accross the screen.

This is the game that is converted to a micropython script.
The tutorial can be found here.

The other game is a vertical catch game. 

Last in line is a tool to create objects in a live-coding setting. The benefit of this is a way of quickly creating assets for your game.

**Additonal remarks**

None of the code is using advanced programming skills such as classes. This will lead to some poor designing choices (such as repeating code).

Every game can be expanded with a start screen, a game over screen and other common 'states' in which a game van reside.
This advanced type of operations is all done using variables instead of (game)classes.


