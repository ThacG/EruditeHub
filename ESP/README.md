# Erudite ESP Library V2
This is an ESP Library made by thacy on Discord, please report any bugs to me directly or on https://discord.gg/eruditehub

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
    MaxDistance = value, -- Determines the maximum distance to display the ESP (if you use studs, maximum will be in studs, if you use meters, maximum will be in meters)
    ShowChams = bool, -- Highlight the targets which can be seen through walls
    ShowTracers = bool, -- Tracers that can be seen through walls
    ShowBoxes = bool, -- Put boxes around the target that can be seen through walls (scales with size of target)
    ShowName = bool, -- Displays the name of the player/object
    ShowDistance = bool, -- Displays the distance of the player/object
    ShowHealth = bool, -- Displays the health of the player/object
    RemoveOnDeath = bool, -- Remove ESP when health is 0
    UseMeters = bool -- Use meters instead of studs
})

-- Remember to give it a variable name, which is ESP1 in this example
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

-- Updating settings of ESP1
```

## Intialise the ESP for Players (Except Yourself)
```lua
ESP1:InitialisePlayers()
```

## Intialise the ESP for All Children of Path
```lua
ESP1:InitialiseAllChildren(path)
```

## Intialise the ESP for All Descendants of Path
```lua
ESP1:InitialiseAllDescendants(path)

-- Not recommended as it may cause performance issues/crashes, make sure you know when to use it!
```

## Intialise the ESP on Humanoids for All Descendants of Path
```lua
ESP1:InitialiseHumanoids(path)

-- This is good for NPCs, Entities, Monsters etc.
```

## Intialise the ESP for a Specific Child
```lua
ESP1:InitialiseChild(parentPath, objectName)

-- All Models/BaseParts with the objectName you put will have ESP
```

## Intialise the ESP for a Specific Descendant
```lua
ESP1:InitialiseDescendant(ancestorPath, objectName)

-- All Models/BaseParts with the objectName you put will have ESP
```

## Stop the ESP
```lua
EruditeESP:ClearESP(ESP1)

-- Clears all ESP of a specific instance, which is ESP1 in this example
```

## Example
```lua
local EruditeESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/ThacG/EruditeHub/main/ESP/Library"))()

local ESP1 = EruditeESP:Init({
    TextColour = Color3.fromRGB(255, 255, 255),
    VisualColour = Color3.fromRGB(0, 255, 0),
    TextSize = 8,
    ShowChams = true,
    ShowTracers = true,
    ShowBoxes = true,
    ShowName = true,
    ShowDistance = true,
    ShowHealth = true,
    RemoveOnDeath = true,
    UseMeters = false,
    MaxDistance = 300
})

-- Using default settings for ESP2
local ESP2 = EruditeESP:Init({})

ESP1:InitialisePlayers()
ESP2:InitialiseAllChildren(game.Workspace.DroppedItems)

task.wait(5)

-- This will change the ESP colour and turn off tracers for ESP1 after 5 seconds
ESP1:UpdateSettings({
    VisualColour = Color3.fromRGB(255, 0, 0),
    ShowTracers = false
})

task.wait(5)

-- This will clear all ESP of ESP2 after another 5 seconds
EruditeESP:ClearESP(ESP2)
```
