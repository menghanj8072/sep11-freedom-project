# Entry 5
##### 4/17/2023

In previous blog, I talked about finish following the Flappy Bird tutorial and starting building my MVP for my freedom project. After that I didn't research for another tutorial to follow because I have to focus on the MVP. My idea for my freedom project was to build a game similar to flappy bird. However, as im working on it the result didn't turn out to be what I wanted. So I changed my idea to make a fish eat fish game. I first start off by creating three scenes for the game: **intro, game, and gameover**. Then I added backgrounds for the three scenes by using `add()`. Inside the intro scene, I created a "start" button and when the player clicks on it, it will link to the game.
```JS
scene("intro", () => {

  add([sprite("bg", { width: width(), height: height() })]);
  
  function addButton(txt, p, f) {
  	const btn = add([
  		text(txt),
  		pos(p),
  		area({ cursor: "pointer", }),
  		scale(1),
  	])
  	btn.onClick(f)
  }
  
  addButton("Start", vec2(200,100), () => 
  go("game"));
});
```
The game can't function without a main sprite to represent as the player. So inside the **game scene** I create a variable named "player" and set it equal to `add()`. The `add()` function will contain the sprite and it's position. The main sprite that the player is going to control is a shark. I decided to make the sprite jump instead of moving in x and y-axis positions. I used `onKeyPress()` function set it to "space", so everytime when the player pressed the space bar the sprite will jump.
```JS
//Player
var player = add([
  sprite("shark"),
  scale(2),
  pos(80, 40),
  area(),
  body(),
]);

  
//Jump when space is pressed
  onKeyPress("space", () => {
  player.jump(400)
})
```
Next I have to add fish into the game. The fish will spawn randomly inside the game. When the player collides with the fish, they will gain 1 point and the fish will disappear. To do that I used the function from the flappy bird tutorial for spawning pipes to help me with spawning fish. Since I made 3 fish sprites, I have to add the sprites for each fish into the function. Then I have to make it spawn at random positions. I used the `pos()` function set x position to width() and use `rand()` to set random y position. 
```JS
function spawn_fish(){
  add([
    sprite("fish1"),
    pos(rand(width()), rand(0,height())),
    "fish1",
    area(),
  ]);

  add([
    sprite("fish2"),
    pos(rand(width()), rand(0, height())),
    "fish2",
    area(),
  ]);

  add([
    sprite("fish3"),
    pos(rand(width()), rand(0, height())),
    "fish3",
    area(),
  ]);
}
```








[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
