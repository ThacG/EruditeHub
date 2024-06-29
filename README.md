# Erudite UI Library
```
function ExampleCode()
	--[[
		This UI was made by spons0parnordvpn on discord
		Feel free to contact me for any help
		
		How do flags works ?
		
		- Well that's easy. Flags are the identifiers we give to an item which is added to the config system.
			This identifier must be UNIQUE
			
	]]
	local EruditeLib = Library:New({
		Name = "Game Name | Erudite Hub", --\\ script name
		FolderName = "Erudite", --\\ the name of the save config folder
		Icon = 5222253854, --\\ I don't recommend any changes.
		BackgroundImage = 17681820371 --\\ I don't recommend any changes.
	})

	local MainTab = EruditeLib:CreateTab({
		Name = "Home", --\\ Tab name
		Icon = 17682712607 --\\ I don't recommend any changes.
	})
	local InactiveTab = EruditeLib:CreateTab(
		{
			Name = "Inactive"
		}
	)
	local Label = MainTab:Label({ --// Labels can act as paragraphs too.
		Text = "Erudite Hub v2 stands at the pinnacle of excellence, embodying unparalleled innovation and expertise. Its sophisticated design and cutting-edge technology ensure it remains the best choice for those seeking top-tier solutions. Elevate your experience with Erudite Hub v2, where superiority meets seamless functionality"
	})
	local Label2 = MainTab:Label({Text="Get Erudite now at .gg/erudite"}) -- Please read above for more explanations.
	-- Label:SetText(text)
	
	local Section = MainTab:Section({
		Title="Main Section" --// WARNING : Sections are not really sections, they act as separators. DO NOT PARENT ITEMS TO IT
	})
	
	local Button = MainTab:Button({
		Text = "Unleash your power", --// Button title
		Icon = 17666676829, --// Please change this icon it's so shitty
		Callback = function() --// The function to trigger when the button is pressed
			warn("You did it !")
		end
	})
	-- Button:SetText(title) or Button:SetCallback(function)
	
	local Slider = MainTab:Slider({
		Title = "My amazing slider", --// Slider title
		Speed = .15, --// I don't recommend any changes.
		Default = 10, --// Slider default value. MUST BE INTO MIN AND MAX RANGE
		Max = 10, --// Slider maximum value
		Min = 2, --// Slider minimum value 
		Flag = "slider-1", --// Flag identifier
		Callback = function(value) --// The function to trigger when slider value changes
			print("Slider value is : ", value)
		end,
	})
	-- Slider:GetValue() or Slider:Set(Number) or Slider:SetCallback(function)
	
	local Toggle = MainTab:Toggle({
		Title = "Enable cheat code", --// Toggle title
		Active = false, --// Toggle default value
		Callback = function(x) --// The function to trigger when toggle value changes
			print(x)
		end,
		Flag = "toggle-1" --// Flag identifier
	})
	-- Toggle:GetValue() or Toggle:Set(true/false)
	
	local Keybind = MainTab:Keybind({
		Flag = "keybind-1",
		Callback = function(value) --// The function to trigger when keybind value changes
			print(value) -- will return as Enum.KeyCode.value YOU MUST ASSIGN THE FUNCTION YOURSELF
		end,
		Title = "Assign a keybind"
	})
	-- Keybind:Set("E")
	local Textbox = MainTab:Textbox({
		Title = "Enter a value here",
		PlaceHolderText = "script here",
		Callback = function(text)
			print(text)
		end,
		Flag = "textbox-1"
	})

	
	local x = MainTab:Dropdown({
		Title = "Pick an option",
		Callback = function(selected)
			print(selected)
		end,
		Options = {"Option 1", "Option 2", "Option 3", "Option 4"},
		Flag = "dropdown-1"
	})

 	local xcolor = MainTab:ColorPicker({
                Title = "Hello world !",
                Callback = function(color3)
                    print(color3)
                end,
                Flag = false,
                Default = nil,
            })
		
		
	 -- Dropdown:Refresh(table)
end

ExampleCode()
wait(2)
Library:Notify("My notification", "I am ready to use", 2, true)
```
```
--[[

local Lib = Library:New()
local Tab = Lib:CreateTab()
Tab:Keybind()
local New = Lib:CreateTab()
Tab:Slider({Flag="Slider-1"})
Tab:Toggle({Flag="Idiot"})
Tab:Textbox()
Tab:ColorPicker()
Lib:Init() -- important

]]
```
