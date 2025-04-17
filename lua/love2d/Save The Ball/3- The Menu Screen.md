
- in the main .lua file we should config these settings :
	- Making game.menu = true
	- Creating The buttons.GameState table with inserting menus
	- Handling drawing of menu screen in the love.draw method
	- Handling Enemy Spawning only in game start
	- Handling Mouse Clicking Events (using :love.mousepressed( x, y, button, istouch, presses )) => https://love2d.org/wiki/love.mousepressed
	- 

**Menu.lua**
```lua 

local love = require("love")

  

-- Button model

-- The button's width and height are set during creation (constructor-like),

-- but its position and text coordinates are set during the draw call.

function Button(text, func, func_param, width, height)

    return {

        -- Encapsulated properties with default values

        width = width or 100,

        height = height or 100,

        func = func or function()

            print("This button has no function assigned.")

        end,

        func_param = func_param,

        text = text or "No Text",

        -- Position values (will be updated during draw)

        button_x = 0,

        button_y = 0,

        text_x = 0,

        text_y = 0,

  

        -- Check if the button is being pressed (cursor is inside it)

        checkPressed = function(self, mouse_x, mouse_y, cursor_radius)

            if (mouse_x + cursor_radius >= self.button_x) and

               (mouse_x - cursor_radius <= self.button_x + self.width) and

               (mouse_y + cursor_radius >= self.button_y) and

               (mouse_y - cursor_radius <= self.button_y + self.height) then

                if self.func_param then

                    self.func(self.func_param)

                else

                    self.func()

                end

            end

        end,

  

        -- Draw the button and its text on the screen

        draw = function(self, button_x, button_y, text_x, text_y)

            self.button_x = button_x or self.button_x

            self.button_y = button_y or self.button_y

  

            -- Position text relative to button

            self.text_x = (text_x and (text_x + self.button_x)) or self.button_x

            self.text_y = (text_y and (text_y + self.button_y)) or self.button_y

  

            -- Draw button background

            love.graphics.setColor(0.6, 0.6, 0.6)

            love.graphics.rectangle("fill", self.button_x, self.button_y, self.width, self.height)

  

            -- Draw button label

            love.graphics.setColor(0, 0, 0)

            love.graphics.print(self.text, self.text_x, self.text_y)

  

            -- Reset color to white

            love.graphics.setColor(1, 1, 1)

        end

    }

end

  

return Button
```
**Main.lua**
```lua
local love = require("love")

local Enemy = require("Enemy")

local button = require("Button")

  

math.randomseed(os.time())

  

local player = {

    difficulty = 1,

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

    }

}

  

-- Button container for each game state (menu in this case)

local buttons = {

    menu_state = {}

}

  

local enemies = {}

  

-- Function to start a new game (called when "Play Game" button is pressed)

-- Switches from menu to game state and spawns the first enemy

local function startNewGame()

    game.state["menu"] = false

    game.state["running"] = true

  

    -- Spawn the first enemy only when the game starts

    table.insert(enemies, 1, Enemy())

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

        -- Move enemies during gameplay only (not in menu)

        for i = 1, #enemies do

            enemies[i]:move(player.x, player.y)

        end

    end

end

  

function love.draw()

    -- Show FPS in bottom-left

    love.graphics.printf("FPS: " .. love.timer.getFPS(), love.graphics.newFont(16), 10, love.graphics.getHeight() - 50, love.graphics.getWidth())

  

    if game.state["running"] then

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