 - Its better to create another module for enemy 
- The point of this is more like understanding oop in lua
Enemy Module :
```lua
local love = require("love")

  

-- Enemy module

-- File name is capitalized to indicate it represents an object-like structure (similar to a class)

  

function Enemy()

    -- In Lua, everything inside the return block is nicely encapsulated :)

    -- So we use this outer scope as a sort of "constructor" to initialize values

  

    -- Randomly decide which of the 4 sides the enemy will spawn from

    local dice = math.random(1, 4)

    local _x, _y  

    local _radius = 20
 
  

    -- Spawn enemy just outside one of the screen edges

    if dice == 1 then

        -- Top

        _x = math.random(0, love.graphics.getWidth())

        _y = -_radius * 4

    elseif dice == 2 then

        -- Left

        _x = -_radius * 4

        _y = math.random(0, love.graphics.getHeight())

    elseif dice == 3 then

        -- Bottom

        _x = math.random(0, love.graphics.getWidth())

        _y = love.graphics.getHeight() + _radius * 4

    elseif dice == 4 then

        -- Right

        _x = love.graphics.getWidth() + _radius * 4

        _y = math.random(0, love.graphics.getHeight())

    end

  

    return {

        level = 1,

        radius = _radius,

        x = _x,

        y = -_y,

  

        -- Move function takes player coordinates directly to avoid storing a full player object

        move = function(self, player_x, player_y)

            -- Move horizontally towards the player

            if player_x > self.x then

                self.x = self.x + self.level

            elseif player_x < self.x then

                self.x = self.x - self.level

            end

  

            -- Move vertically towards the player

            if player_y > self.y then

                self.y = self.y + self.level

            elseif player_y < self.y then

                self.y = self.y - self.level

            end

        end,

  

        -- Render the enemy as a filled circle

        draw = function(self)

            love.graphics.setColor(1, 0.5, 0.7) -- Set color to pink

            love.graphics.circle("fill", self.x, self.y, self.radius)

            love.graphics.setColor(1, 1, 1) -- Reset color to white

        end

    }

end

  

return Enemy
```
- Usage in main .lua looks like this :
	- we must use math.randomseed(os.time())
	```lua
	-- Setting the random seed using the current system time
	
	-- This makes math.random() generate different sequences of random numbers
	
	-- each time the program runs. Without this, Lua would generate the same
	
	-- "random" numbers every time you run the program.
	
	-- Useful in games to create varied behaviors like enemy spawns or item drops.
	
	-- If you want repeatable behavior (like in level generators), use a fixed seed instead.
	
	math.randomseed(os.time())
	
	```
	(تو یه دستگاه تولیدکننده‌ی کارت بازی داری. این دستگاه یه دسته کارت می‌چینه، ولی بر اساس یه عدد خاص (مثلاً 42) کارت‌ها رو به یه ترتیب خاصی می‌چینه. حالا:

	اگه دوباره همون عدد رو بهش بدی (مثلاً 42)، دقیقاً همون ترتیب کارت‌ها رو می‌سازه.
	
	اگه یه عدد دیگه بدی (مثلاً 99)، کارت‌ها رو به یه شکل متفاوت می‌چینه.
	در واقع os.time چون ثانیه از سال 1970 تا الانه همیشه متفواته پس ترتیب کارت ها متفاوت میشه)

- Example of main.lua file with only one enemy : 
``` lua
local love = require("love")

local Enemy = require("Enemy")

  

math.randomseed(os.time())

  

local player = {

    difficulty = 1,

    radius = 20,

    x = 30,

    y = 30

}

  

local game = {

    state = {

        menu = false,

        paused = false,

        running = true,

        ended = false

    }

}

  

local enemies = {}

function love.load()

    love.mouse.setVisible(false)

  

    -- insert the first enemy

    table.insert(enemies,1,Enemy())

end

  

function love.update(dt)

    player.x , player.y = love.mouse.getPosition()

  

    -- Move enemy in every dt

    for i = 1, #enemies do

        enemies[i]:move(player.x,player.y)

    end

end

  

function love.draw()

    love.graphics.printf("FPS: ".. love.timer.getFPS(), love.graphics.newFont(16),10,love.graphics.getHeight() - 50,love.graphics.getWidth())

  

    if game.state["running"] then

        love.graphics.circle("fill",player.x,player.y,player.radius)      

        -- draw enemy in every frame

        for i = 1, #enemies do

            enemies[i]:draw()

        end

    else

        love.graphics.circle("fill",player.x,player.y,player.radius / 2)      

    end

end
```