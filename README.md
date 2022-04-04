local Config = {
    WindowName = "Lunar Hub [paid]",
	Color = Color3.fromRGB(255,128,64),
	Keybind = Enum.KeyCode.RightControl
}

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/kickTh/New-Ui/main/im-retarded-3.txt"))()
local Window = Library:CreateWindow(Config, game:GetService("CoreGui"))

------------------------------------[Tab]----------------------------------------

local Main = Window:CreateTab("Arsenal") 
local Stats = Window:CreateTab("Stats")
local Player = Window:CreateTab("Players")
local Raid = Window:CreateTab("Raid")
local Misc = Window:CreateTab("Misc")
local Setting = Window:CreateTab("Settings")
local UI = Window:CreateTab("UI Settings")
local Hub = Window:CreateTab("Hub")

local Main = Tab1:CreateSection("AutoFarm")
local Main = Tab2:CreateSection("AutoFarm Settings")
local Section1 = Tab1:CreateSection("")
local Section2 = Tab1:CreateSection("")
local Section5 = Tab1:CreateSection("")
local Section3 = Tab2:CreateSection("Menu")
local Section4 = Tab2:CreateSection("Background")

------------------------------------[End]----------------------------------------

------------------------------------[Main]---------------------------------------

local Toggle1 = Section1:CreateToggle("Toggle", nil, function(State)
    getgenv().AimBot.Enabled = State
end)
local Slider2 = Section1:CreateSlider("Slider Radius", 0,1000,nil,false, function(Value)
    getgenv().AimBot.FOV = Value
    Circle.Radius = Value
end)


local Colorpicker3 = Section1:CreateColorpicker("Circle Color", function(Color)
    Circle.Color = Color
end)




local TextBox1 = Section2:CreateTextBox("TextBox", "Only TextBox", true, function(Value)
    TextBox = Value
end)


local Button1 = Section2:CreateButton("Button", function()
game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer) 
end)
local Toggle3 = Section3:CreateToggle("UI Toggle", nil, function(State)
	Window:Toggle(State)
end)

Toggle3:CreateKeybind(tostring(Config.Keybind):gsub("Enum.KeyCode.", ""), function(Key)
	Config.Keybind = Enum.KeyCode[Key]
end)


local Colorpicker3 = Section3:CreateColorpicker("UI Color", function(Color)
	Window:ChangeColor(Color)
end)
Colorpicker3:UpdateColor(Config.Color)


local Dropdown3 = Section4:CreateDropdown("Image")
local Option7 = Dropdown3:AddOption("Default", function(String)
	Window:SetBackground("2151741365")
end)
local Option8 = Dropdown3:AddOption("Hearts", function(String)
	Window:SetBackground("6073763717")
end)
local Option9 = Dropdown3:AddOption("Abstract", function(String)
	Window:SetBackground("6073743871")
end)
local Option10 = Dropdown3:AddOption("Hexagon", function(String)
	Window:SetBackground("6073628839")
end)
local Option11 = Dropdown3:AddOption("Circles", function(String)
	Window:SetBackground("6071579801")
end)
local Option12 = Dropdown3:AddOption("Lace With Flowers", function(String)
	Window:SetBackground("6071575925")
end)
local Option13 = Dropdown3:AddOption("Floral", function(String)
	Window:SetBackground("5553946656")
end)
Option7:SetOption()

local Colorpicker4 = Section4:CreateColorpicker("Color", function(Color)
	Window:SetBackgroundColor(Color)
end)
Colorpicker4:UpdateColor(Color3.new(1,1,1))

local Slider3 = Section4:CreateSlider("Transparency",0,1,nil,false, function(Value)
	Window:SetBackgroundTransparency(Value)
end)
Slider3:SetValue(0)

local Slider4 = Section4:CreateSlider("Tile Scale",0,1,nil,false, function(Value)
	Window:SetTileScale(Value)
end)
Slider4:SetValue(0.5)
