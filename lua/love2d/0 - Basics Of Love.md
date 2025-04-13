### Project Setup


![](attachments/Pasted%20image%2020250412224115.png)


- first of all we will need a main.lua file that imports love framework with the first line
- load : when we boot up the game
- update : runs every frame 
	- ( in 1 second it will called 60 times 60 fps ) dt (delta time) 
	- ( move player will happen in here )
- draw : draws every thing to screen

![Another Image](attachments/Pasted%20Image%2020250411163408_297.png)
1. at first load will set number to 2
2. and then every frame will increase number to 5 
3. and after update the draw will draw it in that frame


### Config File
![Config Image](attachments/Pasted%20Image%2020250411173207_637.png)

- the file that allows us to config application more to add permission or some features too
configs : 
https://love2d.org/wiki/Config_Files

### Shapes

![Shapes Image](attachments/Pasted%20Image%2020250411182806_639.png)

### Little Packman Game : 

```lua
_G.love = require("love") -- Optional: usually not necessary, love is globally available
function love.load()
    -- Set the background color (applied once on load)
    love.graphics.setBackgroundColor(1, 1, 1) -- White background (R, G, B from 0 to 1)

    _G.windowWidth, _G.windowHeight = love.graphics.getWidth(), love.graphics.getHeight() -- Resizable is off

    -- Initialize Pac-Man
    _G.packman = {
        x = 100,
        y = 250,
    }

    -- Initialize Food
    _G.food = {
        x = 600,
        y = 200,
        eaten = false
    }
end

function love.update(dt)
    -- Move left
    if love.keyboard.isDown("a") and packman.x > 0 then
        packman.x = packman.x - 1
    end

    -- Move right
    if love.keyboard.isDown("d") and packman.x < windowWidth then
        packman.x = packman.x + 1
    end

    -- Move up
    if love.keyboard.isDown("w") and packman.y > 0 then
        packman.y = packman.y - 1
    end

    -- Move down
    if love.keyboard.isDown("s") and packman.y < windowHeight then
        packman.y = packman.y + 1
    end

    -- Check for "eating" the food (basic X overlap logic)
    if packman.x >= food.x + 20 then
        food.eaten = true
    end
end

function love.draw()
    -- Draw the food only if it hasn't been eaten
    if not food.eaten then
        love.graphics.setColor(1, 0, 0) -- Red color
        love.graphics.rectangle("fill", food.x, food.y, 100, 100) -- Food block
    end

    -- Draw Pac-Man (as a black arc)
    love.graphics.setColor(0, 0, 0) -- Black color
    love.graphics.arc("line", packman.x, packman.y, 60, 1, 5) -- Pac-Man shape
end
```
