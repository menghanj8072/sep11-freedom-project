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



















[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
