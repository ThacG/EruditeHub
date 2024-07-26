# Erudite ESP Library V2
This is an ESP Library made by thacy on Discord, please report any bugs to me directly or on https://discord.gg/erudite

This is a lightweight and simple to use ESP Library that works on anything, while not affecting your FPS

## Booting the Library
```lua
local EruditeESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/ThacG/EruditeHub/main/ESP/Library"))()
```
## Settings
```lua
local ESP1 = EruditeESP:Init({
    TextColour = color3, -- Determines the colour of the text, such as name, hp and distance
    VisualColour = color3, -- Determines the colour of the chams, tracers and box
    TextSize = value, -- Determines the size of the text
    MaxDistance = value, -- Determines the maximum distance to display the ESP (if you use studs, maximum will be studs, if you use meters, maximum will be meters)
    ShowChams = bool, -- Highlight the players which can be seen through walls
    ShowTracers = bool, -- Tracers that can be seen through walls
    ShowBoxes = bool, -- Put boxes around the players/objects that can be seen through walls
    ShowName = bool, -- Displays the name of the player/object
    ShowDistance = bool, -- Displays the distance of the player/object
    ShowHealth = bool, -- Displays the health of the player/object
    RemoveOnDeath = bool, -- Remove ESP when health is 0
    UseMeters = bool -- Use meters instead of studs
})
```

## Update Settings
```lua
ESP1:UpdateSettings({
    TextColour = color3,
    VisualColour = color3,
    TextSize = value,
    MaxDistance = value,
    ShowChams = bool,
    ShowTracers = bool,
    ShowBoxes = bool,
    ShowName = bool,
    ShowDistance = bool,
    ShowHealth = bool,
    RemoveOnDeath = bool,
    UseMeters = bool
})
```

## Intialize the ESP for Players (Except Yourself)
```lua
EruditeESP:InitializePlayers()
```

## Intialize the ESP for a Container (All Children of Path)
```lua
EruditeESP:InitializeContainer(path)
```

## Intialize the ESP for a Specific Object
```lua
EruditeESP:InitializeContainer(parentPath, objectName)
```

## Stop the ESP
```lua
EruditeESP:ClearAllESP()
```

## Example
```lua
local EruditeESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/ThacG/EruditeHub/main/ESP/Library"))()

EruditeESP:Init({
    TextColour = Color3.fromRGB(255, 255, 255),
    VisualColour = Color3.fromRGB(255, 0, 0),
    TextSize = 8,
    MaxDistance = 300,
    ShowChams = false,
    ShowTracers = false,
    ShowBoxes = true,
    ShowName = true,
    ShowDistance = true,
    ShowHealth = true,
    RemoveOnDeath = true,
    UseMeters = false
})

EruditeESP:InitializePlayers() -- Initialize Player ESP
EruditeESP:InitializeContainer(game.Workspace.DroppedItems) -- Initialize ESP for all objects inside of game.Workspace.DroppedItems
EruditeESP:InitializeObject(game.Workspace.DroppedItems, "Lucky Potion") -- Initialize the ESP for all objects named "Lucky Potion" inside of game.Workspace.DroppedItems

task.wait(5)

EruditeESP:ClearAllESP() -- Stop all ESP after 5 seconds
```

## Note
You do not have to Init the settings if you use wish to use the default settings
```lua
local EruditeESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/ThacG/EruditeHub/main/ESP/Library"))()

EruditeESP:InitializePlayers() -- Initialize Player ESP
EruditeESP:InitializeContainer(game.Workspace.DroppedItems) -- Initialize ESP for all objects inside of game.Workspace.DroppedItems
EruditeESP:InitializeObject(game.Workspace.DroppedItems, "Lucky Potion") -- Initialize the ESP for all objects named "Lucky Potion" inside of game.Workspace.DroppedItems

task.wait(5)

EruditeESP:ClearAllESP() -- Stop all ESP after 5 seconds
```
