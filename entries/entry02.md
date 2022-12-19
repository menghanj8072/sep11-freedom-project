# Entry 2
##### 12/12/2022

In the last blog entry, I explained why I picked KaboomJs as my freedom project. Now in this blog, I will be talking about how I learn KaboomJs. In the KaboomJs website, there was a tutorial that covers the basic concepts. The tutorial teaches how to make a Chrome Dino game. First I start off by setting up Kaboom development. There was a option for me to fork a template, so I forked it on replit. Then I begin following the steps on the tutorial. My first few steps was to add a background and add a sprite. I learned that using `kaboom()` will add a blank canvas with checkboard pattern. To add a sprite, I will have to use `loadSprite()` to load the sprite from an image. As I move on following the steps, I came across adding obstacles to the game. The obstacles will be representating as trees. When I was adding the code for the obstacles, I was thinking if I can make the obstacles not only on ground but also on the top of the screen. I looked into the code to see what can I change to make that happen. I notice that in `pos()` I can change the position. Then I played around with the position and I found out the solution.
Here is the original code:
```JS
pos(width(), height() - 48),
```
After:
```JS
pos(width(), 0 + 48),
```
Although I found out the solution, but I was still confused how it works. I will have to tinker more and do some research.







[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
