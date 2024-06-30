# Erudite ESP Library V1
This is an ESP Library made by thacy on Discord, please report any bugs to me directly or on https://discord.gg/erudite
This is a lightweight and simple to use ESP Library that works on anything

## Booting the Library
```lua
local EruditeESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/ThacG/EruditeHub/main/ESP/Library"))()
```
## Settings
```lua
EruditeESP:Init({
    TextColour = color3,
    VisualColour = color3,
    TextSize = value,
    MaxDistance = value,
    ShowChams = bool,
    ShowTracers = bool,
    ShowBox = bool,
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
    ShowBox = true,
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
