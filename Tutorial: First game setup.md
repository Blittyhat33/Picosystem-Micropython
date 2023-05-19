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

For our background we will use: _Pen(2,10,3)_.

This is something that should be the first step in our draw(tick) part. 
To tell the picosystem that this color should be used to clear the screen, we simply add a line with 'clear()'.
The script now looks like this:

![image](https://github.com/Blittyhat33/Picosystem-Micropython/assets/131597538/3fea8d4a-4c4a-481a-9a06-0af8d4dffcf1)

Run the script and the Picosytem should have a greenish screen.
Both the update and draw part of the script run every 'tick'. This makes sure that everything that is drawn to the screen gets erased every frame.

## Drawing a HUD (Head up Display)

To keep track of progress it is a good step to display a score and a number of lives the player currently has.
For this part of the tutorial there will not be an mechanism in place for this part of the gameplay.
The setup however, is crucial and is done in this part.

To do this, we will create an variable on top of our script with the name 'score' and 'lives'.

_player_lives = 3
score = 0_

We will also use an variable with the horizontal an vertical display size.
_WINDOW_WIDTH = 120
WINDOW_HEIGHT = 120_

Now we have to display this on our background. 
In our draw(tick) part we will add a new line (below clear()).
To make the new input visible, a new color should be chosen.
In this example we will use light blue.

We can use the variables to generate a score and lives text field.
The command to add text to the display is text(). This command takes 3 parameters: the text, x and y.
For this game we want to place the text of the score in the middle and the player lives in the top left corner.
This is done by using the command:

_text("Lives: "+ str(player_lives),0 , 3)_

Note the y coordinate of _3_: this is to ensure readibility.

To display the score: we should use the window width and divide this by 2.
To make sure the result is an integer (in this case that is not an issue), it is a good custom to use whole integer division:

_text("Score: "+ str(score),WINDOW_WIDTH//2,3)_

To finish this HUD we will draw a primitive shape: a horizontal line.
It needs an x and y starint coordinate and (because it is an horizontal line) the size. In this case that would be the whole screen.

_hline(0,12,WINDOW_WIDTH)_

![image](https://github.com/Blittyhat33/Picosystem-Micropython/assets/131597538/fac8016a-0bfe-4b2c-ae4e-bcbb6cad551d)

Nice, but to create some basic gameplay, we at least need a **player**!

## Blitting the player

The device is packed with a nice set of images (sprites). This way we don't have to create all images using only primitive shapes.
To place an image on the screen we can use a technique called 'blitting'.
But before we do this, we will create a number of new variables.

First we need an icon. There are a large number of icons to choose from, but we will start with something that looks a bit like a cat.

_player_icon = 184_

Next we will position the player on the screen. Of course the player will move later on, but for now the posittion needs to be close to the left edge of the screen.
First we will position the player on the y axis, somewhere in the middle.

_player_y = WINDOW_HEIGHT//2_

The x position will be done in a similar way:

_player_x = WINDOW_WIDTH//10

To ensure that the icon is visible, we will use an size of 20. Note that you can stretch images, but for the player icon this will cause serious distortions.
We will use the same variable for bot the widt and height.

_player_size = 20_

Now whe only have to add one extra line to our draw script:

_sprite(player_icon, player_pos_x,player_pos_y, 1,1,player_size,player_size)_

Notice the 1,1 in this line? That is because this methods also allows you to draw multiple iamges (sprites) with this command. 
For this game we only need one icon, so this options can be ignored.

![image](https://github.com/Blittyhat33/Picosystem-Micropython/assets/131597538/b2973216-f371-437a-b8cc-c928c87980fe)

Next step is the movement of the player.












 







