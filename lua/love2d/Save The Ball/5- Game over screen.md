- To handle fonts better we will creat a table of fonts and use that instead :
	(Make sure to set the default font in draw method at first !)
```lua
local fonts = {

    medium = {

        font = love.graphics.newFont(16),

        size = 16

    },

    large = {

        font = love.graphics.newFont(24),

        size = 24

    },

    massive = {

        font = love.graphics.newFont(60),

        size = 60

    }


}

```

- To Create the game over screen
	- Add Ended state to buttons
	- config it in draw methods 
	- config the mouse click event
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

  

local fonts = {

    medium = {

        font = love.graphics.newFont(16),

        size = 16

    },

    large = {

        font = love.graphics.newFont(24),

        size = 24

    },

    massive = {

        font = love.graphics.newFont(60),

        size = 60

    }

  
  

}

-- Button container for each game state (menu in this case)

local buttons = {

    menu_state = {},

    ended_state ={}

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

            if game.state["menu"]then

                -- Loop through all menu buttons and check if any is clicked

                for index in pairs(buttons.menu_state) do

                    buttons.menu_state[index]:checkPressed(x, y, player.radius)

                end

  

            else if game.state["ended"]then

                for index in pairs(buttons.ended_state) do

                    buttons.ended_state[index]:checkPressed(x, y, player.radius)

                end

            end

            end

        end

    end

end

  

function love.load()

    love.mouse.setVisible(false)

  

    -- Initialize menu buttons and assign functions to each

    buttons.menu_state.play_game =  button("Play game", startNewGame, nil, 140, 30)

    buttons.menu_state.settings =   button("Settings", nil, nil, 140, 30)

    buttons.menu_state.exit_game =  button("Exit Game", love.event.quit, nil, 140, 30)

  

    buttons.ended_state.replay_game =  button("Replay game", startNewGame, nil, 140, 50)

    buttons.ended_state.menu =   button("Menu", changeGameState, "menu", 140, 50)

    buttons.ended_state.exit_game =  button("Exit Game", love.event.quit, nil, 140, 50)

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

                changeGameState("ended")

            end

        end

        -- Increment game points over time

        game.points = game.points + dt

    end

end

  

function love.draw()

    -- We need to set the font to default whenever we draw to ensure to reset the font after changing

    love.graphics.setFont(fonts.medium.font)

    -- Show FPS in bottom-left

    love.graphics.printf("FPS: " .. love.timer.getFPS(), fonts.medium.font, 10, love.graphics.getHeight() - 50, love.graphics.getWidth())

  
  

    if game.state["running"] then

        love.graphics.printf(math.floor(game.points),fonts.large.font,0,10,love.graphics.getWidth(),"center")

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

  

    elseif game.state["ended"] then

        love.graphics.setFont(fonts.large.font)

        buttons.ended_state.replay_game:draw(love.graphics.getWidth() / 2.25, love.graphics.getHeight() / 1.8, 10, 10)

        buttons.ended_state.menu:draw(love.graphics.getWidth() / 2.25, love.graphics.getHeight() / 1.54, 17, 10)

        buttons.ended_state.exit_game:draw(love.graphics.getWidth() / 2.25, love.graphics.getHeight() / 1.32, 1, 10)

  

    end

    -- Draw a smaller player circle when not in active game state (e.g., menu)

    if not game.state["running"] then

        love.graphics.circle("fill", player.x, player.y, player.radius / 2)

    end

end
```