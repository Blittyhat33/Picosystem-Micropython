# Setup

First things first, make sure you have setup the Picosystem, installed the latest release and launched the Thonny IDE.
Connect the device to a USB port using a USB-C cable that fits and press the power button to switch on the Picosystem.  
In the Thonny IDE you should see an option to select the correct port (and interpretter)

![image](https://github.com/Blittyhat33/Picosystem-Micropython/assets/131597538/5d62e2a6-5c39-48a1-b047-780ec33b68dd)

Now you are good to go!

# First game loop

To get a feel for the device and the controls, the first game loop will be about the basics.

- Basis loop setup
- Drawing a background
- Drawing the HUD 
  - score
  - lives     
- Blitting/Placing the player
- Moving the player

The result will be a icon that can move across the screen using the directional pad.

## Basis loop setup

This is fairly simple. You need only three steps to create the foundation for this game

1. def update(tick):
2. def draw(tick):
3. start()

The script will not do anything and because both 'update' and 'draw' do not contain instructions, it will not run.
Let's change that in our next step.

## Drawing the background
To start with an easy approach, we can use the build in command to control the color of the 'pen'. This 'pen' is the device that is used to color the screen.
Let us pick a color that is friendly on the eyes: like lightgreen. The colors are RGB represented in a range of 0 to 15. 
For example:

- Black = Pen(0,0,0)
- White = Pen(15,15,15)
- Green = Pen(0,15,0)

For our background we will use: Pen(2,10,3).

This is something that should be the first step in our draw(tick) part. 
To tell the picosystem that this color should be used to clear the screen, we simply add a line with 'clear()'.
The script now looks like this:

![image](https://github.com/Blittyhat33/Picosystem-Micropython/assets/131597538/3fea8d4a-4c4a-481a-9a06-0af8d4dffcf1)

Run the script and the Picosytem should have a greenish screen.
Both the update and draw part of the script run every 'tick'. This makes sure that everything that is drawn to the screen gets erased every frame.









