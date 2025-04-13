 - **Point Of The Game :**
	 - Collision Detection
	 - How dt works
	 - How to get fps
	 - how to draw shapes
	 - Point System
- Points :
	- Using Local Variables out of the love.load() Is Better for scope 
		```lua
			 local game = {
			
			    state = {
			
			        menu = true,
			
			        paused = false,
			
			        running = false,
			
			        ended = false
			
			    }
			
			}
			
			  
			  
			
			function love.load()
			
			    love.mouse.setVisible(false)
			
			end
		```
```lua
local player = {

    radius = 20,

    x = 30,

    y = 30

}

  

local game = {

    state = {

        menu = true,

        paused = false,

        running = false,

        ended = false

    }

}

  
  

function love.load()

    love.mouse.setVisible(false)

end

  

function love.update(dt)

    player.x , player.y = love.mouse.getPosition()

end

  

function love.draw()

    love.graphics.printf("FPS: ".. love.timer.getFPS(), love.graphics.newFont(16),10,love.graphics.getHeight() - 50,love.graphics.getWidth())

  

    if game.state["menu"] then

        love.graphics.circle("fill",player.x,player.y,player.radius / 2)        

    end

    if not game.state["menu"] then

        love.graphics.circle("fill",player.x,player.y,player.radius)        

    end

end
	
```
