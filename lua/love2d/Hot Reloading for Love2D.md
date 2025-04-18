
https://github.com/usysrc/LICK.git

- add this lines of codes to main.lua file
```lua
LICK = require "lick"

-- reload love.load
LICK.reset = true
```
- The only file that we need in the repo is lick.lua file so we can move the lick.lua file from repo to another location or folder in our game folders and then import it and use it !

