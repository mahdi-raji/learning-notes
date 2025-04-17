- To check whether the player has touched an enemy, we use Euclidean Distance since all entities in the game are circular.
The distance between two points (x1, y1) and (x2, y2) is calculated using:
 ``` lua
	 math.sqrt((self.x - player_x) ^ 2 +(self.y - player_y) ^ 2) <= cursor_radius * 2)
	```
)
- If this condition is true, it means the enemy and the player have collided (touched).

- Inside the game update loop, when the game state is "running", we:
```lua
if game.state["running"] then

    -- Move enemies only during active gameplay
    for i = 1, #enemies do

        -- Check if the enemy has NOT touched the player
        if not enemies[i]:checkTouched(player.x, player.y, player.radius) then
            
            -- Move the enemy toward the player
            enemies[i]:move(player.x, player.y)

            -- Check if current points match any level-up threshold
            for i = 1, #game.levels do
                if math.floor(game.points) == game.levels[i] then
                    -- Spawn a new enemy with increased difficulty
                    table.insert(enemies, 1, Enemy(game.difficulty * (i + 1)))
                    
                    -- Prevent repeated spawns at the same point
                    game.points = game.points + 1
                end
            end

        else
            -- If enemy touches the player, go back to menu
            changeGameState("menu")
        end

    end

    -- Increment game points over time
    game.points = game.points + dt
end

```
-To handle game state transitions cleanly and consistently, use a centralized function:
```lua
local function changeGameState(state)

    -- if game.state["menu"] then

    --     game.state["menu"] = true

    -- else    

    --     game.state["menu"] = false

    -- end

    game.state["menu"] = state == "menu"

    game.state["paused"] = state == "paused"

    game.state["running"] = state == "running"

    game.state["ended"] = state == "ended"

  

end
```
**Enemy.lua**
```lua
local love = require("love")

  

-- Enemy module

-- File name is capitalized to indicate it represents an object-like structure (similar to a class)

  

function Enemy(level)

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

        _y = -_radius * 2

    elseif dice == 2 then

        -- Left

        _x = -_radius * 2

        _y = math.random(0, love.graphics.getHeight())

    elseif dice == 3 then

        -- Bottom

        _x = math.random(0, love.graphics.getWidth())

        _y = love.graphics.getHeight() + _radius * 2

    elseif dice == 4 then

        -- Right

        _x = love.graphics.getWidth() + _radius * 2

        _y = math.random(0, love.graphics.getHeight())

    end

  

    return {

        level = level or 1,

        radius = _radius,

        x = _x,

        y = -_y,

  

        checkTouched = function (self,player_x,player_y,cursor_radius)

            -- Using Euclidean Distance For Distance Of Player and Enemy

            return math.sqrt((self.x - player_x) ^ 2 +(self.y - player_y) ^ 2) <= cursor_radius * 2

        end,

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
**Main.lua**
```lua
local love = require("love")

local enemy = require("Enemy")

local button = require("Button")

  

math.randomseed(os.time())

  

local player = {

    radius = 20,

    x = 30,

    y = 30

}

  

-- Game state configuration

-- Initially in menu mode

local game = {

    state = {

        menu = true,

        paused = false,

        running = false,

        ended = false

    },

    points = 0,

    difficulty = 1,

    levels = {15,30,60,120 }

}

  

-- Button container for each game state (menu in this case)

local buttons = {

    menu_state = {}

}

  

local enemies = {}

  

local function changeGameState(state)

    -- if game.state["menu"] then

    --     game.state["menu"] = true

    -- else    

    --     game.state["menu"] = false

    -- end

    game.state["menu"] = state == "menu"

    game.state["paused"] = state == "paused"

    game.state["running"] = state == "running"

    game.state["ended"] = state == "ended"

  

end

  

-- Function to start a new game (called when "Play Game" button is pressed)

-- Switches from menu to game state and spawns the first enemy

local function startNewGame()

    changeGameState("running")

    game.points = 0

    -- Spawn the first enemy only when the game starts

    enemies = {

        enemy(1)

    }

end

  

-- Handle mouse click events

function love.mousepressed(x, y, button, isTouch, presses)

    if not game.state["running"] then

        if button == 1 then -- Left click

            if game.state["menu"] then

                -- Loop through all menu buttons and check if any is clicked

                for index in pairs(buttons.menu_state) do

                    buttons.menu_state[index]:checkPressed(x, y, player.radius)

                end

            end

        end

    end

end

  

function love.load()

    love.mouse.setVisible(false)

  

    -- Initialize menu buttons and assign functions to each

    buttons.menu_state.play_game =  button("Play game", startNewGame, nil, 100, 30)

    buttons.menu_state.settings =   button("Settings", nil, nil, 100, 30)

    buttons.menu_state.exit_game =  button("Exit Game", love.event.quit, nil, 100, 30)

end

  

function love.update(dt)

    player.x, player.y = love.mouse.getPosition()

  

    if game.state["running"] then

  

        -- Move enemies only during active gameplay

        for i = 1, #enemies do

            -- Check if the enemy has NOT touched the player

            if not enemies[i]:checkTouched(player.x, player.y, player.radius) then

                -- Move the enemy toward the player

                enemies[i]:move(player.x, player.y)

                -- Check if current points match any level-up threshold

                for i = 1, #game.levels do

                    if math.floor(game.points) == game.levels[i] then

                        -- Spawn a new enemy with increased difficulty

                        table.insert(enemies, 1, Enemy(game.difficulty * (i + 1)))

                        -- Prevent repeated spawns at the same point

                        game.points = game.points + 1

                    end

                end

            else

                -- If enemy touches the player, go back to menu

                changeGameState("menu")

            end

        end

        -- Increment game points over time

        game.points = game.points + dt

    end

end

  

function love.draw()

    -- Show FPS in bottom-left

    love.graphics.printf("FPS: " .. love.timer.getFPS(), love.graphics.newFont(16), 10, love.graphics.getHeight() - 50, love.graphics.getWidth())

  
  

    if game.state["running"] then

        love.graphics.printf(math.floor(game.points), love.graphics.newFont(24),0,10,love.graphics.getWidth(),"center")

        -- Draw enemies and player during gameplay

        for i = 1, #enemies do

            enemies[i]:draw()

        end

        love.graphics.circle("fill", player.x, player.y, player.radius)

  

    elseif game.state["menu"] then

        -- Draw the main menu buttons

        buttons.menu_state.play_game:draw(30, 30, 20, 6)

        buttons.menu_state.settings:draw(30, 80, 20, 6)

        buttons.menu_state.exit_game:draw(30, 130, 20, 6)

    end

  

    -- Draw a smaller player circle when not in active game state (e.g., menu)

    if not game.state["running"] then

        love.graphics.circle("fill", player.x, player.y, player.radius / 2)

    end

end
```