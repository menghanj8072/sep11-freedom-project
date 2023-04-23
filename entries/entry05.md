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
The game can't function without a main sprite to represent as the player. So inside the **game scene** I create a variable named "player" and set it equal to add(). The add() function will contain the sprite and it's position.







[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
