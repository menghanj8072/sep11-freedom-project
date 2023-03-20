# Entry 4
##### 3/13/2023
Last time I wasn't able to finish the flappy bird tutorial. But now I have finished it. I have added score and collision detection. For the scoring system every time when the bird flies past a pipe, the score will increase by 1. In order to make the system, I have to add a custom property called `passed` inside the producePipes function. Then I have to save the score inside a variable and display it on the screen so that the player can know their score. After doing that, I have to do the last step to finish the scoring system. I need to check if any pipes have moved past flappy bird, and update their `passed` flag, so that the system won't count them more than once. So I need to modify the onUpdate() event handler by adding a `if` statement.
Here is the code for the scoring system:
```JS
//Add into the producePipes function
{ passed: false },

//Variable to keep track of the score
let score = 0;
const scoreText = add([text(score, { size: 50 })]);

//Add into the onUpdate()
  if (pipe.passed === false && pipe.pos.x < player.pos.x) {
    pipe.passed = true;
    score += 1;
    scoreText.text = score;
```
Now I have to make the collision detection system. I need to check if the flappy bird have collide with a pipe. On the tutorial it says that "Kaboom  has a `collide` method that is added with the `area` collider component." So I need to use that and I can also call a function when the flappy bird collides with a pipe.
```JS
player.collides("pipe", () => {
  go("gameover", score);
});
```
The `go` function will switch to the gameover scene when the flappy collides with a pipe. Then I have to add a message saying that the game is over and display the player's score and also their highest score. I have to create a variable call `highscore` to keep track of the highest scores and to compare it with the latest score and to see if the score need to be updated. I also need to use `onKeyPress` eventlistener to listen to for the player when they press the `space` bar for playing again.
```JS
let highScore = 0;
scene("gameover", (score) => {
  if (score > highScore) {
    highScore = score;
  }

  add([
    text("gameover!\n" + "score: " + score + "\nhigh score: " + highScore, {
      size: 45,
    }),
  ]);

  onKeyPress("space", () => {
    go("game");
  });
});

```
After finishing the flappy bird tutorial, I have to work on the MVP for my freedom project. I didn't really make much progress on it yet. I only added a start button and also a background for the game. I'm still working on adding instructions and a name for the game.

Right now I'm currently in stage **2 Research the Problem** and **5 create a prototype**. I'm learning about my FP tool and making my MVP(Minimum Viable Product) for my FP at the same time. One new skill I learned was "**Time Mangement**". I learned when I should focus on learning my tool and when I should work on my MVP.

















[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
