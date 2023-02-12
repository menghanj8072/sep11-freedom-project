# Entry 3
##### 2/6/2023

During the winter break, I have found a new tutorial to follow. The tutorial was about making Flappy Bird Game in Kaboom Js. In order for me to begin the tutorial, I have to make a new project first in replit. After doing that I begin downloading the sprites and assest files that I will need for making the Flappy Bird Game. The first step in the tutorial was to import the sprites and sound by using `loadSprite()` and `loadSound()`. Then I begin adding scenes to the game. Scenes are like different stages in Kaboom. As mention in the tutorial, the Flappy Bird Game has 3 scenes: start, main game, and end. So I follow the steps and created the scene by doing:
```JS
scene("game", () => {
});

scene("gameover", (score) => {
});

go("game");
```
Then I moved on to the next step which is to build the game world. What that means is that to add the background and the main sprite "flappy bird" into the game. According to the tutorial, I have to use `add()` function to add the backgroud and the "flappy bird". I have to do it inside the `game scene`. 
```JS
scene("game", () => {
  add([sprite("bg", { width: width(), height: height() })]);
  
  const player = add([
  sprite("birdy"),
  scale(2),
  pos(80, 40),
  area(),
  body(),
]);
});
```
After building the game world, the next step was to make the flappy bird fly and adding the pipes. In order to make the bird fly, I have to use the `onKeyPress` function. This function allows something to happen when certain key is pressed. On tutorial it says to set it to "space" and add sound when the space key was pressed. It was pretty easy to understand how this function works. After that I moved on adding pipes. The pipes must have gaps between each one on the top and the bottom. For the position of the pipe on the bottom, the tutorial already calculated it which is `height()/2 + offset + PIPE_GAP/2`. Same for the position of the pipe on the top `height()/2 + offset - PIPE_GAP/2`. The difference between the two code is the `+` and the `-` sign. I have to add all those code inside a function. Then I have to update the all pipes' positions with each frame using `onUpdate` function and use `loop` function to generate pipes at a steady rate. 

Make flappy bird fly(inside game scene):
```JS 
onKeyPress("space", () => {
  play("wooosh");
  player.jump(400);
});
```
Add pipes(inside game scene):
```JS
function producePipes(){
    const offset = rand(-50, 50);

    add([
      sprite("pipe"),
      pos(width(), height()/2 + offset + PIPE_GAP/2),
      "pipe",
      area(),
      {passed: false}
    ]);

    add([
      sprite("pipe", {flipY: true}),
      pos(width(), height()/2 + offset - PIPE_GAP/2),
      origin("botleft"),
      "pipe",
      area()
    ]);
}
```
Here is the result I have so far. I didn't get really far on the tutorial. I still have to add scores, things for the `end scenes`, etc.
![flappy-pipe](https://replit-docs-images.util.repl.co/images/tutorials/35-flappy-bird/moving-pipes.gif)











[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
