
repeat wait() until game.Players
repeat wait() until game.Players.LocalPlayer
repeat wait() until game.ReplicatedStorage
repeat wait() until game.ReplicatedStorage:FindFirstChild("Remotes");
repeat wait() until game:GetService("ReplicatedStorage").Effect.Container
repeat wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui");
repeat wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");
repeat wait() until game:GetService("Players")
repeat wait() until game:GetService("Players").LocalPlayer.Character:FindFirstChild("Energy")

wait(1)

if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end

if game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam") then
	repeat wait()
		if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
			if _G.Team == "Pirate" then
				for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
					v.Function()
				end
			elseif _G.Team == "Marine" then
				for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
					v.Function()
				end
			else
				for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
					v.Function()
				end
			end
		end
	until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded()
end

local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton.Size = UDim2.new(0, 70, 0, 70)
ImageButton.Draggable = true
ImageButton.Image = ""
ImageButton.MouseButton1Down:connect(function()
	game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
	game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)

UICorner.Parent = ImageButton

local Sound = Instance.new("Sound")
Sound.Parent = ScreenGui
Sound.SoundId = "rbxassetid://130785805"
Sound.Volume = 1

ImageButton.MouseButton1Down:Connect(function()
	Sound:Play()
end)


_G.Color = Color3.fromRGB(255, 0, 0)
_G.Logo = ""
_G.PlayerName = game.Players.LocalPlayer.Name

do  
	local ui = game:GetService("CoreGui"):FindFirstChild("UILibrary") 
	if ui then 
		ui:Destroy() 
	end 
end

local UserInputService = game:GetService("UserInputService")
local VirtualInputManager = game:GetService("VirtualInputManager")
local TweenService = game:GetService("TweenService")
local tween = game:service"TweenService"
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local GuiService = game:GetService("GuiService")

local function tablefound(ta, object)
	for i,v in pairs(ta) do
		if v == object then
			return true
		end
	end
	return false
end

local ActualTypes = {
	RoundFrame = "ImageLabel",
	Shadow = "ImageLabel",
	Circle = "ImageLabel",
	CircleButton = "ImageButton",
	Frame = "Frame",
	Label = "TextLabel",
	Button = "TextButton",
	SmoothButton = "ImageButton",
	Box = "TextBox",
	ScrollingFrame = "ScrollingFrame",
	Menu = "ImageButton",
	NavBar = "ImageButton"
}

local Properties = {
	RoundFrame = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	SmoothButton = {
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	Shadow = {
		Name = "Shadow",
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554236805",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(23,23,277,277),
		Size = UDim2.fromScale(1,1) + UDim2.fromOffset(30,30),
		Position = UDim2.fromOffset(-15,-15)
	},
	Circle = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	CircleButton = {
		BackgroundTransparency = 1,
		AutoButtonColor = false,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	Frame = {
		BackgroundTransparency = 1,
		BorderSizePixel = 0,
		Size = UDim2.fromScale(1,1)
	},
	Label = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Button = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Box = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	ScrollingFrame = {
		BackgroundTransparency = 1,
		ScrollBarThickness = 0,
		CanvasSize = UDim2.fromScale(0,0),
		Size = UDim2.fromScale(1,1)
	},
	Menu = {
		Name = "More",
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5555108481",
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromScale(1,0.5) - UDim2.fromOffset(25,10)
	},
	NavBar = {
		Name = "SheetToggle",
		Image = "http://www.roblox.com/asset/?id=5576439039",
		BackgroundTransparency = 1,
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromOffset(5,5),
		AutoButtonColor = false
	}
}

local Types = {
	"RoundFrame",
	"Shadow",
	"Circle",
	"CircleButton",
	"Frame",
	"Label",
	"Button",
	"SmoothButton",
	"Box",
	"ScrollingFrame",
	"Menu",
	"NavBar"
}

function FindType(String)
	for _, Type in next, Types do
		if Type:sub(1, #String):lower() == String:lower() then
			return Type
		end
	end
	return false
end

local Objects = {}

function Objects.new(Type)
	local TargetType = FindType(Type)
	if TargetType then
		local NewImage = Instance.new(ActualTypes[TargetType])
		if Properties[TargetType] then
			for Property, Value in next, Properties[TargetType] do
				NewImage[Property] = Value
			end
		end
		return NewImage
	else
		return Instance.new(Type)
	end
end

local function GetXY(GuiObject)
	local Max, May = GuiObject.AbsoluteSize.X, GuiObject.AbsoluteSize.Y
	local Px, Py = math.clamp(Mouse.X - GuiObject.AbsolutePosition.X, 0, Max), math.clamp(Mouse.Y - GuiObject.AbsolutePosition.Y, 0, May)
	return Px/Max, Py/May
end

local function CircleAnim(GuiObject, EndColour, StartColour)
	local PX, PY = GetXY(GuiObject)
	local Circle = Objects.new("Shadow")
	Circle.Size = UDim2.fromScale(0,0)
	Circle.Position = UDim2.fromScale(PX,PY)
	Circle.ImageColor3 = StartColour or GuiObject.ImageColor3
	Circle.ZIndex = 200
	Circle.Parent = GuiObject
	local Size = GuiObject.AbsoluteSize.X
	TweenService:Create(Circle, TweenInfo.new(0.5), {Position = UDim2.fromScale(PX,PY) - UDim2.fromOffset(Size/2,Size/2), ImageTransparency = 1, ImageColor3 = EndColour, Size = UDim2.fromOffset(Size,Size)}):Play()
	spawn(function()
		wait(0.5)
		Circle:Destroy()
	end)
end

local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos =
			UDim2.new(
				StartPosition.X.Scale,
				StartPosition.X.Offset + Delta.X,
				StartPosition.Y.Scale,
				StartPosition.Y.Offset + Delta.Y
			)
		local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end

local UIConfig = {Bind = Enum.KeyCode.RightControl}
local chars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
local length = 20
local randomString = ""

math.randomseed(os.time())

charTable = {}
for c in chars:gmatch "." do
	table.insert(charTable, c)
end

for i = 1, length do
	randomString = randomString .. charTable[math.random(1, #charTable)]
end

for i, v in pairs(game.CoreGui:WaitForChild("RobloxGui"):WaitForChild("Modules"):GetChildren()) do
	if v.ClassName == "ScreenGui" then
		for i1, v1 in pairs(v:GetChildren()) do
			if v1.Name == "Main" then
				do
					local ui = v
					if ui then
						ui:Destroy()
					end
				end
			end
		end
	end
end
function CircleClick(Button, X, Y)
	coroutine.resume(
		coroutine.create(
			function()
				local Circle = Instance.new("ImageLabel")
				Circle.Parent = Button
				Circle.Name = "Circle"
				Circle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Circle.BackgroundTransparency = 1.000
				Circle.ZIndex = 10
				Circle.Image = "rbxassetid://266543268"
				Circle.ImageColor3 = Color3.fromRGB(255, 255, 255)
				Circle.ImageTransparency = 0.7
				local NewX = X - Circle.AbsolutePosition.X
				local NewY = Y - Circle.AbsolutePosition.Y
				Circle.Position = UDim2.new(0, NewX, 0, NewY)

				local Time = 0.2
				Circle:TweenSizeAndPosition(
					UDim2.new(0, 30.25, 0, 30.25),
					UDim2.new(0, NewX - 15, 0, NewY - 10),
					"Out",
					"Quad",
					Time,
					false,
					nil
				)
				for i = 1, 10 do
					Circle.ImageTransparency = Circle.ImageTransparency + 0.01
					wait(Time / 10)
				end
				Circle:Destroy()
			end
		)
	)
end
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
function dragify(Frame, object)
	dragToggle = nil
	dragSpeed = .25
	dragInput = nil
	dragStart = nil
	dragPos = nil

	function updateInput(input)
		Delta = input.Position - dragStart
		Position =
			UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
		game:GetService("TweenService"):Create(object, TweenInfo.new(dragSpeed), {Position = Position}):Play()
	end

	Frame.InputBegan:Connect(
		function(input)
			if
				(input.UserInputType == Enum.UserInputType.MouseButton1 or
					input.UserInputType == Enum.UserInputType.Touch)
			then
				dragToggle = true
				dragStart = input.Position
				startPos = object.Position
				input.Changed:Connect(
					function()
						if (input.UserInputState == Enum.UserInputState.End) then
							dragToggle = false
						end
					end
				)
			end
		end
	)

	Frame.InputChanged:Connect(
		function(input)
			if
				(input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch)
			then
				dragInput = input
			end
		end
	)

	game:GetService("UserInputService").InputChanged:Connect(
	function(input)
		if (input == dragInput and dragToggle) then
			updateInput(input)
		end
	end
	)
end

local UI = Instance.new("ScreenGui")
UI.Name = randomString
UI.Parent = game.CoreGui:WaitForChild("RobloxGui"):WaitForChild("Modules")
UI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

library = {}

function library:Destroy()
	library:Destroy()
end



function library:Evil(text,text2,logo)
	local Main = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local Top = Instance.new("Frame")
	local TabHolder = Instance.new("Frame")
	local UICorner_2 = Instance.new("UICorner")
	local TabContainer = Instance.new("ScrollingFrame")
	local UIListLayout = Instance.new("UIListLayout")
	local UIPadding = Instance.new("UIPadding")
	local Logo = Instance.new("ImageLabel")
	local Title = Instance.new("TextLabel")
	local Title2 = Instance.new("TextLabel")
	local Welcome = Instance.new("TextLabel")

	Main.Name = "Main"
	Main.Parent = UI
	Main.BackgroundColor3 = Color3.fromRGB(5, 5, 5)
	Main.Position = UDim2.new(0.5, 0, 0.5, 0)
	Main.Size = UDim2.new(0, 0, 0, 0)
	Main.ClipsDescendants = true
	Main.AnchorPoint = Vector2.new(0.5, 0.5)

	Main:TweenSize(UDim2.new(0,550,0,335),"Out","Quad",0.4,true)

	local Top2 = Instance.new("Frame")
	Top2.Name = "Top2"
	Top2.Parent = Main
	Top2.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
	Top2.BackgroundTransparency = 0
	Top2.Position = UDim2.new(0, 0, 0, 0)
	Top2.Size = UDim2.new(0, 550, 0, 45)

	local UICorner_59 = Instance.new("UICorner")
	UICorner_59.CornerRadius = UDim.new(0, 5)
	UICorner_59.Parent = Top2


	Logo.Name = "Logo"
	Logo.Parent = Main
	Logo.Active = true
	Logo.AnchorPoint = Vector2.new(0,0)
	Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Logo.BackgroundTransparency = 1.000
	Logo.Position = UDim2.new(0, 2, 0, 0)
	Logo.Size = UDim2.new(0, 45, 0, 45)
	Logo.ImageTransparency = 0
	Logo.Image = "rbxassetid://"..(logo or 13732317842)

	Title.Name = "Title"
	Title.Parent = Main
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.Position = UDim2.new(0, 45, 0, 10)
	Title.Size = UDim2.new(0, 483, 0, 31)
	Title.Font = Enum.Font.GothamMedium
	Title.Text = text
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextSize = 17.000
	Title.TextWrapped = true
	Title.TextXAlignment = Enum.TextXAlignment.Left

	Title2.Name = "Title2"
	Title2.Parent = Main
	Title2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title2.BackgroundTransparency = 1.000
	Title2.Position = UDim2.new(0, 102, 0, 10)
	Title2.Size = UDim2.new(0, 483, 0, 31)
	Title2.Font = Enum.Font.GothamMedium
	Title2.Text = text2
	Title2.TextColor3 = _G.Color
	Title2.TextSize = 17.000
	Title2.TextWrapped = true
	Title2.TextXAlignment = Enum.TextXAlignment.Left

	local UiToggle_UiStroke1 = Instance.new("UIStroke")

	UiToggle_UiStroke1.Color = Color3.fromRGB(25,25,25)
	UiToggle_UiStroke1.Thickness = 2
	UiToggle_UiStroke1.Name = "UiToggle_UiStroke1"
	UiToggle_UiStroke1.Parent = Main

	UICorner.CornerRadius = UDim.new(0, 6)
	UICorner.Parent = Main

	Top.Name = "Top"
	Top.Parent = Main
	Top.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Top.BackgroundTransparency = 1
	Top.Position = UDim2.new(0.021956088, 0, 0, 10)
	Top.Size = UDim2.new(0, 565, 0, 39)

	local ClickFrame = Instance.new("Frame")
	ClickFrame.Name = "Top"
	ClickFrame.Parent = Main
	ClickFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ClickFrame.BackgroundTransparency = 1
	ClickFrame.Position = UDim2.new(0, 0, 0, 0)
	ClickFrame.Size = UDim2.new(0, 600, 0, 35)

	TabHolder.Name = "TabHolder"
	TabHolder.Parent = Top
	TabHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TabHolder.Position = UDim2.new(0, 120, 0, 0)
	TabHolder.BackgroundTransparency = 1.000
	TabHolder.Size = UDim2.new(0, 450, 0, 38)

	UICorner_2.Parent = TabHolder

	TabContainer.Name = "TabContainer"
	TabContainer.Parent = TabHolder
	TabContainer.Active = true
	TabContainer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TabContainer.BackgroundTransparency = 1.000
	TabContainer.Size = UDim2.new(0, 450, 0, 38)
	TabContainer.CanvasSize = UDim2.new(2, 0, 0, 0)
	TabContainer.ScrollBarThickness = 1
	TabContainer.VerticalScrollBarInset = Enum.ScrollBarInset.Always

	UIListLayout.Parent = TabContainer
	UIListLayout.FillDirection = Enum.FillDirection.Horizontal
	UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
	UIListLayout.Padding = UDim.new(0, 10)
	UIListLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(
	function()
		TabContainer.CanvasSize = UDim2.new(0, UIListLayout.AbsoluteContentSize.X, 0, 0)
	end)
	UIPadding.Parent = TabContainer
	UIPadding.PaddingLeft = UDim.new(0, 5)
	UIPadding.PaddingTop = UDim.new(0, 5)
	local Bottom = Instance.new("Frame")
	Bottom.Name = "Bottom"
	Bottom.Parent = Main
	Bottom.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
	Bottom.BackgroundTransparency = 1.000
	Bottom.Position = UDim2.new(0.0119760484, 7, 0, 55)
	Bottom.Size = UDim2.new(0, 500, 0, 320)

	local uitoggled = false
	UserInputService.InputBegan:Connect(
		function(io, p)
			if io.KeyCode == UIConfig.Bind then
				if uitoggled == false then
					Main:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, 0.4, true) wait(0.4) UI.Enabled = false
					uitoggled = true
				else
					UI.Enabled = true
					Main:TweenSize(UDim2.new(0, 550, 0, 335), Enum.EasingDirection.Out, Enum.EasingStyle.Quart,0.4,true)
					uitoggled = false
				end
			end
		end
	)

	dragify(ClickFrame, Main)
	local tabs = {}
	local S = false
	function tabs:CraftTab(Name,icon)
		local FrameTab = Instance.new("Frame")
		local Tab = Instance.new("TextButton")
		local UICorner_3 = Instance.new("UICorner")
		local UICorner_Tab = Instance.new("UICorner")
		local ImageLabel = Instance.new("ImageLabel")
		local TextLabel = Instance.new("TextLabel")
		icon = 123

		FrameTab.Name = "FrameTab"
		FrameTab.Parent = Tab
		FrameTab.BackgroundColor3 = _G.Color
		FrameTab.BackgroundTransparency = 0
		FrameTab.Position = UDim2.new(0, 10, 0, 22)
		--FrameTab.Size = UDim2.new(0, 80, 0, 2)
		FrameTab.Size = UDim2.new(0, 0, 0, 2)
		FrameTab.Visible = false

		UICorner_Tab.CornerRadius = UDim.new(0, 3)
		UICorner_Tab.Parent = FrameTab

		Tab.Name = "Tab"
		Tab.Parent = TabContainer
		Tab.BackgroundColor3 = Color3.fromRGB(13, 13, 13)
		Tab.Size = UDim2.new(0, 80, 0, 20)
		Tab.BackgroundTransparency = 1.00
		Tab.Text = ""
		UICorner_3.CornerRadius = UDim.new(0, 3)
		UICorner_3.Parent = Tab

		ImageLabel.Parent = Tab
		ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ImageLabel.Position = UDim2.new(0, 5, 0.2, 0)
		ImageLabel.Size = UDim2.new(0, 20, 0, 30)
		ImageLabel.Image = "http://www.roblox.com/asset/?id=" .. icon
		ImageLabel.ImageColor3 = Color3.fromRGB(255, 255, 255)
		ImageLabel.ImageTransparency = 0.2
		ImageLabel.BackgroundTransparency = 1

		TextLabel.Parent = Tab
		TextLabel.Text = Name.." "

		TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TextLabel.BackgroundTransparency = 1.000
		TextLabel.Position = UDim2.new(0, 10, 0, 0)
		TextLabel.Size = UDim2.new(0, 80, 0, 30)
		TextLabel.Font = Enum.Font.GothamBold
		TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
		TextLabel.TextSize = 12.300
		TextLabel.TextTransparency = 0.200

		if TextLabel.Name == Name.." " then
			Tab.Size = UDim2.new(0, 60 + TextLabel.TextBounds.X, 0, 15)
		end

		local Sound = Instance.new("Sound")
		Sound.Parent = Tab
		Sound.SoundId = "rbxassetid://130785805"
		Sound.Volume = 1

		Tab.MouseButton1Down:Connect(function()
			Sound:Play()
		end)


		local Page = Instance.new("ScrollingFrame")
		local Left = Instance.new("ScrollingFrame")
		local Right = Instance.new("ScrollingFrame")
		local UIListLayout_5 = Instance.new("UIListLayout")
		local UIPadding_5 = Instance.new("UIPadding")

		Page.Name = "Page"
		Page.Parent = Bottom
		Page.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Page.BackgroundTransparency = 1.000
		Page.Size = UDim2.new(0, 600, 0, 350)
		Page.ScrollBarThickness = 0
		Page.CanvasSize = UDim2.new(0, 0, 0, 0)
		Page.Visible = false

		Left.Name = "Left"
		Left.Parent = Page
		Left.Active = true
		Left.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Left.BackgroundTransparency = 10
		Left.Size = UDim2.new(0, 255, 0, 255)
		Left.ScrollBarThickness = 0
		Left.CanvasSize = UDim2.new(0, 0, 0, 0)

		Right.Name = "Right"
		Right.Parent = Page
		Right.Active = true
		Right.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Right.BackgroundTransparency = 10
		Right.Size = UDim2.new(0, 255, 0, 255)
		Right.ScrollBarThickness = 0
		Right.CanvasSize = UDim2.new(0, 0, 0, 0)

		local LeftList = Instance.new("UIListLayout")
		local RightList = Instance.new("UIListLayout")

		LeftList.Parent = Left
		LeftList.SortOrder = Enum.SortOrder.LayoutOrder
		LeftList.Padding = UDim.new(0, 5)

		RightList.Parent = Right
		RightList.SortOrder = Enum.SortOrder.LayoutOrder
		RightList.Padding = UDim.new(0, 5)

		UIListLayout_5.Parent = Page
		UIListLayout_5.FillDirection = Enum.FillDirection.Horizontal
		UIListLayout_5.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout_5.Padding = UDim.new(0, 13)

		UIPadding_5.Parent = Page

		if S == false then
			S = true
			Page.Visible = true
			TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
			TextLabel.TextTransparency = 0
			ImageLabel.ImageTransparency = 0
			ImageLabel.ImageColor3 = Color3.fromRGB(255, 255, 255)
			FrameTab.Size = UDim2.new(0, 80, 0, 2)
			FrameTab.Visible = true
		end

		Tab.MouseButton1Click:Connect(
			function()
				for _, x in next, TabContainer:GetChildren() do
					if x.Name == "Tab" then
						TweenService:Create(
							x.TextLabel,
							TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextColor3 = Color3.fromRGB(255, 255, 255)}
						):Play()
						TweenService:Create(
							x.ImageLabel,
							TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageColor3 = Color3.fromRGB(255, 255, 255)}
						):Play()
						TweenService:Create(
							x.ImageLabel,
							TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageTransparency = 0.2}
						):Play()
						TweenService:Create(
							x.TextLabel,
							TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextTransparency = 0.2}
						):Play()
						TweenService:Create(
							x.FrameTab,
							TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 0, 0, 2)}
						):Play()
						for index, y in next, Bottom:GetChildren() do
							TweenService:Create(
								y,
								TweenInfo.new(0.2,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
								{Position = UDim2.new(0,1500,0,0)}
							):Play()
							y.Visible = false
						end
						x.FrameTab.Visible = false
					end
				end
				TweenService:Create(
					TextLabel,
					TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(255, 255, 255)}
				):Play()
				TweenService:Create(
					ImageLabel,
					TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{ImageColor3 = Color3.fromRGB(255, 255, 255)}
				):Play()
				TweenService:Create(
					ImageLabel,
					TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{ImageTransparency = 0}
				):Play()
				TweenService:Create(
					TextLabel,
					TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
				FrameTab.Visible = true
				TweenService:Create(
					FrameTab,
					TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 80, 0, 2)}
				):Play()
				TweenService:Create(
					Page,
					TweenInfo.new(0.2,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{Position = UDim2.new(0,1,0,0)}
				):Play()
				Page.Visible = true
			end
		)

		local function GetType(value)
			if value == 1 then
				return Left
			elseif value == 2 then
				return Right
			else
				return Left
			end
		end

		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				Right.CanvasSize = UDim2.new(0,0,0,RightList.AbsoluteContentSize.Y + 5)
				Left.CanvasSize = UDim2.new(0,0,0,LeftList.AbsoluteContentSize.Y + 5)
			end)
		end)

		local sections = {}
		function sections:CraftPage(Name,side)

			if side == nil then
				return Left
			end

			local Section = Instance.new("Frame")
			local UICorner_5 = Instance.new("UICorner")
			local Top_2 = Instance.new("Frame")
			local Line = Instance.new("Frame")
			local Sectionname = Instance.new("TextLabel")
			local SectionContainer = Instance.new("Frame")
			local SectionContainer_2 = Instance.new("Frame")
			local UIListLayout_2 = Instance.new("UIListLayout")
			local UIPadding_2 = Instance.new("UIPadding")

			Section.Name = "Section"
			Section.Parent = GetType(side)
			Section.BackgroundColor3 = Color3.fromRGB(7, 7, 7)
			Section.ClipsDescendants = true
			Section.Transparency = 0
			Section.Size = UDim2.new(0, 150, 0, 400)

			UICorner_5.CornerRadius = UDim.new(0, 5)
			UICorner_5.Parent = Section

			Top_2.Name = "Top"
			Top_2.Parent = Section
			Top_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Top_2.BackgroundTransparency = 1.000
			Top_2.BorderColor3 = Color3.fromRGB(27, 42, 53)
			Top_2.Size = UDim2.new(0, 200, 0, 31)

			Line.Name = "Line"
			Line.Parent = Top_2
			Line.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Line.BorderSizePixel = 0
			Line.Size = UDim2.new(0, 200, 0, 1)

			Sectionname.Name = "Sectionname"
			Sectionname.Parent = Top_2
			Sectionname.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Sectionname.BackgroundTransparency = 1.000
			Sectionname.Position = UDim2.new(0.0591227226, 0, 0.0222222228, 0)
			Sectionname.Size = UDim2.new(0, 224, 0, 24)
			Sectionname.Font = Enum.Font.GothamBold
			Sectionname.Text = Name
			Sectionname.TextColor3 = _G.Color
			Sectionname.TextSize = 14.000
			Sectionname.TextTransparency = 0
			Sectionname.TextXAlignment = Enum.TextXAlignment.Left

			SectionContainer.Name = "SectionContainer"
			SectionContainer.Parent = Top_2
			SectionContainer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SectionContainer.BackgroundTransparency = 1.000
			SectionContainer.BorderSizePixel = 0
			SectionContainer.Position = UDim2.new(0, 0, 0.796416223, 0)
			SectionContainer.Size = UDim2.new(0, 200, 0, 318)

			SectionContainer_2.Name = "SectionContainer_2"
			SectionContainer_2.Parent = Top_2
			SectionContainer_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SectionContainer_2.BackgroundTransparency = 1.000
			SectionContainer_2.BorderSizePixel = 0
			SectionContainer_2.Position = UDim2.new(0, 0, 0.796416223, 0)
			SectionContainer_2.Size = UDim2.new(0, 200, 0, 318)

			UIListLayout_2.Parent = SectionContainer
			UIListLayout_2.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout_2.Padding = UDim.new(0, 10)

			UIPadding_2.Parent = SectionContainer
			UIPadding_2.PaddingLeft = UDim.new(0, 5)

			UIListLayout_2:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(
			function()

				Section.Size = UDim2.new(1, 0, 0, UIListLayout_2.AbsoluteContentSize.Y + 35)
			end
			)

			local functionitem = {}

			function functionitem:Label(text)
				local textas = {}
				local Label = Instance.new("Frame")
				local Text = Instance.new("TextLabel")
				Label.Name = "Label"
				Label.Parent = SectionContainer
				Label.AnchorPoint = Vector2.new(0.5, 0.5)
				Label.BackgroundTransparency = 1.000
				Label.Size = UDim2.new(0, 265, 0, 30)

				local Label22 = Instance.new("Frame")
				Label22.Name = "Label22"
				Label22.Parent = Label
				Label22.AnchorPoint = Vector2.new(0, 0.5)
				Label22.BackgroundColor3 = _G.Color
				Label22.Position = UDim2.new(0,0,0.5,0)
				Label22.Size = UDim2.new(0, 45, 0, 2)

				local Label23 = Instance.new("Frame")
				Label23.Name = "Label23"
				Label23.Parent = Label
				Label23.AnchorPoint = Vector2.new(0, 0.5)
				Label23.BackgroundColor3 = _G.Color
				Label23.Position = UDim2.new(0,200,0.5,0)
				Label23.Size = UDim2.new(0, 45, 0, 2)

				Text.Name = "Text"
				Text.Parent = Label
				Text.AnchorPoint = Vector2.new(0.5, 0.5)
				Text.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Text.BackgroundTransparency = 1.000
				Text.Position = UDim2.new(0.5, 0, 0.5, 0)
				Text.Size = UDim2.new(0, 53, 0, 150)
				Text.ZIndex = 16
				Text.Font = Enum.Font.GothamBold
				Text.Text = text
				Text.TextColor3 = Color3.fromRGB(255, 255, 255)
				Text.TextSize = 12.000
				function textas.Refresh(newtext)
					Text.Text = newtext
				end
				return textas
			end

			function functionitem:LabelLog(text)
				local textas = {}
				local Label = Instance.new("Frame")
				local Text = Instance.new("TextLabel")
				Label.Name = "Label"
				Label.Parent = SectionContainer
				Label.AnchorPoint = Vector2.new(0.5, 0.5)
				Label.BackgroundTransparency = 1.000
				Label.Size = UDim2.new(0, 265, 0, 30)

				Text.Name = "Text"
				Text.Parent = Label
				Text.AnchorPoint = Vector2.new(0.5, 0.5)
				Text.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Text.BackgroundTransparency = 1.000
				Text.Position = UDim2.new(0.5, 0, 0.5, 0)
				Text.Size = UDim2.new(0, 53, 0, 12)
				Text.ZIndex = 16
				Text.Font = Enum.Font.GothamBold
				Text.Text = text
				Text.TextColor3 = Color3.fromRGB(255, 255, 255)
				Text.TextSize = 12.000
				function textas:Refresh(newtext)
					Text.Text = newtext
				end
				function textas:Color(Color)
					Text.TextColor3 = Color
				end
				return textas
			end

			function functionitem:ButtonTog(Title, default, callback)
				local b3Func = {}
				local callback = callback or function()
				end
				local Tgs = default
				local Button_2 = Instance.new("Frame")
				local UICorner_21 = Instance.new("UICorner")
				local TextLabel_4 = Instance.new("TextLabel")
				local TextButton_4 = Instance.new("TextButton")

				Button_2.Name = "Button"
				Button_2.Parent = SectionContainer
				Button_2.BackgroundColor3 = Color3.fromRGB(33, 132, 112)
				Button_2.Size = UDim2.new(0, 265, 0, 30)
				Button_2.ZIndex = 16

				if default then
					Button_2.BackgroundColor3 = Color3.fromRGB(33, 132, 112)
				else
					Button_2.BackgroundColor3 = _G.Color
				end

				UICorner_21.CornerRadius = UDim.new(0, 4)
				UICorner_21.Parent = Button_2

				TextLabel_4.Parent = Button_2
				TextLabel_4.AnchorPoint = Vector2.new(0.5, 0.5)
				TextLabel_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextLabel_4.BackgroundTransparency = 1.000
				TextLabel_4.Position = UDim2.new(0.5, 0, 0.5, 0)
				TextLabel_4.Size = UDim2.new(0, 40, 0, 12)
				TextLabel_4.ZIndex = 16
				TextLabel_4.Font = Enum.Font.GothamBold
				TextLabel_4.Text = tostring(Title)
				TextLabel_4.TextColor3 = Color3.fromRGB(255, 255, 255)
				TextLabel_4.TextSize = 12.000

				TextButton_4.Parent = Button_2
				TextButton_4.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
				TextButton_4.BackgroundTransparency = 1.000
				TextButton_4.BorderSizePixel = 0
				TextButton_4.ClipsDescendants = true
				TextButton_4.Size = UDim2.new(1, 0, 1, 0)
				TextButton_4.ZIndex = 16
				TextButton_4.AutoButtonColor = false
				TextButton_4.Font = Enum.Font.Gotham
				TextButton_4.Text = ""
				TextButton_4.TextColor3 = Color3.fromRGB(255, 255, 255)
				TextButton_4.TextSize = 14.000

				TextButton_4.MouseButton1Click:Connect(
					function()
						Tgs = not Tgs
						b3Func:Update(Tgs)
						CircleClick(Button_2, Mouse.X, Mouse.Y)
					end
				)

				if default then
					TweenService:Create(
						Button_2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{
							BackgroundColor3 = state and _G.Color or Color3.fromRGB(33, 132, 112)
						}
					):Play()
					callback(default)
					Tgs = default
				end
				function b3Func:Update(state)
					TweenService:Create(
						Button_2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{
							BackgroundColor3 = state and Color3.fromRGB(33, 132, 112) or _G.Color
						}
					):Play()
					callback(state)
					Tgs = state
				end

				return b3Func
			end

			function functionitem:Button(text,callback)

				local ButtonFrame = Instance.new("Frame")

				ButtonFrame.Name = "ButtonFrame"
				ButtonFrame.Parent = SectionContainer
				ButtonFrame.BackgroundColor3 = _G.Color
				ButtonFrame.BorderSizePixel = 0
				ButtonFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
				ButtonFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				ButtonFrame.Size = UDim2.new(0, 213, 0, 25) -- UDim2.new(0, 213, 0, 35)
				ButtonFrame.BackgroundTransparency  = 1
				ButtonFrame.ClipsDescendants = true



				local MheeFrameStroke = Instance.new("UIStroke")

				MheeFrameStroke.Thickness = 0
				MheeFrameStroke.Name = ""
				MheeFrameStroke.Parent = ButtonFrame
				MheeFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
				MheeFrameStroke.Color = _G.Color
				MheeFrameStroke.Transparency = 0.7

				local Button = Instance.new("TextButton")

				Button.Parent = ButtonFrame
				Button.Name = "Button"
				Button.BackgroundColor3 = _G.Color
				Button.Size = UDim2.new(0,150, 0, 30)
				Button.Font = Enum.Font.SourceSansSemibold
				Button.Text = tostring(text)
				Button.TextColor3 = Color3.fromRGB(155, 155, 155)
				Button.TextSize = 13.000
				Button.AnchorPoint = Vector2.new(0.5, 0.5)
				Button.Position = UDim2.new(0.6, 0, 0.5, 0)
				Button.TextXAlignment = Enum.TextXAlignment.Center
				Button.BackgroundTransparency = 0.6
				Button.TextWrapped = true
				Button.AutoButtonColor = false
				Button.ClipsDescendants = true

				local ConnerPageMhee = Instance.new("UICorner")

				ConnerPageMhee.CornerRadius = UDim.new(0, 4)
				ConnerPageMhee.Name = ""
				ConnerPageMhee.Parent = Button

				Button.MouseEnter:Connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size =  UDim2.new(0, 170, 0, 25)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)
				Button.MouseLeave:Connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size =  UDim2.new(0, 150, 0, 25)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.6} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						Button,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				Button.MouseButton1Click:Connect(function()
					CircleClick(Button, Mouse.X, Mouse.Y)
					Button.TextSize = 0
					TweenService:Create(
						Button,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextSize = 12}
					):Play()
					callback()
				end)

			end



			function functionitem:Toggle(text,config,callback)
				local Toggle = Instance.new("Frame")

				Toggle.Name = "Toggle"
				Toggle.Parent = SectionContainer
				Toggle.Active = true
				Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.BackgroundTransparency = 1
				Toggle.BorderColor3 = Color3.fromRGB(27, 42, 53)
				Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
				Toggle.Size = UDim2.new(0, 250, 0, 35)

				local TextButton_Toggle = Instance.new("TextButton")
				TextButton_Toggle.Name = "TextButton_Toggle"
				TextButton_Toggle.Parent = Toggle
				TextButton_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextButton_Toggle.BackgroundTransparency = 1.000
				TextButton_Toggle.Size = UDim2.new(0, 213, 0, 35)
				TextButton_Toggle.Font = Enum.Font.SourceSansSemibold
				TextButton_Toggle.Text = " "
				TextButton_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_Toggle.TextSize = 14.000

				local TextButton_2_Toggle = Instance.new("TextButton")

				TextButton_2_Toggle.Name = "TextButton_2_Toggle"
				TextButton_2_Toggle.Parent = TextButton_Toggle
				TextButton_2_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_2_Toggle.BackgroundColor3 = Color3.fromRGB(5,5,5)
				TextButton_2_Toggle.BorderSizePixel = 0
				TextButton_2_Toggle.Position = UDim2.new(0.0807512328, 0, 0.5, 0)
				TextButton_2_Toggle.Size = UDim2.new(0, 21, 0, 21)
				TextButton_2_Toggle.AutoButtonColor = false
				TextButton_2_Toggle.Font = Enum.Font.SourceSansSemibold
				TextButton_2_Toggle.Text = " "
				TextButton_2_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_2_Toggle.TextSize = 14.000

				local Main_UiStroke = Instance.new("UIStroke")

				Main_UiStroke.Thickness = 1
				Main_UiStroke.Name = ""
				Main_UiStroke.Parent = TextButton_2_Toggle
				Main_UiStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
				Main_UiStroke.LineJoinMode = Enum.LineJoinMode.Round
				Main_UiStroke.Color = Color3.fromRGB(0, 0, 0)
				Main_UiStroke.Transparency = 0

				local TextButton_2_Toggle2 = Instance.new("TextButton")

				TextButton_2_Toggle2.Name = "TextButton_2_Toggle"
				TextButton_2_Toggle2.Parent = TextButton_2_Toggle
				TextButton_2_Toggle2.BackgroundColor3 = Color3.fromRGB(7,7,7)
				TextButton_2_Toggle2.BorderSizePixel = 0
				TextButton_2_Toggle2.BackgroundTransparency = 1
				TextButton_2_Toggle2.Position = UDim2.new(0.0807512328, 0, 0.5, 0)
				TextButton_2_Toggle2.Size = UDim2.new(0, 21, 0, 21)
				TextButton_2_Toggle2.AutoButtonColor = false
				TextButton_2_Toggle2.Font = Enum.Font.SourceSansSemibold
				TextButton_2_Toggle2.Text = " "
				TextButton_2_Toggle2.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_2_Toggle2.TextSize = 14.000

				local UICorner2 = Instance.new("UICorner")

				UICorner2.CornerRadius = UDim.new(0, 5)
				UICorner2.Parent = TextButton_2_Toggle2

				local UICorner = Instance.new("UICorner")

				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = TextButton_2_Toggle

				local ImageButton = Instance.new("ImageButton")

				ImageButton.Parent = TextButton_2_Toggle
				ImageButton.AnchorPoint = Vector2.new(0.5, 0.5)
				ImageButton.BackgroundColor3 = Color3.fromRGB(16, 255, 96)
				ImageButton.Image = "http://www.roblox.com/asset/?id=6023426926"
				ImageButton.BackgroundTransparency = 0
				ImageButton.BorderSizePixel = 0
				ImageButton.AutoButtonColor = false
				ImageButton.Position = UDim2.new(0.5, 0, 0.5, 0)
				ImageButton.Size = UDim2.new(0, 0, 0, 0)

				local UICorner6 = Instance.new("UICorner")

				UICorner6.CornerRadius = UDim.new(0, 5)
				UICorner6.Parent = ImageButton

				local TextLabel_Toggle = Instance.new("TextLabel")

				TextLabel_Toggle.Name = "TextLabel_Toggle"
				TextLabel_Toggle.Parent = Toggle
				TextLabel_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextLabel_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextLabel_Toggle.BackgroundTransparency = 1
				TextLabel_Toggle.Position = UDim2.new(0.55, 0, 0.5, 0)
				TextLabel_Toggle.Size = UDim2.new(0, 200, 0, 25)
				TextLabel_Toggle.Font = Enum.Font.SourceSansSemibold
				TextLabel_Toggle.TextColor3 = Color3.fromRGB(155, 155, 155)
				TextLabel_Toggle.TextSize = 14.000
				TextLabel_Toggle.Text = text
				TextLabel_Toggle.TextWrapped = true
				TextLabel_Toggle.TextXAlignment = Enum.TextXAlignment.Left

				TextButton_Toggle.MouseEnter:Connect(function()
					TweenService:Create(
						TextLabel_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255,255,255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextButton_2_Toggle2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(10,10,10)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end)

				TextButton_Toggle.MouseLeave:Connect(function()
					TweenService:Create(
						TextLabel_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextButton_2_Toggle2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(7,7,7)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end)
				local check = {toogle = false ; loacker = true ; togfunction = {

				};}

				TextButton_Toggle.MouseButton1Click:Connect(function()
					if check.toogle == false and check.loacker == true  then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 21, 0, 21)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					elseif  check.loacker ==  true then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 0, 0, 0)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					if  check.loacker == true  then
						check.toogle = not check.toogle
						callback(check.toogle)
					end
				end)

				TextButton_2_Toggle.MouseButton1Click:Connect(function()
					if check.toogle == false and check.loacker == true  then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 21, 0, 21)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					elseif  check.loacker ==  true then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 0, 0, 0)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					if  check.loacker == true  then
						check.toogle = not check.toogle
						callback(check.toogle)
					end
				end)

				TextButton_2_Toggle2.MouseButton1Click:Connect(function()
					if check.toogle == false and check.loacker == true  then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 21, 0, 21)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					elseif  check.loacker ==  true then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 0, 0, 0)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					if  check.loacker == true  then
						check.toogle = not check.toogle
						callback(check.toogle)
					end
				end)

				ImageButton.MouseButton1Click:Connect(function()
					if check.toogle == false and check.loacker == true  then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 21, 0, 21)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					elseif  check.loacker ==  true then
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						wait(0.1)
						TweenService:Create(
							ImageButton,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 0, 0, 0)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					if  check.loacker == true  then
						check.toogle = not check.toogle
						callback(check.toogle)
					end
				end)

				if config == true then
					TweenService:Create(
						ImageButton,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 25, 0, 25)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					wait(0.1)
					TweenService:Create(
						ImageButton,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 21, 0, 21)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					check.toogle = true
					callback(check.toogle)
				end
				local lockerframe = Instance.new("Frame")

				lockerframe.Name = "lockerframe"
				lockerframe.Parent = Toggle
				lockerframe.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				lockerframe.BackgroundTransparency = 1
				lockerframe.BorderSizePixel = 0
				lockerframe.Size = UDim2.new(0, 300, 0, 35)
				lockerframe.Position = UDim2.new(0.5, 0, 0.5, 0)
				lockerframe.AnchorPoint = Vector2.new(0.5, 0.5)

				local LockerImageLabel = Instance.new("ImageLabel")
				LockerImageLabel.Parent = lockerframe
				LockerImageLabel.BackgroundTransparency = 1.000
				LockerImageLabel.BorderSizePixel = 0
				LockerImageLabel.Position = UDim2.new(0.45, 0, 0.5, 0)
				LockerImageLabel.AnchorPoint = Vector2.new(0.5, 0.5)
				LockerImageLabel.Size = UDim2.new(0, 0, 0, 0)
				LockerImageLabel.Image = "http://www.roblox.com/asset/?id=6031082533"

				function check.togfunction:lock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 0.7}
					):Play()
					wait(0.5)
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.2, Enum.EasingStyle.Bounce, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 25, 0, 25)}
					):Play()

					check.loacker  = false
				end
				function check.togfunction:unlock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 1}
					):Play()
					wait(0.5)
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.2, Enum.EasingStyle.Bounce, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 0, 0, 0)}
					):Play()
					check.loacker  = true
				end
				return  check.togfunction
			end

			function functionitem:Textbox(text,text2,callback)
				local TextFrame = Instance.new("Frame")

				TextFrame.Name = "TextFrame"
				TextFrame.Parent = SectionContainer
				TextFrame.BackgroundColor3 =  Color3.fromRGB(7, 7, 7)
				TextFrame.BorderSizePixel = 0
				TextFrame.Position = UDim2.new(0.6, 0, 0.5, 0)
				TextFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				TextFrame.Size = UDim2.new(0, 213, 0, 70)
				TextFrame.BackgroundTransparency  = 1
				TextFrame.ClipsDescendants = true

				local LabelNameSliderxd = Instance.new("TextLabel")

				LabelNameSliderxd.Parent = TextFrame
				LabelNameSliderxd.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelNameSliderxd.BackgroundTransparency = 1
				LabelNameSliderxd.BorderSizePixel = 0
				LabelNameSliderxd.Position = UDim2.new(0.6, 0, 0.1, 0)
				LabelNameSliderxd.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelNameSliderxd.Size = UDim2.new(0, 160, 0, 20)
				LabelNameSliderxd.Font = Enum.Font.SourceSansSemibold
				LabelNameSliderxd.Text = tostring(text)
				LabelNameSliderxd.TextColor3 = Color3.fromRGB(155, 155, 155)
				LabelNameSliderxd.TextSize = 11.000
				LabelNameSliderxd.TextXAlignment = Enum.TextXAlignment.Center

				local ConerTextBox = Instance.new("UICorner")

				ConerTextBox.CornerRadius = UDim.new(0, 4)
				ConerTextBox.Name = ""
				ConerTextBox.Parent = TextFrame

				local FrameBox = Instance.new("Frame")

				FrameBox.Name = "TextFrame"
				FrameBox.Parent = TextFrame
				FrameBox.BackgroundColor3 =  Color3.fromRGB(15, 15, 15)
				FrameBox.BorderSizePixel = 0
				FrameBox.Position = UDim2.new(0.6, 0, 0.5)
				FrameBox.AnchorPoint = Vector2.new(0.5, 0.5)
				FrameBox.Size = UDim2.new(0, 158, 0, 30)
				FrameBox.BackgroundTransparency  = 0.2
				FrameBox.ClipsDescendants = true
				FrameBox.AnchorPoint = Vector2.new(0.5, 0.5)

				local TextFrame2 = Instance.new("TextBox")

				TextFrame2.Parent = FrameBox
				TextFrame2.BackgroundColor3 = _G.Color
				TextFrame2.BorderSizePixel = 0
				TextFrame2.ClipsDescendants = true
				TextFrame2.Position = UDim2.new(0.5, 0, 0.5)
				TextFrame2.AnchorPoint = Vector2.new(0.5, 0.5)
				TextFrame2.Size = UDim2.new(0, 158, 0, 35)
				TextFrame2.Font = Enum.Font.SourceSansSemibold
				TextFrame2.PlaceholderColor3 = Color3.fromRGB(155, 155, 155)
				TextFrame2.PlaceholderText = text2
				TextFrame2.Text = ""
				TextFrame2.TextColor3 = Color3.fromRGB(155, 155, 155)
				TextFrame2.TextSize = 14.000
				TextFrame2.BackgroundTransparency = 1

				local ConerTextBox2 = Instance.new("UICorner")

				ConerTextBox2.CornerRadius = UDim.new(0, 4)
				ConerTextBox2.Name = ""
				ConerTextBox2.Parent = FrameBox

				local TextBoxStroke = Instance.new("UIStroke")

				TextBoxStroke.Thickness = 1
				TextBoxStroke.Name = ""
				TextBoxStroke.Parent = FrameBox
				TextBoxStroke.LineJoinMode = Enum.LineJoinMode.Round
				TextBoxStroke.Color = _G.Color
				TextBoxStroke.Transparency = 0.7


				TextFrame.MouseEnter:Connect(function()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 170, 0, 30)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = _G.Color} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextFrame2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{PlaceholderColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextFrame2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelNameSliderxd,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextBoxStroke,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Thickness = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				TextFrame.MouseLeave:Connect(function()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 158, 0, 30)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(23, 23, 23)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextFrame2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{PlaceholderColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextBoxStroke,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Thickness = 1} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelNameSliderxd,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextFrame2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)
				TextFrame2.FocusLost:Connect(function ()
					if #TextFrame2.Text > 0 then
						pcall(callback,TextFrame2.Text)
					end
				end)
			end

			function functionitem:Dropdown(text, list, default, callback)
				local Dropfunc = {}

				local MainDropDown = Instance.new("Frame")
				local UICorner_7 = Instance.new("UICorner")
				local MainDropDown_2 = Instance.new("Frame")
				local UICorner_8 = Instance.new("UICorner")
				local v = Instance.new("TextButton")
				local Text_2 = Instance.new("TextLabel")
				local ImageButton = Instance.new("ImageButton")
				local Scroll_Items = Instance.new("ScrollingFrame")
				local UIListLayout_3 = Instance.new("UIListLayout")
				local UIPadding_3 = Instance.new("UIPadding")

				local MainDropDown_3 = Instance.new("Frame")
				MainDropDown_3.Name = "MainDropDown"
				MainDropDown_3.Parent = SectionContainer
				MainDropDown_3.BackgroundColor3 = Color3.fromRGB(1, 2, 3)
				MainDropDown_3.Position = UDim2.new(0,0,2,0)
				MainDropDown_3.BackgroundTransparency = 1
				MainDropDown_3.BorderSizePixel = 0
				MainDropDown_3.ClipsDescendants = true
				MainDropDown_3.Size = UDim2.new(0, 240, 0, 15)
				MainDropDown_3.ZIndex = 16

				local Text_3 = Instance.new("TextLabel")

				Text_3.Name = "Text_3"
				Text_3.Parent = MainDropDown_3
				Text_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Text_3.BackgroundTransparency = 1.000
				Text_3.Size = UDim2.new(0, 62, 0, 12)
				Text_3.ZIndex = 16
				Text_3.Font = Enum.Font.SourceSansSemibold
				Text_3.Text = text
				Text_3.TextColor3 = Color3.fromRGB(255, 255, 255)
				Text_3.TextSize = 12.000
				Text_3.TextXAlignment = Enum.TextXAlignment.Left

				MainDropDown_2.Name = "MainDropDown"
				MainDropDown_2.Parent = MainDropDown
				MainDropDown_2.BackgroundColor3 = Color3.fromRGB(1, 2, 3)
				MainDropDown_2.BackgroundTransparency = 0.700
				MainDropDown_2.BorderSizePixel = 0
				MainDropDown_2.ClipsDescendants = true
				MainDropDown_2.Size = UDim2.new(1, 0, 0, 35)
				MainDropDown_2.ZIndex = 16

				UICorner_8.CornerRadius = UDim.new(0, 4)
				UICorner_8.Parent = MainDropDown_2

				MainDropDown.Name = "MainDropDown"
				MainDropDown.Parent = SectionContainer
				MainDropDown.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				MainDropDown.BackgroundTransparency = 0.700
				MainDropDown.BorderSizePixel = 0
				MainDropDown.ClipsDescendants = true
				MainDropDown.Size = UDim2.new(0, 240, 0, 35)
				MainDropDown.ZIndex = 16

				UICorner_7.CornerRadius = UDim.new(0, 4)
				UICorner_7.Parent = MainDropDown


				v.Name = "v"
				v.Parent = MainDropDown_2
				v.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				v.BackgroundTransparency = 1.000
				v.BorderSizePixel = 0
				v.Size = UDim2.new(1, 0, 1, 0)
				v.ZIndex = 16
				v.AutoButtonColor = false
				v.Font = Enum.Font.SourceSansSemibold
				v.Text = ""
				v.TextColor3 = Color3.fromRGB(255, 255, 255)
				v.TextSize = 12.000
				function getpro()
					if default then
						if table.find(list, default) then
							callback(default)
							return default
						else
							return ""
						end
					else
						return ""
					end
				end
				Text_2.Name = "Text"
				Text_2.Parent = MainDropDown_2
				Text_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Text_2.BackgroundTransparency = 1.000
				Text_2.Size = UDim2.new(0, 240, 0, 35)
				Text_2.ZIndex = 16
				Text_2.Font = Enum.Font.SourceSansSemibold
				Text_2.Text = getpro()
				Text_2.TextColor3 = Color3.fromRGB(255, 255, 255)
				Text_2.TextSize = 13.000
				Text_2.TextXAlignment = Enum.TextXAlignment.Center

				local Main_ImageButton = Instance.new("Frame")
				Main_ImageButton.Name = "Main_ImageButton"
				Main_ImageButton.AnchorPoint = Vector2.new(0, 0.5)
				Main_ImageButton.Parent = MainDropDown_2
				Main_ImageButton.BackgroundColor3  = Color3.fromRGB(40, 40, 40)
				Main_ImageButton.Size = UDim2.new(0, 20, 0, 20)
				Main_ImageButton.Position = UDim2.new(1, -25, 0.5, 1)
				Main_ImageButton.ZIndex = 16

				ImageButton.Parent = Main_ImageButton
				ImageButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ImageButton.BackgroundTransparency = 1
				ImageButton.Position = UDim2.new(0, 3, 0, 5)
				ImageButton.Size = UDim2.new(0, 13, 0, 13)
				ImageButton.ZIndex = 16
				ImageButton.Image = "http://www.roblox.com/asset/?id=6282522798"

				local UICorner_35 = Instance.new("UICorner")
				UICorner_35.CornerRadius = UDim.new(0, 5)
				UICorner_35.Parent = Main_ImageButton

				Scroll_Items.Name = "Scroll_Items"
				Scroll_Items.Parent = MainDropDown
				Scroll_Items.Active = true
				Scroll_Items.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Scroll_Items.BackgroundTransparency = 1.000
				Scroll_Items.BorderSizePixel = 0
				Scroll_Items.Position = UDim2.new(0, 0, 0, 35)
				Scroll_Items.Size = UDim2.new(1, 0, 1, -35)
				Scroll_Items.ZIndex = 16
				Scroll_Items.CanvasSize = UDim2.new(0, 0, 0, 240)
				Scroll_Items.ScrollBarThickness = 0

				UIListLayout_3.Parent = Scroll_Items
				UIListLayout_3.SortOrder = Enum.SortOrder.LayoutOrder
				UIListLayout_3.Padding = UDim.new(0, 5)
				UIListLayout_2:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(
				function()
					Scroll_Items.CanvasSize = UDim2.new(1, 0, 0, UIListLayout_2.AbsoluteContentSize.Y+40)
				end
				)
				UIPadding_3.Parent = Scroll_Items
				UIPadding_3.PaddingLeft = UDim.new(0, 10)
				UIPadding_3.PaddingTop = UDim.new(0, 5)

				function Dropfunc:TogglePanel(state)
					TweenService:Create(
						MainDropDown,
						TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = state and UDim2.new(0, 240, 0, 299) or UDim2.new(0, 240, 0, 35)}
					):Play()
					TweenService:Create(
						ImageButton,
						TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = state and 180 or 0}
					):Play()
				end
				local Tof = false
				ImageButton.MouseButton1Click:Connect(
					function()
						Tof = not Tof
						Dropfunc:TogglePanel(Tof)
					end
				)
				v.MouseButton1Click:Connect(
					function()
						Tof = not Tof
						Dropfunc:TogglePanel(Tof)
					end
				)
				function Dropfunc:Clear()
					for i, v in next, Scroll_Items:GetChildren() do
						if v:IsA("TextButton") then 
							v:Destroy()
						end
					end
				end

				function Dropfunc:Add(Text)
					local _5 = Instance.new("TextButton")
					local UICorner_9 = Instance.new("UICorner")
					_5.Name = Text
					_5.Parent = Scroll_Items
					_5.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
					_5.BorderSizePixel = 0
					_5.ClipsDescendants = true
					_5.Size = UDim2.new(1, -10, 0, 30)
					_5.ZIndex = 17
					_5.AutoButtonColor = false
					_5.Font = Enum.Font.GothamBold
					_5.Text = Text
					_5.TextColor3 = Color3.fromRGB(255, 255, 255)
					_5.TextSize = 12.000

					UICorner_9.CornerRadius = UDim.new(0, 4)
					UICorner_9.Parent = _5

					_5.MouseButton1Click:Connect(
						function()
							if _x == nil then
								Tof = false
								Dropfunc:TogglePanel(Tof)
								callback(Text)
								Text_2.Text = Text
								_x = nil
							end
						end
					)
				end
				for i, v in next, list do
					Dropfunc:Add(v)
				end


				return Dropfunc
			end

			function functionitem:Seperator(text)
				local Label = Instance.new("TextLabel")
				local PaddingLabel = Instance.new("UIPadding")
				local labell = {}

				Label.Name = "Label"
				Label.Parent = SectionContainer
				Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Label.BackgroundTransparency = 1.000
				Label.Position = UDim2.new(0, 0, 0.5, 0)
				Label.Size = UDim2.new(0, 470, 0, 20)
				Label.Font = Enum.Font.SourceSansSemibold
				Label.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label.TextSize = 14.000
				Label.Text = text
				Label.TextXAlignment = Enum.TextXAlignment.Left

				PaddingLabel.PaddingLeft = UDim.new(0,15)
				PaddingLabel.Parent = Label
				PaddingLabel.Name = "PaddingLabel"

				function labell:Set(newtext)
					Label.Text = newtext
				end

				return labell
			end

			function functionitem:Slider(text,floor,min,max,de,callback)
				local SliderFrame = Instance.new("Frame")
				local LabelNameSlider = Instance.new("TextLabel")
				local ShowValueFrame = Instance.new("Frame")
				local CustomValue = Instance.new("TextBox")
				local ShowValueFrameUICorner = Instance.new("UICorner")
				local ValueFrame = Instance.new("Frame")
				local ValueFrameUICorner = Instance.new("UICorner")
				local PartValue = Instance.new("Frame")
				local PartValueUICorner = Instance.new("UICorner")
				local MainValue = Instance.new("Frame")
				local MainValueUICorner = Instance.new("UICorner")
				local sliderfunc = {}

				SliderFrame.Name = "SliderFrame"
				SliderFrame.Parent = SectionContainer
				SliderFrame.BackgroundColor3 = Color3.fromRGB(7, 7, 7)
				SliderFrame.Position = UDim2.new(0.109489053, 0, 0.708609283, 0)
				SliderFrame.Size = UDim2.new(0, 250, 0, 45)

				local UICorner_7 = Instance.new("UICorner")
				UICorner_7.CornerRadius = UDim.new(0, 4)
				UICorner_7.Parent = SliderFrame

				LabelNameSlider.Name = "LabelNameSlider"
				LabelNameSlider.Parent = SliderFrame
				LabelNameSlider.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelNameSlider.BackgroundTransparency = 1.000
				LabelNameSlider.Position = UDim2.new(0.0729926974, 0, 0.0396823473, 0)
				LabelNameSlider.Size = UDim2.new(0, 182, 0, 25)
				LabelNameSlider.Font = Enum.Font.GothamBold
				LabelNameSlider.Text = tostring(text)
				LabelNameSlider.TextColor3 = Color3.fromRGB(255, 255, 255)
				LabelNameSlider.TextSize = 11.000
				LabelNameSlider.TextXAlignment = Enum.TextXAlignment.Left

				ShowValueFrame.Name = "ShowValueFrame"
				ShowValueFrame.Parent = SliderFrame
				ShowValueFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				ShowValueFrame.Position = UDim2.new(0.733576655, 0, 0.0656082779, 0)
				ShowValueFrame.Size = UDim2.new(0, 58, 0, 21)

				CustomValue.Name = "CustomValue"
				CustomValue.Parent = ShowValueFrame
				CustomValue.AnchorPoint = Vector2.new(0.5, 0.5)
				CustomValue.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
				CustomValue.Position = UDim2.new(0.5, 0, 0.5, 0)
				CustomValue.Size = UDim2.new(0, 55, 0, 21)
				CustomValue.Font = Enum.Font.GothamBold
				CustomValue.Text = "50"
				CustomValue.TextColor3 = Color3.fromRGB(255, 255, 255)
				CustomValue.TextSize = 11.000

				local UICorner_7 = Instance.new("UICorner")
				UICorner_7.CornerRadius = UDim.new(0, 4)
				UICorner_7.Parent = CustomValue

				ShowValueFrameUICorner.CornerRadius = UDim.new(0, 4)
				ShowValueFrameUICorner.Name = "ShowValueFrameUICorner"
				ShowValueFrameUICorner.Parent = ShowValueFrame

				ValueFrame.Name = "ValueFrame"
				ValueFrame.Parent = SliderFrame
				ValueFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				ValueFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
				ValueFrame.Position = UDim2.new(0.5, 0, 0.8, 0)
				ValueFrame.Size = UDim2.new(0, 200, 0, 5)

				ValueFrameUICorner.CornerRadius = UDim.new(0, 30)
				ValueFrameUICorner.Name = "ValueFrameUICorner"
				ValueFrameUICorner.Parent = ValueFrame

				PartValue.Name = "PartValue"
				PartValue.Parent = ValueFrame
				PartValue.AnchorPoint = Vector2.new(0.5, 0.5)
				PartValue.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
				PartValue.BackgroundTransparency = 1.000
				PartValue.Position = UDim2.new(0.5, 0, 0.8, 0)
				PartValue.Size = UDim2.new(0, 200, 0, 5)

				PartValueUICorner.CornerRadius = UDim.new(0, 30)
				PartValueUICorner.Name = "PartValueUICorner"
				PartValueUICorner.Parent = PartValue

				MainValue.Name = "MainValue"
				MainValue.Parent = ValueFrame
				MainValue.BackgroundColor3 = _G.Color
				MainValue.Size = UDim2.new((de or 0) / max, 0, 0, 5)
				MainValue.BorderSizePixel = 0

				MainValueUICorner.CornerRadius = UDim.new(0, 30)
				MainValueUICorner.Name = "MainValueUICorner"
				MainValueUICorner.Parent = MainValue


				local ConneValue = Instance.new("Frame")
				ConneValue.Name = "ConneValue"
				ConneValue.Parent = PartValue
				ConneValue.AnchorPoint = Vector2.new(0.7, 0.7)
				ConneValue.BackgroundColor3 = _G.Color
				ConneValue.Position = UDim2.new((de or 0)/max, 0.5, 0.5,0, 0)
				ConneValue.Size = UDim2.new(0, 10, 0, 10)
				ConneValue.BorderSizePixel = 0

				local UICorner = Instance.new("UICorner")
				UICorner.CornerRadius = UDim.new(0, 10)
				UICorner.Parent = ConneValue


				if floor == true then
					CustomValue.Text =  tostring(de and string.format((de / max) * (max - min) + min) or 0)
				else
					CustomValue.Text =  tostring(de and math.floor((de / max) * (max - min) + min) or 0)
				end

				local function move(input)
					local pos =
						UDim2.new(
							math.clamp((input.Position.X - ValueFrame.AbsolutePosition.X) / ValueFrame.AbsoluteSize.X, 0, 1),
							0,
							0.5,
							0
						)
					local pos1 =
						UDim2.new(
							math.clamp((input.Position.X - ValueFrame.AbsolutePosition.X) / ValueFrame.AbsoluteSize.X, 0, 1),
							0,
							0,
							5
						)
					MainValue:TweenSize(pos1, "Out", "Sine", 0.2, true)
					ConneValue:TweenPosition(pos, "Out", "Sine", 0.2, true)
					if floor == true then
						local value = string.format("%.0f",((pos.X.Scale * max) / max) * (max - min) + min)
						CustomValue.Text = tostring(value)
						callback(value)
					else
						local value = math.floor(((pos.X.Scale * max) / max) * (max - min) + min)
						CustomValue.Text = tostring(value)
						callback(value)
					end
				end
				local dragging = false
				ConneValue.InputBegan:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = true
						end
					end)
				ConneValue.InputEnded:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = false
						end
					end)
				SliderFrame.InputBegan:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = true
						end
					end)
				SliderFrame.InputEnded:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = false
						end
					end)
				ValueFrame.InputBegan:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = true
						end
					end)
				ValueFrame.InputEnded:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							dragging = false
						end
					end)
				game:GetService("UserInputService").InputChanged:Connect(function(input)
					if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
						move(input)
					end
				end)
				CustomValue.FocusLost:Connect(function()
					if CustomValue.Text == "" then
						CustomValue.Text  = de
					end
					if  tonumber(CustomValue.Text) > max then
						CustomValue.Text  = max
					end
					MainValue:TweenSize(UDim2.new((CustomValue.Text or 0) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
					ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0.6, 0) , "Out", "Sine", 0.2, true)
					if floor == true then
						CustomValue.Text = tostring(CustomValue.Text and string.format("%.0f",(CustomValue.Text / max) * (max - min) + min) )
					else
						CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
					end
					pcall(callback, CustomValue.Text)
				end)

				function sliderfunc:Update(value)
					MainValue:TweenSize(UDim2.new((value or 0) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
					ConneValue:TweenPosition(UDim2.new((value or 0)/max, 0.5, 0.5,0, 0) , "Out", "Sine", 0.2, true)
					CustomValue.Text = value
					pcall(function()
						callback(value)
					end)
				end
				return sliderfunc
			end
			return functionitem
		end
		return sections
	end
	return tabs
end

--Script

if game.PlaceId == 2753915549 then
	World1 = true
elseif game.PlaceId == 4442272183 then
	World2 = true
elseif game.PlaceId == 7449423635 then
	World3 = true
end

local function QuestCheck()
	local Lvl = game:GetService("Players").LocalPlayer.Data.Level.Value
	if Lvl >= 1 and Lvl <= 9 then
		if tostring(game.Players.LocalPlayer.Team) == "Marines" then
			MobName = "Trainee [Lv. 5]"
			QuestName = "MarineQuest"
			QuestLevel = 1
			Mon = "Trainee"
			NPCPosition = CFrame.new(-2709.67944, 24.5206585, 2104.24585, -0.744724929, -3.97967455e-08, -0.667371571, 4.32403588e-08, 1, -1.07884304e-07, 0.667371571, -1.09201515e-07, -0.744724929)
		elseif tostring(game.Players.LocalPlayer.Team) == "Pirates" then
			MobName = "Bandit [Lv. 5]"
			Mon = "Bandit"
			QuestName = "BanditQuest1"
			QuestLevel = 1
			NPCPosition = CFrame.new(1059.99731, 16.9222069, 1549.28162, -0.95466274, 7.29721794e-09, 0.297689587, 1.05190106e-08, 1, 9.22064114e-09, -0.297689587, 1.19340022e-08, -0.95466274)
		end
		return {
			[1] = QuestLevel,
			[2] = NPCPosition,
			[3] = MobName,
			[4] = QuestName,
			[5] = LevelRequire,
			[6] = Mon,
			[7] = MobCFrame
		}
	end

	if Lvl >= 375 and Lvl <= 399 then -- Fishman Warrior
		MobName = "Fishman Warrior [Lv. 375]"
		QuestName = "FishmanQuest"
		QuestLevel = 1
		Mon = "Fishman Warrior"
		NPCPosition = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
		MobCFrame = CFrame.new(60955.0625, 48.7988472, 1543.7168, -0.831178129, 6.20639318e-09, -0.556006253, 7.20035302e-08, 1, -9.64761853e-08, 0.556006253, -1.20223305e-07, -0.831178129)
		if _G.Auto_Farm_Level and (NPCPosition.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
		end
		return {
			[1] = QuestLevel,
			[2] = NPCPosition,
			[3] = MobName,
			[4] = QuestName,
			[5] = LevelRequire,
			[6] = Mon,
			[7] = MobCFrame
		}
	end

	if Lvl >= 15 and Lvl <= 29 then
		MobName = "Gorilla [Lv. 20]"
		QuestName = "JungleQuest"
		QuestLevel = 2
		Mon = "Gorilla"
		NPCPosition = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
		MobCFrame = CFrame.new(-1142.0293, 40.5877495, -516.118103, 0.55559355, 7.58965513e-08, 0.831454039, 1.24594361e-08, 1, -9.96073553e-08, -0.831454039, 6.57006538e-08, 0.55559355)
		return {
			[1] = QuestLevel,
			[2] = NPCPosition,
			[3] = MobName,
			[4] = QuestName,
			[5] = LevelRequire,
			[6] = Mon,
			[7] = MobCFrame
		}
	end

	if Lvl >= 400 and Lvl <= 449 then -- Fishman Commando
		MobName = "Fishman Commando [Lv. 400]"
		QuestName = "FishmanQuest"
		QuestLevel = 2
		Mon = "Fishman Commando"
		NPCPosition = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
		MobCFrame = CFrame.new(61872.3008, 75.5976562, 1394.83484, -0.922134459, 4.36911973e-09, -0.38686946, -2.54707899e-08, 1, 7.20052e-08, 0.38686946, 7.62523484e-08, -0.922134459)
		if _G.Auto_Farm_Level and (NPCPosition.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
		end
		return {
			[1] = QuestLevel,
			[2] = NPCPosition,
			[3] = MobName,
			[4] = QuestName,
			[5] = LevelRequire,
			[6] = Mon,
			[7] = MobCFrame
		}
	end

	--game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
	local GuideModule = require(game:GetService("ReplicatedStorage").GuideModule)
	local Quests = require(game:GetService("ReplicatedStorage").Quests)
	for i,v in pairs(GuideModule["Data"]["NPCList"]) do
		for i1,v1 in pairs(v["Levels"]) do
			if Lvl >= v1 then
				if not LevelRequire then
					LevelRequire = 0
				end
				if v1 > LevelRequire then
					NPCPosition = i["CFrame"]
					QuestLevel = i1
					LevelRequire = v1
				end
				if #v["Levels"] == 3 and QuestLevel == 3 then
					NPCPosition = i["CFrame"]
					QuestLevel = 2
					LevelRequire = v["Levels"][2]
				end
			end
		end
	end
	for i,v in pairs(Quests) do
		for i1,v1 in pairs(v) do
			if v1["LevelReq"] == LevelRequire and i ~= "CitizenQuest" then
				QuestName = i
				for i2,v2 in pairs(v1["Task"]) do
					MobName = i2
					Mon = string.split(i2," [Lv. ".. v1["LevelReq"] .. "]")[1]
				end
			end
		end
	end
	if QuestName == "MarineQuest2" then
		QuestName = "MarineQuest2"
		QuestLevel = 1
		MobName = "Chief Petty Officer [Lv. 120]"
		Mon = "Chief Petty Officer"
		LevelRequire = 120
	elseif QuestName == "ImpelQuest" then
		QuestName = "PrisonerQuest"
		QuestLevel = 2
		MobName = "Dangerous Prisoner [Lv. 190]"
		Mon = "Dangerous Prisoner"
		LevelRequire = 210
		NPCPosition = CFrame.new(5310.60547, 0.350014925, 474.946594, 0.0175017118, 0, 0.999846935, 0, 1, 0, -0.999846935, 0, 0.0175017118)
	elseif QuestName == "SkyExp1Quest" then
		if QuestLevel == 1 then
			NPCPosition = CFrame.new(-4721.88867, 843.874695, -1949.96643, 0.996191859, -0, -0.0871884301, 0, 1, -0, 0.0871884301, 0, 0.996191859)
		elseif QuestLevel == 2 then
			NPCPosition = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
		end
	elseif QuestName == "Area2Quest" and QuestLevel == 2 then
		QuestName = "Area2Quest"
		QuestLevel = 1
		MobName = "Swan Pirate [Lv. 775]"
		Mon = "Swan Pirate"
		LevelRequire = 775
	end
	MobName = MobName:sub(1,#MobName)

	return {
		[1] = QuestLevel,
		[2] = NPCPosition,
		[3] = MobName,
		[4] = QuestName,
		[5] = LevelRequire,
		[6] = Mon,
		[7] = MobCFrame
	}
end


function CheckBossQuest()
	if _G.Select_Boss == "Saber Expert [Lv. 200] [Boss]" then
		MsBoss = "Saber Expert [Lv. 200] [Boss]"
		NameBoss = "Saber Expert"
		CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
	elseif _G.Select_Boss == "The Saw [Lv. 100] [Boss]" then
		MsBoss = "The Saw [Lv. 100] [Boss]"
		NameBoss = "The Saw"
		CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
	elseif _G.Select_Boss == "Greybeard [Lv. 750] [Raid Boss]" then
		MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
		NameBoss = "Greybeard"
		CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
	elseif _G.Select_Boss == "The Gorilla King [Lv. 25] [Boss]" then
		MsBoss = "The Gorilla King [Lv. 25] [Boss]"
		NameBoss = "The Gorilla King"
		NameQuestBoss = "JungleQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
		CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
	elseif _G.Select_Boss == "Bobby [Lv. 55] [Boss]" then
		MsBoss = "Bobby [Lv. 55] [Boss]"
		NameBoss = "Bobby"
		NameQuestBoss = "BuggyQuest1"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
		CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
	elseif _G.Select_Boss == "Yeti [Lv. 110] [Boss]" then
		MsBoss = "Yeti [Lv. 110] [Boss]"
		NameBoss = "Yeti"
		NameQuestBoss = "SnowQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
		CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
	elseif _G.Select_Boss == "Mob Leader [Lv. 120] [Boss]" then
		MsBoss = "Mob Leader [Lv. 120] [Boss]"
		NameBoss = "Mob Leader"
		CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
	elseif _G.Select_Boss == "Vice Admiral [Lv. 130] [Boss]" then
		MsBoss = "Vice Admiral [Lv. 130] [Boss]"
		NameBoss = "Vice Admiral"
		NameQuestBoss = "MarineQuest2"
		LevelQuestBoss = 2
		CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
		CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
	elseif _G.Select_Boss == "Warden [Lv. 175] [Boss]" then
		MsBoss = "Warden [Lv. 175] [Boss]"
		NameBoss = "Warden"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 1
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Chief Warden [Lv. 200] [Boss]" then
		MsBoss = "Chief Warden [Lv. 200] [Boss]"
		NameBoss = "Chief Warden"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 2
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Swan [Lv. 225] [Boss]" then
		MsBoss = "Swan [Lv. 225] [Boss]"
		NameBoss = "Swan"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Magma Admiral [Lv. 350] [Boss]" then
		MsBoss = "Magma Admiral [Lv. 350] [Boss]"
		NameBoss = "Magma Admiral"
		NameQuestBoss = "MagmaQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
		CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
	elseif _G.Select_Boss == "Fishman Lord [Lv. 425] [Boss]" then
		MsBoss = "Fishman Lord [Lv. 425] [Boss]"
		NameBoss = "Fishman Lord"
		NameQuestBoss = "FishmanQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
		CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
	elseif _G.Select_Boss == "Wysper [Lv. 500] [Boss]" then
		MsBoss = "Wysper [Lv. 500] [Boss]"
		NameBoss = "Wysper"
		NameQuestBoss = "SkyExp1Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
		CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
	elseif _G.Select_Boss == "Thunder God [Lv. 575] [Boss]" then
		MsBoss = "Thunder God [Lv. 575] [Boss]"
		NameBoss = "Thunder God"
		NameQuestBoss = "SkyExp2Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
		CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
	elseif _G.Select_Boss == "Cyborg [Lv. 675] [Boss]" then
		MsBoss = "Cyborg [Lv. 675] [Boss]"
		NameBoss = "Cyborg"
		NameQuestBoss = "FountainQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
		CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
		-- New World
	elseif _G.Select_Boss == "Diamond [Lv. 750] [Boss]" then
		MsBoss = "Diamond [Lv. 750] [Boss]"
		NameBoss = "Diamond"
		NameQuestBoss = "Area1Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
		CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
	elseif _G.Select_Boss == "Jeremy [Lv. 850] [Boss]" then
		MsBoss = "Jeremy [Lv. 850] [Boss]"
		NameBoss = "Jeremy"
		NameQuestBoss = "Area2Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
		CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
	elseif _G.Select_Boss == "Fajita [Lv. 925] [Boss]" then
		MsBoss = "Fajita [Lv. 925] [Boss]"
		NameBoss = "Fajita"
		NameQuestBoss = "MarineQuest3"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
		CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
	elseif _G.Select_Boss == "Don Swan [Lv. 1000] [Boss]" then
		MsBoss = "Don Swan [Lv. 1000] [Boss]"
		NameBoss = "Don Swan"
		CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
	elseif _G.Select_Boss == "Smoke Admiral [Lv. 1150] [Boss]" then
		MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
		NameBoss = "Smoke Admiral"
		NameQuestBoss = "IceSideQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
		CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
	elseif _G.Select_Boss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
		MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
		NameBoss = "Cursed Captain"
		CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
	elseif _G.Select_Boss == "Darkbeard [Lv. 1000] [Raid Boss]" then
		MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
		NameBoss = "Darkbeard"
		CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
	elseif _G.Select_Boss == "Order [Lv. 1250] [Raid Boss]" then
		MsBoss = "Order [Lv. 1250] [Raid Boss]"
		NameBoss = "Order"
		CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
	elseif _G.Select_Boss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
		MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
		NameBoss = "Awakened Ice Admiral"
		NameQuestBoss = "FrostQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
		CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
	elseif _G.Select_Boss == "Tide Keeper [Lv. 1475] [Boss]" then
		MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
		NameBoss = "Tide Keeper"
		NameQuestBoss = "ForgottenQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
		CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
		-- Thire World
	elseif _G.Select_Boss == "Stone [Lv. 1550] [Boss]" then
		MsBoss = "Stone [Lv. 1550] [Boss]"
		NameBoss = "Stone"
		NameQuestBoss = "PiratePortQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-290, 44, 5577)
		CFrameBoss = CFrame.new(-1085, 40, 6779)
	elseif _G.Select_Boss == "Island Empress [Lv. 1675] [Boss]" then
		MsBoss = "Island Empress [Lv. 1675] [Boss]"
		NameBoss = "Island Empress"
		NameQuestBoss = "AmazonQuest2"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5443, 602, 752)
		CFrameBoss = CFrame.new(5659, 602, 244)
	elseif _G.Select_Boss == "Kilo Admiral [Lv. 1750] [Boss]" then
		MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
		NameBoss = "Kilo Admiral"
		NameQuestBoss = "MarineTreeIsland"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(2178, 29, -6737)
		CFrameBoss =CFrame.new(2846, 433, -7100)
	elseif _G.Select_Boss == "Captain Elephant [Lv. 1875] [Boss]" then
		MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
		NameBoss = "Captain Elephant"
		NameQuestBoss = "DeepForestIsland"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
		CFrameBoss = CFrame.new(-13221, 325, -8405)
	elseif _G.Select_Boss == "Beautiful Pirate [Lv. 1950] [Boss]" then
		MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
		NameBoss = "Beautiful Pirate"
		NameQuestBoss = "DeepForestIsland2"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
		CFrameBoss = CFrame.new(5182, 23, -20)
	elseif _G.Select_Boss == "Cake Queen [Lv. 2175] [Boss]" then
		MsBoss = "Cake Queen [Lv. 2175] [Boss]"
		NameBoss = "Cake Queen"
		NameQuestBoss = "IceCreamIslandQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-716, 382, -11010)
		CFrameBoss = CFrame.new(-821, 66, -10965)
	elseif _G.Select_Boss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
		MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
		NameBoss = "rip_indra True Form"
		CFrameBoss = CFrame.new(-5359, 424, -2735)
	elseif _G.Select_Boss == "Longma [Lv. 2000] [Boss]" then
		MsBoss = "Longma [Lv. 2000] [Boss]"
		NameBoss = "Longma"
		CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
	elseif _G.Select_Boss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
		MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
		NameBoss = "Soul Reaper"
		CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
	end
end


Number = math.random(1, 1000000)
function isnil(L_426_arg0)
	return (L_426_arg0 == nil)
end
local function L_52_func(L_427_arg0)
	return math.floor(tonumber(L_427_arg0) + 0.5)
end

spawn(function()
	while wait() do
		for L_428_forvar0, L_429_forvar1 in pairs(game:GetService'Players':GetChildren()) do
			pcall(function()
				if not isnil(L_429_forvar1.Character) then
					if _G.EspPlayer then
						if not isnil(L_429_forvar1.Character.Head) and not L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number) then
							local L_430_ = Instance.new('BillboardGui', L_429_forvar1.Character.Head)
							L_430_.Name = 'NameEsp' .. Number
							L_430_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_430_.Size = UDim2.new(1, 200, 1, 30)
							L_430_.Adornee = L_429_forvar1.Character.Head
							L_430_.AlwaysOnTop = true
							local L_431_ = Instance.new('TextLabel', L_430_)
							L_431_.Font = "GothamBold"
							L_431_.FontSize = "Size14"
							L_431_.TextWrapped = true
							L_431_.Text = (L_429_forvar1.Name .. ' : '..L_429_forvar1.Character.Humanoid.Health..' : ' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_429_forvar1.Character.Head.Position).Magnitude / 3) .. ' M')
							L_431_.Size = UDim2.new(1, 0, 1, 0)
							L_431_.TextYAlignment = 'Top'
							L_431_.BackgroundTransparency = 1
							L_431_.TextStrokeTransparency = 0.5
							if L_429_forvar1.Team == game:GetService("Teams").Pirates then
								L_431_.TextColor3 = Color3.new(255, 0, 0)
							else
								L_431_.TextColor3 = Color3.new(0, 255, 255)
							end
						else
							L_429_forvar1.Character.Head['NameEsp' .. Number].TextLabel.Text = (L_429_forvar1.Name .. ' | ' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_429_forvar1.Character.Head.Position).Magnitude / 3) .. ' M : Health : ' .. L_52_func(L_429_forvar1.Character.Humanoid.Health * 100 / L_429_forvar1.Character.Humanoid.MaxHealth) .. '%')
						end
					else
						if L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number) then
							L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_436_forvar0, L_437_forvar1 in pairs(game.Workspace:GetChildren()) do
			pcall(function()
				if L_437_forvar1.Name == "Chest1" or L_437_forvar1.Name == "Chest2" or L_437_forvar1.Name == "Chest3" then
					if _G.EspChest then
						if (L_437_forvar1.Name == "Chest1" or L_437_forvar1.Name == "Chest2" or L_437_forvar1.Name == "Chest3") and (L_437_forvar1.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 60000 then
							if not L_437_forvar1:FindFirstChild("ChestESP" .. Number) then
								local L_438_ = Instance.new("BillboardGui", L_437_forvar1)
								L_438_.Name = "ChestESP" .. Number
								L_438_.ExtentsOffset = Vector3.new(0, 1, 0)
								L_438_.Size = UDim2.new(1, 200, 1, 30)
								L_438_.Adornee = L_437_forvar1
								L_438_.AlwaysOnTop = true
								local L_439_ = Instance.new("TextLabel", L_438_)
								L_439_.Font = "GothamBold"
								L_439_.FontSize = "Size14"
								L_439_.Size = UDim2.new(1, 0, 1, 0)
								L_439_.BackgroundTransparency = 1
								L_439_.TextStrokeTransparency = 0.5
								if L_437_forvar1.Name == "Chest1" then
									L_439_.TextColor3 = Color3.fromRGB(174, 123, 47)
									L_439_.Text = "Bronze Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
								end
								if L_437_forvar1.Name == "Chest2" then
									L_439_.TextColor3 = Color3.fromRGB(255, 255, 127)
									L_439_.Text = "Gold Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
								end
								if L_437_forvar1.Name == "Chest3" then
									L_439_.Text = "Diamond Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
									L_439_.TextColor3 = Color3.fromRGB(5, 243, 255)
								end
							else
								L_437_forvar1["ChestESP" .. Number].TextLabel.Text = L_437_forvar1.Name .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
							end
						end
					else
						if L_437_forvar1:FindFirstChild("ChestESP" .. Number) then
							L_437_forvar1:FindFirstChild("ChestESP" .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_432_forvar0, L_433_forvar1 in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
			pcall(function()
				if _G.EspIsland then
					if L_433_forvar1.Name ~= "Sea" then
						if not L_433_forvar1:FindFirstChild('NameEsp') then
							local L_434_ = Instance.new('BillboardGui', L_433_forvar1)
							L_434_.Name = 'NameEsp'
							L_434_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_434_.Size = UDim2.new(1, 200, 1, 30)
							L_434_.Adornee = L_433_forvar1
							L_434_.AlwaysOnTop = true
							local L_435_ = Instance.new('TextLabel', L_434_)
							L_435_.Font = "GothamBold"
							L_435_.FontSize = "Size14"
							L_435_.TextWrapped = true
							L_435_.Size = UDim2.new(1, 0, 1, 0)
							L_435_.TextYAlignment = 'Top'
							L_435_.BackgroundTransparency = 1
							L_435_.TextStrokeTransparency = 0.5
							L_435_.TextColor3 = Color3.fromRGB(80, 245, 245)
						else
							L_433_forvar1['NameEsp'].TextLabel.Text = (L_433_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_433_forvar1.Position).Magnitude / 3) .. ' M')
						end
					end
				else
					if L_433_forvar1:FindFirstChild('NameEsp') then
						L_433_forvar1:FindFirstChild('NameEsp'):Destroy()
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_440_forvar0, L_441_forvar1 in pairs(game:GetService("Workspace"):GetChildren()) do
			pcall(function()
				if _G.EspFruit then
					if string.find(L_441_forvar1.Name, "Fruit") then
						if not L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number) then
							local L_442_ = Instance.new('BillboardGui', L_441_forvar1.Handle)
							L_442_.Name = 'NameEsp' .. Number
							L_442_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_442_.Size = UDim2.new(1, 200, 1, 30)
							L_442_.Adornee = L_441_forvar1.Handle
							L_442_.AlwaysOnTop = true
							local L_443_ = Instance.new('TextLabel', L_442_)
							L_443_.Font = "GothamBold"
							L_443_.FontSize = "Size14"
							L_443_.TextWrapped = true
							L_443_.Size = UDim2.new(1, 0, 1, 0)
							L_443_.TextYAlignment = 'Top'
							L_443_.BackgroundTransparency = 1
							L_443_.TextStrokeTransparency = 0.5
							L_443_.TextColor3 = Color3.fromRGB(255, 0, 0)
							L_443_.Text = (L_441_forvar1.Name .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_441_forvar1.Handle.Position).Magnitude / 3) .. ' M')
						else
							L_441_forvar1.Handle['NameEsp' .. Number].TextLabel.Text = (L_441_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_441_forvar1.Handle.Position).Magnitude / 3) .. ' M')
						end
					end
				else
					if L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number) then
						L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number):Destroy()
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_444_forvar0, L_445_forvar1 in pairs(game:GetService("Workspace"):GetChildren()) do
			pcall(function()
				if L_445_forvar1.Name == "Flower2" or L_445_forvar1.Name == "Flower1" then
					if _G.EspFower then
						if not L_445_forvar1:FindFirstChild('NameEsp' .. Number) then
							local L_446_ = Instance.new('BillboardGui', L_445_forvar1)
							L_446_.Name = 'NameEsp' .. Number
							L_446_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_446_.Size = UDim2.new(1, 200, 1, 30)
							L_446_.Adornee = L_445_forvar1
							L_446_.AlwaysOnTop = true
							local L_447_ = Instance.new('TextLabel', L_446_)
							L_447_.Font = "GothamBold"
							L_447_.FontSize = "Size14"
							L_447_.TextWrapped = true
							L_447_.Size = UDim2.new(1, 0, 1, 0)
							L_447_.TextYAlignment = 'Top'
							L_447_.BackgroundTransparency = 1
							L_447_.TextStrokeTransparency = 0.5
							L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							if L_445_forvar1.Name == "Flower1" then
								L_447_.Text = ("Blue Flower" .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
								L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							end
							if L_445_forvar1.Name == "Flower2" then
								L_447_.Text = ("Red Flower" .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
								L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							end
						else
							L_445_forvar1['NameEsp' .. Number].TextLabel.Text = (L_445_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
						end
					else
						if L_445_forvar1:FindFirstChild('NameEsp' .. Number) then
							L_445_forvar1:FindFirstChild('NameEsp' .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)


function AutoHaki()
	if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
	end
end

function EquipWeapon(ToolSe)
	if not _G.NotAutoEquip then
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			local Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
			wait(.1)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
		end
	end
end

local function GetIsLand(...)
	local RealtargetPos = {...}
	local targetPos = RealtargetPos[1]
	local RealTarget
	if type(targetPos) == "vector" then
		RealTarget = targetPos
	elseif type(targetPos) == "userdata" then
		RealTarget = targetPos.Position
	elseif type(targetPos) == "number" then
		RealTarget = CFrame.new(unpack(RealtargetPos))
		RealTarget = RealTarget.p
	end

	local ReturnValue
	local CheckInOut = math.huge;
	if game.Players.LocalPlayer.Team then
		for i,v in pairs(game.Workspace._WorldOrigin.PlayerSpawns:FindFirstChild(tostring(game.Players.LocalPlayer.Team)):GetChildren()) do 
			local ReMagnitude = (RealTarget - v:GetModelCFrame().p).Magnitude;
			if ReMagnitude < CheckInOut then
				CheckInOut = ReMagnitude;
				ReturnValue = v.Name
			end
		end
		if ReturnValue then
			return ReturnValue
		end 
	end
end

--BTP
function BTP(P)
	repeat wait(1)
		game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
		task.wait()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
	until (P.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1500
end

function Com(com,...)
	local Remote = game:GetService('ReplicatedStorage').Remotes:FindFirstChild("Comm"..com)
	if Remote:IsA("RemoteEvent") then
		Remote:FireServer(...)
	elseif Remote:IsA("RemoteFunction") then
		Remote:InvokeServer(...)
	end
end


getgenv().ToTarget = function(...)
	local RealtargetPos = {...}
	local targetPos = RealtargetPos[1]
	local RealTarget
	if type(targetPos) == "vector" then
		RealTarget = CFrame.new(targetPos)
	elseif type(targetPos) == "userdata" then
		RealTarget = targetPos
	elseif type(targetPos) == "number" then
		RealTarget = CFrame.new(unpack(RealtargetPos))
	end

	if game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health == 0 then if tween then tween:Cancel() end repeat wait() until game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health > 0; wait(0.2) end

	local tweenfunc = {}
	local Distance = (RealTarget.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude

	if _G.Bypass_TP then
		if Distance > 3000 and not _G.Auto_Farm_Material and not _G.Auto_God_Human and not _G.AutoSaber and not _G.Auto_Next_Island and not (game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Backpack:FindFirstChild("God's Chalice") or game.Players.LocalPlayer.Character:FindFirstChild("God's Chalice") or game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Hallow Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Sweet Chalice") or game.Players.LocalPlayer.Backpack:FindFirstChild("Sweet Chalice")) and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") then
			pcall(function()
				tween:Cancel()
				fkwarp = false

				if game:GetService("Players")["LocalPlayer"].Data:FindFirstChild("SpawnPoint").Value == tostring(GetIsLand(RealTarget)) then 
					wait(.1)
					Com("F_","TeleportToSpawn")
				elseif game:GetService("Players")["LocalPlayer"].Data:FindFirstChild("LastSpawnPoint").Value == tostring(GetIsLand(RealTarget)) then
					game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid"):ChangeState(15)
					wait(0.1)
					repeat wait() until game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0
				else
					if game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0 then
						if fkwarp == false then
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = RealTarget
						end
						fkwarp = true
					end
					wait(.08)
					game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid"):ChangeState(15)
					repeat wait() until game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0
					wait(.1)
					Com("F_","SetSpawnPoint")
				end
				wait(0.2)

				return
			end)
		end
	end

	if _G.Stoptween == true then
		tween:Cancel()
	end

	local tween_s = game:service"TweenService"
	local info = TweenInfo.new((RealTarget.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/290, Enum.EasingStyle.Linear)
	local tweenw, err = pcall(function()
		tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = RealTarget})
		tween:Play()
	end)

	function tweenfunc:Stop()
		tween:Cancel()
	end 

	function tweenfunc:Wait()
		tween.Completed:Wait()
	end 

	return tweenfunc
end

function StopTween(target)
	if not target then
		_G.StopTween = true
		wait()
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		wait()
		if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
			game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
		end
		_G.StopTween = false
		_G.Clip = false
	end
end

function Bypass(P)
	repeat wait(1)
		game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
		task.wait()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
	until (P.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3000
end

function UseCode(Text)
	game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
end

function toTarget(targetPos, targetCFrame)
	local tweenfunc = {}
	local tween_s = game:service"TweenService"
	local info = TweenInfo.new((targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/300, Enum.EasingStyle.Linear)
	local tween = tween_s:Create(game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = targetCFrame * CFrame.fromAxisAngle(Vector3.new(1,0,0), math.rad(0))})
	tween:Play()

	function tweenfunc:Stop()
		tween:Cancel()
		return tween
	end

	if not tween then return tween end
	return tweenfunc
end

function Hop()
	local PlaceID = game.PlaceId
	local AllIDs = {}
	local foundAnything = ""
	local actualHour = os.date("!*t").hour
	local Deleted = false
	function TPReturner()
		local Site;
		if foundAnything == "" then
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
		else
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
		end
		local ID = ""
		if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
			foundAnything = Site.nextPageCursor
		end
		local num = 0;
		for i,v in pairs(Site.data) do
			local Possible = true
			ID = tostring(v.id)
			if tonumber(v.maxPlayers) > tonumber(v.playing) then
				for _,Existing in pairs(AllIDs) do
					if num ~= 0 then
						if ID == tostring(Existing) then
							Possible = false
						end
					else
						if tonumber(actualHour) ~= tonumber(Existing) then
							local delFile = pcall(function()
								AllIDs = {}
								table.insert(AllIDs, actualHour)
							end)
						end
					end
					num = num + 1
				end
				if Possible == true then
					table.insert(AllIDs, ID)
					wait()
					pcall(function()
						wait()
						game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
					end)
					wait(4)
				end
			end
		end
	end
	function Teleport() 
		while wait() do
			pcall(function()
				TPReturner()
				if foundAnything ~= "" then
					TPReturner()
				end
			end)
		end
	end
	Teleport()
end

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama or _G.Auto_Kill_Law or _G.Auto_Soul_Guitar or _G.Auto_Farm_Chest_Fast then
				if not game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					local Noclip = Instance.new("BodyVelocity")
					Noclip.Name = "BodyClip"
					Noclip.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
					Noclip.MaxForce = Vector3.new(100000,100000,100000)
					Noclip.Velocity = Vector3.new(0,0,0)
				end
			else
				game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
			end
		end)
	end
end)

-----------------------------------------------------------



local Win = library:Evil("MAMA","HUB",_G.Logo )

local tab1 = Win:CraftTab('General')
local page1 = tab1:CraftPage('Main',1)
local page2 = tab1:CraftPage('Setting',2)
local tab2 = Win:CraftTab('island')
local island1 = tab2:CraftPage('island / Server',1)
local island2 = tab2:CraftPage('Dungeon / Law',2)
local tab3 = Win:CraftTab('Visuals')
local Visuals1 = tab3:CraftPage('Players / Ability',1)
local Visuals2 = tab3:CraftPage('Esp / Misc',2)
local tab4 = Win:CraftTab('Shop')
local Shop1 = tab4:CraftPage('Fruit',1)
local Shop2 = tab4:CraftPage('Shop',2)



page1:Label("Auto Farm")

page1:Toggle("Auto Farm Level",false,function(value)
	_G.Auto_Farm_Level = value
	StopTween(_G.Auto_Farm_Level)
end)

spawn(function()
	local Methodnow = 1
	while wait(1) do
		if _G.Method then
			if Methodnow == 1 then
				Methodnow = 2
				MethodFarm = CFrame.new(30, 30, 0) -- เคลื่อนที่ไปทางด้านขวา
			elseif Methodnow == 2 then
				Methodnow = 3
				MethodFarm = CFrame.new(0, 30, 30) -- เคลื่อนที่ไปทางด้านหลัง
			elseif Methodnow == 3 then 
				Methodnow = 4
				MethodFarm = CFrame.new(-30, 30, 0) -- เคลื่อนที่ไปทางด้านซ้าย
			else
				Methodnow = 1
				MethodFarm = CFrame.new(0, 30, -30) -- เคลื่อนที่ไปทางด้านหน้า
			end
		else
			MethodFarm = CFrame.new(0, 30, 0)
		end
	end
end)

spawn(function()
	while wait() do
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		pcall(function()
			if _G.Auto_Farm_Level then
				if QuestC.Visible == true then
					if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
						for _i,_v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if string.find(_v.Name,QuestCheck()[3]) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if string.find(_v.Name,QuestCheck()[3]) then
										if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
											repeat wait()
												if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,NameMon) then
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
												else
													PosMon = v.HumanoidRootPart.CFrame
													v.HumanoidRootPart.Size = Vector3.new(50,50,50)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													v.Head.CanCollide = false
													BringMobFarm = true
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													v.HumanoidRootPart.Transparency = 1
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												end
											until not _G.Auto_Farm_Level or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
										end
									end
								end
							end
						end
					else
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				else
					repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Level
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						BringMobFarm = false
						wait(0.2)
						game:GetService('ReplicatedStorage').Remotes.CommF_:InvokeServer("StartQuest", QuestCheck()[4], QuestCheck()[1]) wait(0.5)
					else
						repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Level
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				end
			end
		end)
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if _G.Brimob then
				for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Level and BringMobFarm and v.Name == QuestCheck()[3] and (v.HumanoidRootPart.Position - PosMon.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMon
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)

page1:Label("World")


page1:Toggle("Auto New World",false,function(value)
	_G.Auto_New_World = value
	StopTween(_G.Auto_New_World)
end)

spawn(function()
	while wait() do
		if _G.Auto_New_World then
			pcall(function()
				if game.Players.LocalPlayer.Data.Level.Value >= 700 and World1 then
					_G.Auto_Farm_Level = false
					if game.Workspace.Map.Ice.Door.CanCollide == true and game.Workspace.Map.Ice.Door.Transparency == 0 then
						repeat wait() getgenv().ToTarget(CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563)) until (CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
						wait(1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
						EquipWeapon("Key")
						local pos2 = CFrame.new(1347.7124, 37.3751602, -1325.6488)
						repeat wait() getgenv().ToTarget(pos2) until (pos2.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
						wait(3)
					elseif game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Ice Admiral [Lv. 700] [Boss]" and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.HumanoidRootPart.Transparency = 1
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until v.Humanoid.Health <= 0 or not v.Parent or not _G.Auto_New_World
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
								end
							end
						else
							getgenv().ToTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
						end
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
					end
				end
			end)
		end
	end
end)

page1:Toggle("Auto Third World",false,function(value)
	_G.Auto_Third_World = value
	StopTween(_G.Auto_Third_World)
end)


spawn(function()
	while wait() do
		if _G.Auto_Third_World then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 and World2 then
					_G.Auto_Farm_Level = false
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
						getgenv().ToTarget(CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016))
						if (CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
							wait(1.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
						end
						wait(1.8)
						if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "rip_indra [Lv. 1500] [Boss]" then
									OldCFrameThird = v.HumanoidRootPart.CFrame
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CFrame = OldCFrameThird
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid.WalkSpeed = 0
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
										sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
									until _G.Auto_Third_World == false or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") and (CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016))
						end
					end
				end
			end)
		end
	end
end)

page1:Label("Boss")

local BossTable = {}

for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
	if string.find(v.Name, "Boss") then
		if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
		else
			table.insert(BossTable, v.Name)
		end
	end
end

page1:Dropdown("Select Boss",BossTable,true,function(value)
	_G.Select_Boss = value
end)

page1:Button('Refresh Boss', function()
	table.clear(BossTable)
	for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
		if string.find(v.Name, "Boss") then
			if v.Name == "Ice Admiral [Lv. 700] [Boss]" then

			else
				table.insert(BossTable, v.Name)
			end
		end
	end
end)

page1:Toggle("Auto Farm Boss",false,function(value)
	_G.Auto_Farm_Boss = value
	StopTween(_G.Auto_Farm_Boss)
end)

page1:Toggle("Auto Quest Boss",true,function(value)
	_G.Auto_Quest_Boss = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Farm_Boss then
			pcall(function()
				CheckBossQuest()
				if MsBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" or MsBoss == "Longma [Lv. 2000] [Boss]" or MsBoss == "Don Swan [Lv. 1000] [Boss]" or MsBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" or MsBoss == "Order [Lv. 1250] [Raid Boss]" or MsBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
					if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == MsBoss then
								repeat wait()
									EquipWeapon(_G.Select_Weapon)
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
								until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					else
						getgenv().ToTarget(CFrameBoss)
					end
				else
					if _G.Auto_Quest_Boss then
						CheckBossQuest()
						if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
						end
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							repeat wait() getgenv().ToTarget(CFrameQuestBoss) until (CFrameQuestBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Boss
							if (CFrameQuestBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuestBoss, LevelQuestBoss)
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == MsBoss then
										repeat wait()
											if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
												EquipWeapon(_G.Select_Weapon)
												AutoHaki()
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)									
											else
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
											end
										until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
									end
								end
							else
								getgenv().ToTarget(CFrameBoss)
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == MsBoss then
									repeat wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)									
									until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						else
							getgenv().ToTarget(CFrameBoss)
						end
					end
				end
			end)
		end
	end
end)


page1:Toggle("Auto Farm Boss All",false,function(value)
	_G.Auto_Farm_All_Boss = value
	StopTween(_G.Auto_Farm_All_Boss)
end)


spawn(function()
	while wait() do
		if _G.Auto_Farm_All_Boss then
			pcall(function()
				for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
					if string.find(v.Name,"Boss") then
						repeat task.wait()
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame)
							elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(80,80,80)
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
							end
						until v.Humanoid.Health <= 0 or _G.Auto_Farm_All_Boss == false or not v.Parent
					end
				end
			end)
		end
	end
end)

page1:Label("Mastery")

page1:Toggle("Auto Farm BF Mastery",false,function(value)
	_G.Auto_Farm_BF_Mastery = value
	StopTween(_G.Auto_Farm_BF_Mastery)
end)


if _G.Auto_Farm_BF_Mastery == false then
	UseSkill = false 
end

spawn(function()
	while wait() do
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		pcall(function()
			if _G.Auto_Farm_BF_Mastery then
				if QuestC.Visible == true then
					if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == QuestCheck()[3] then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									HealthMs = v.Humanoid.MaxHealth * _G.Kill_At/100
									repeat task.wait()
										if v.Humanoid.Health <= HealthMs then
											AutoHaki()
											EquipWeapon(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											PosMonMasteryFruit = v.HumanoidRootPart.CFrame
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
											UseSkill = true
										else           
											UseSkill = false 
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											PosMonMasteryFruit = v.HumanoidRootPart.CFrame
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
										end
										StartMasteryFruitMagnet = true
									until not _G.Auto_Farm_BF_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
								end
							end
						end
					else
						StartMasteryFruitMagnet = false   
						UseSkill = false 
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				else
					repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_BF_Mastery
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						BringMobFarm = false
						wait(0.2)
						game:GetService('ReplicatedStorage').Remotes.CommF_:InvokeServer("StartQuest", QuestCheck()[4], QuestCheck()[1]) wait(0.5)
					else
						repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_BF_Mastery
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				end
			end
		end)
	end
end)

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.Brimob then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_BF_Mastery and StartMasteryFruitMagnet then
						if v.Name == "Monkey [Lv. 14]" then
							if (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryFruit
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						elseif v.Name == "Factory Staff [Lv. 800]" then
							if (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryFruit
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						elseif v.Name == QuestCheck()[3] then
							if (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryFruit
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						end
					end
				end
			end
		end)
	end
end)


spawn(function()
	while wait() do
		if UseSkill then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Backpack[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					end
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then                      
						if _G.Skill_Z then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                        
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then          
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))               
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                          
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom-Venom") then   
						if _G.Skill_Z then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                        
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then        
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))               
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then 
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                          
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
						if _G.Skill_Z and game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(2, 2.0199999809265, 1) then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                         
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.Skill_V then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						if _G.Skill_Z then 
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                         
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.Skill_V then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		pcall(function()
			if UseSkill then
				for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Notifications:GetChildren()) do
					if v.Name == "NotificationTemplate" then
						if string.find(v.Text,"Skill locked!") then
							v:Destroy()
						end
					end
				end
			end
		end)
	end)
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").RenderStepped:Connect(function()
			if UseSkill then
				local args = {
					[1] = PosMonMasteryFruit.Position
				}
				game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
			end
		end)
	end)
end)


page1:Toggle("Auto Farm Gun Mastery",false,function(value)
	_G.Auto_Farm_Gun_Mastery = value
	StopTween(_G.Auto_Farm_Gun_Mastery)
end)


spawn(function()
	pcall(function()
		while wait() do
			for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectWeaponGun = v.Name
					end
				end
			end
		end
	end)
end)

spawn(function()
	while wait() do
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		pcall(function()
			if _G.Auto_Farm_Gun_Mastery then
				if QuestC.Visible == true then
					if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == QuestCheck()[3] then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat task.wait()
										if string.find(QuestC.Container.QuestTitle.Title.Text, QuestCheck()[6]) then
											HealthMin = v.Humanoid.MaxHealth * _G.Kill_At/100
											if v.Humanoid.Health <= HealthMin then                                                
												EquipWeapon(SelectWeaponGun)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(2,2,1)
												v.Head.CanCollide = false                                                
												local args = {
													[1] = v.HumanoidRootPart.Position,
													[2] = v.HumanoidRootPart
												}
												game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
											else
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.Head.CanCollide = false               
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											end
											StartMasteryGunMagnet = true 
											PosMonMasteryGun = v.HumanoidRootPart.CFrame
										else
											StartMasteryGunMagnet = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									until not _G.Auto_Farm_Gun_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
								end
							end
						end
					else
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				else
					repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Gun_Mastery
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						BringMobFarm = false
						wait(0.2)
						game:GetService('ReplicatedStorage').Remotes.CommF_:InvokeServer("StartQuest", QuestCheck()[4], QuestCheck()[1]) wait(0.5)
					else
						repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Gun_Mastery
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				end
			end
		end)
	end
end)

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.Brimob then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Gun_Mastery and StartMasteryGunMagnet then
						if v.Name == "Monkey [Lv. 14]" then
							if (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryGun
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						elseif v.Name == "Factory Staff [Lv. 800]" then
							if (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryGun
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						elseif v.Name == QuestCheck()[3] then
							if (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.Humanoid:ChangeState(14)
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.CFrame = PosMonMasteryGun
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
							end
						end
					end
				end
			end
		end)
	end
end)

page1:Slider("Kill AT",true,1,100,25,function(value)
	_G.Kill_At = value
end)

page1:Label("Material")


function MaterialMon()
	if _G.SelectMaterial == "Radioactive Material" then
		MMon = "Factory Staff [Lv. 800]"
		MPos = CFrame.new(-507.7895202636719, 72.99479675292969, -126.45632934570312)
		SP = "Bar"
	elseif _G.SelectMaterial == "Mystic Droplet" then
		MMon = "Water Fighter [Lv. 1450]"
		MPos = CFrame.new(-3214.218017578125, 298.69952392578125, -10543.685546875)
		SP = "ForgottenIsland"
	elseif _G.SelectMaterial == "Magma Ore" then
		if game.PlaceId == 2753915549 then
			MMon = "Military Spy [Lv. 325]"
			MPos = CFrame.new(-5850.2802734375, 77.28675079345703, 8848.6748046875)
			SP = "Magma"
		elseif game.PlaceId == 4442272183 then
			MMon = "Lava Pirate [Lv. 1200]"
			MPos = CFrame.new(-5234.60595703125, 51.953372955322266, -4732.27880859375)
			SP = "CircleIslandFire"
		end
	elseif _G.SelectMaterial == "Angel Wings" then
		MMon = "Royal Soldier [Lv. 550]"
		MPos = CFrame.new(-7827.15625, 5606.912109375, -1705.5833740234375)
		SP = "Sky2"
	elseif _G.SelectMaterial == "Leather" then
		if game.PlaceId == 2753915549 then
			MMon = "Pirate [Lv. 36]"
			MPos = CFrame.new(-1211.8792724609375, 4.787090301513672, 3916.83056640625)
			SP = "Pirate"
		elseif game.PlaceId == 4442272183 then
			MMon = "Marine Captain [Lv. 900]"
			MPos = CFrame.new(-2010.5059814453125, 73.00115966796875, -3326.620849609375)
			SP = "Greenb"
		elseif game.PlaceId == 7449423635 then
			MMon = "Jungle Pirate [Lv. 1900]"
			MPos = CFrame.new(-11975.78515625, 331.7734069824219, -10620.0302734375)
			SP = "PineappleTown"
		end
	elseif _G.SelectMaterial == "Scrap Metal" then
		if game.PlaceId == 2753915549 then
			MMon = "Brute [Lv. 45]"
			MPos = CFrame.new(-1132.4202880859375, 14.844913482666016, 4293.30517578125)
			SP = "Pirate"
		elseif game.PlaceId == 4442272183 then
			MMon = "Mercenary [Lv. 725]"
			MPos = CFrame.new(-972.307373046875, 73.04473876953125, 1419.2901611328125)
			SP = "DressTown"
		elseif game.PlaceId == 7449423635 then
			MMon = "Pirate Millionaire [Lv. 1500]"
			MPos = CFrame.new(-289.6311950683594, 43.8282470703125, 5583.66357421875)
			SP = "Default"
		end
	elseif _G.SelectMaterial == "Demonic Wisp" then
		MMon = "Demonic Soul [Lv. 2025]"
		MPos = CFrame.new(-9503.388671875, 172.139892578125, 6143.0634765625)
		SP = "HauntedCastle"
	elseif _G.SelectMaterial == "Vampire Fang" then
		MMon = "Vampire [Lv. 975]"
		MPos = CFrame.new(-5999.20458984375, 6.437741279602051, -1290.059326171875)
		SP = "Graveyard"
	elseif _G.SelectMaterial == "Conjured Cocoa" then
		MMon = "Chocolate Bar Battler [Lv. 2325]"
		MPos = CFrame.new(744.7930908203125, 24.76934242248535, -12637.7255859375)
		SP = "Chocolate"
	elseif _G.SelectMaterial == "Dragon Scale" then
		MMon = "Dragon Crew Warrior [Lv. 1575]"
		MPos = CFrame.new(5824.06982421875, 51.38640213012695, -1106.694580078125)
		SP = "Hydra1"
	elseif _G.SelectMaterial == "Gunpowder" then
		MMon = "Pistol Billionaire [Lv. 1525]"
		MPos = CFrame.new(-379.6134338378906, 73.84449768066406, 5928.5263671875)
		SP = "Default"
	elseif _G.SelectMaterial == "Fish Tail" then
		MMon = "Fishman Captain [Lv. 1800]"
		MPos = CFrame.new(-10961.0126953125, 331.7977600097656, -8914.29296875)
		SP = "PineappleTown"
	elseif _G.SelectMaterial == "Mini Tusk" then
		MMon = "Mythological Pirate [Lv. 1850]"
		MPos = CFrame.new(-13516.0458984375, 469.8182373046875, -6899.16064453125)
		SP = "BigMansion"
	end
end

local MaterialMethod
if World1 then
	MaterialMethod = {
		"Magma Ore",
		"Angel Wings",
		"Leather",
		"Scrap Metal",
		"Radioactive Material",
	}
elseif World2 then
	MaterialMethod = {
		"Mystic Droplet",
		"Magma Ore",
		"Leather",
		"Scrap Metal",
		"Demonic Wisp",
		"Vampire Fang",
		"Radioactive Material",
	}
elseif World3 then
	MaterialMethod = {
		"Leather",
		"Scrap Metal",
		"Vampire Fang",
		"Conjured Cocoa",
		"Dragon Scale",
		"Gunpowder",
		"Fish Tail",
		"Mini Tusk",
		"Radioactive Material",
	}
end

page1:Dropdown("Select Material",MaterialMethod,true,function(value)
	_G.SelectMaterial = value
end)

page1:Toggle("Auto Material",false,function(value)
	_G.AutoFarmMaterial = value
	StopTween(_G.AutoFarmMaterial)
end)

local function CustomFindFirstChild(tablename)
	for i,v in pairs(tablename) do
		if game:GetService("Workspace").Enemies:FindFirstChild(v) then
			return true
		end
	end
	return false
end


spawn(function()
	while task.wait() do
		pcall(function()
			if _G.AutoFarmMaterial and _G.SelectMaterial then
				MaterialMon()
				if game.Workspace.Enemies:FindFirstChild(MMon) then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if v.Name == MMon then
							if v:FindFirstChild("HumanoidRootPart") then
								repeat task.wait()
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid.WalkSpeed = 0
									v.Head.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(50,50,50)
									StartMagnet = true
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									MatMon = v.Name
									MatPos = v.HumanoidRootPart.CFrame
								until not _G.AutoFarmMaterial or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					end
				else
					getgenv().ToTarget(MPos)
				end
			end
		end)
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if _G.Brimob then
				for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if v.Name == MatMon and StartMagnet and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMon
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)


page1:Seperator("Observation")

local ObservationLevel = page1:Label("...")

spawn(function()
	while game:GetService("RunService").Heartbeat:wait() do
		if game.Players.LocalPlayer.VisionRadius.Value == 3000 then
			value = "Max"
		else
			value = math.round(game.Players.LocalPlayer.VisionRadius.value)
		end
		ObservationLevel:Set("Observation Haki Level : "..tostring(value))
	end
end)

page1:Toggle("Auto Farm Observation",_G.AutoObservation,function(value)
	_G.AutoObservation = value
	StopTween(_G.AutoObservation)
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoObservation then
				repeat task.wait()
					if not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
						game:GetService('VirtualUser'):CaptureController()
						game:GetService('VirtualUser'):SetKeyDown('0x65')
						wait(2)
						game:GetService('VirtualUser'):SetKeyUp('0x65')
					end
				until game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") or not _G.AutoObservation
			end
		end)
	end
end)

page1:Toggle("Auto Farm Observation Hop",_G.AutoObservation_Hop,function(value)
	_G.AutoObservation_Hop = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.AutoObservation then
				if game:GetService("Players").LocalPlayer.VisionRadius.Value >= 3000 then
					print("Observation Haki Level Max")
				else
					if World2 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Water Fighter [Lv. 1450]") then
							if game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Water Fighter [Lv. 1450]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								until _G.AutoObservation == false or not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							else
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Water Fighter [Lv. 1450]").HumanoidRootPart.CFrame * CFrame.new(0,50,0)+
										wait(1)
									if not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
										game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
									end
								until _G.AutoObservation == false or game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							end
						else
							getgenv().ToTarget(CFrame.new(-3184.662353515625, 58.35300064086914, -9662.85546875))
						end
					elseif World1 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]") then
							if game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								until _G.AutoObservation == false or not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							else
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(0,50,0)
									wait(1)
									if not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
										game:GetService("TeleportService"):Teleport(game.PlaceId,game:GetService("Players").LocalPlayer)
									end
								until _G.AutoObservation == false or game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							end
						else
							getgenv().ToTarget(CFrame.new(5533.29785, 88.1079102, 4852.3916))
						end
					elseif World3 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]") then
							if game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								until _G.AutoObservation == false or not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							else
								repeat task.wait()
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]").HumanoidRootPart.CFrame * CFrame.new(0,50,0)
									wait(1)
									if not game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
										game:GetService("TeleportService"):Teleport(game.PlaceId,game:GetService("Players").LocalPlayer)
									end
								until _G.AutoObservation == false or game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
							end
						else
							getgenv().ToTarget(CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789))
						end
					end
				end
			end
		end
	end)
end)

page1:Label("Other")

page1:Toggle("Auto Mob Aura",false,function(value)
	_G.Auto_Farm_Mob_Aura = value
	StopTween(_G.Auto_Farm_Mob_Aura)
end)


task.spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Farm_Mob_Aura then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if _G.Auto_Farm_Mob_Aura and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 1000 then
						repeat task.wait()
							EquipWeapon(_G.Select_Weapon)
							AutoHaki()
							PosMonAura = v.HumanoidRootPart.CFrame
							v.HumanoidRootPart.Size = Vector3.new(60,60,60)
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.Humanoid:ChangeState(11)
							getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
						until not _G.Auto_Farm_Mob_Aura or not v.Parent or v.Humanoid.Health <= 0
					end
				end
			end
		end)
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if _G.Brimob then
				for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Mob_Aura and (v.HumanoidRootPart.Position - PosMonAura.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMonAura
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)

page1:Toggle("Auto Farm Chest",false,function(value)
	_G.AutoFarmChest = value
	StopTween(_G.AutoFarmChest)
end)

_G.MagnitudeAdd = 0
spawn(function()
	while wait() do 
		if _G.AutoFarmChest then
			for i,v in pairs(game:GetService("Workspace"):GetChildren()) do 
				if v.Name:find("Chest") then
					if game:GetService("Workspace"):FindFirstChild(v.Name) then
						if (v.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5000+_G.MagnitudeAdd then
							repeat wait()
								if game:GetService("Workspace"):FindFirstChild(v.Name) then
									getgenv().ToTarget(v.CFrame)
								end
							until _G.AutoFarmChest == false or not v.Parent
							getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
							_G.MagnitudeAdd = _G.MagnitudeAdd+1500
							break
						end
					end
				end
			end
		end
	end
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.Brimob then
					if _G.Auto_Bartilo_Quest and AutoBartiloBring and v.Name == "Swan Pirate [Lv. 775]" and (v.HumanoidRootPart.Position - PosMonBarto.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMonBarto
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if _G.Brimob then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Rengoku and StartRengokuMagnet and (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and (v.HumanoidRootPart.Position - RengokuMon.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = RengokuMon
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)

if World2 then

	page1:Toggle("Auto Rengoku",false,function(value)
		_G.Auto_Rengoku = value
		StopTween(_G.Auto_Rengoku)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Rengoku then
				pcall(function()
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hidden Key") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hidden Key") then
						EquipWeapon("Hidden Key")
						getgenv().ToTarget(CFrame.new(6571.1201171875, 299.23028564453, -6967.841796875))
					elseif game:GetService("Workspace").Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") or game:GetService("Workspace").Enemies:FindFirstChild("Arctic Warrior [Lv. 1350]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and v.Humanoid.Health > 0 then
								repeat task.wait()
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(50,50,50)
									RengokuMon = v.HumanoidRootPart.CFrame
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									StartRengokuMagnet = true
								until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hidden Key") or _G.Auto_Rengoku == false or not v.Parent or v.Humanoid.Health <= 0
								StartRengokuMagnet = false
							end
						end
					else
						StartRengokuMagnet = false
						getgenv().ToTarget(CFrame.new(5439.716796875, 84.420944213867, -6715.1635742188))
					end
				end)
			end
		end
	end)

	page1:Toggle("Auto Bartilo Quest",false,function(value)
		_G.Auto_Bartilo_Quest = value
		StopTween(_G.Auto_Bartilo_Quest)
	end)


	spawn(function()
		pcall(function()
			while wait() do
				if _G.Auto_Bartilo_Quest then
					if game:GetService("Players").LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then 
							if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Swan Pirate [Lv. 775]" then
										pcall(function()
											repeat task.wait()
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.HumanoidRootPart.Transparency = 1
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)												
												PosMonBarto =  v.HumanoidRootPart.CFrame
												AutoBartiloBring = true
											until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Bartilo_Quest == false or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
											AutoBartiloBring = false
										end)
									end
								end
							else
								repeat getgenv().ToTarget(CFrame.new(932.624451, 156.106079, 1180.27466, -0.973085582, 4.55137119e-08, -0.230443969, 2.67024713e-08, 1, 8.47491108e-08, 0.230443969, 7.63147128e-08, -0.973085582)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(932.624451, 156.106079, 1180.27466, -0.973085582, 4.55137119e-08, -0.230443969, 2.67024713e-08, 1, 8.47491108e-08, 0.230443969, 7.63147128e-08, -0.973085582)).Magnitude <= 10
							end
						else
							repeat getgenv().ToTarget(CFrame.new(-456.28952, 73.0200958, 299.895966)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-456.28952, 73.0200958, 299.895966)).Magnitude <= 10
							wait(1.1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
						end 
					elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Jeremy [Lv. 850] [Boss]" then
									OldCFrameBartlio = v.HumanoidRootPart.CFrame
									repeat wait()
										sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.Transparency = 1
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										v.HumanoidRootPart.CFrame = OldCFrameBartlio
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
									until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Bartilo_Quest == false
								end
							end
						elseif game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							repeat getgenv().ToTarget(CFrame.new(-456.28952, 73.0200958, 299.895966)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-456.28952, 73.0200958, 299.895966)).Magnitude <= 10
							wait(1.1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo")
							wait(1)
							repeat getgenv().ToTarget(CFrame.new(2099.88159, 448.931, 648.997375)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(2099.88159, 448.931, 648.997375)).Magnitude <= 10
							wait(2)
						else
							repeat getgenv().ToTarget(CFrame.new(2099.88159, 448.931, 648.997375)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(2099.88159, 448.931, 648.997375)).Magnitude <= 10
						end
					elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
						repeat getgenv().ToTarget(CFrame.new(-1850.49329, 13.1789551, 1750.89685)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1850.49329, 13.1789551, 1750.89685)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1858.87305, 19.3777466, 1712.01807)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1858.87305, 19.3777466, 1712.01807)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1803.94324, 16.5789185, 1750.89685)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1803.94324, 16.5789185, 1750.89685)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1858.55835, 16.8604317, 1724.79541)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1858.55835, 16.8604317, 1724.79541)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1869.54224, 15.987854, 1681.00659)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1869.54224, 15.987854, 1681.00659)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1800.0979, 16.4978027, 1684.52368)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1800.0979, 16.4978027, 1684.52368)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1819.26343, 14.795166, 1717.90625)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1819.26343, 14.795166, 1717.90625)).Magnitude <= 10
						wait(1)
						repeat getgenv().ToTarget(CFrame.new(-1813.51843, 14.8604736, 1724.79541)) wait() until not _G.Auto_Bartilo_Quest or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1813.51843, 14.8604736, 1724.79541)).Magnitude <= 10
					end
				end 
			end
		end)
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				if _G.Brimob then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if _G.Auto_Evo_Race_V2 and StartEvoMagnet and v.Name == "Swan Pirate [Lv. 775]" and (v.HumanoidRootPart.Position - PosMonEvo.Position).magnitude <= 225 then
							v.HumanoidRootPart.CFrame = PosMonEvo
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						end
					end
				end
			end)
		end)
	end)


	page1:Toggle("Auto Evo Race V2",false,function(value)
		_G.Auto_Evo_Race_V2 = value
		StopTween(_G.Auto_Evo_Race_V2)
	end)



	spawn(function()
		pcall(function()
			while wait() do
				if _G.Auto_Evo_Race_V2 then
					if not game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") then
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 0 then
							getgenv().ToTarget(CFrame.new(-2779.83521, 72.9661407, -3574.02002, -0.730484903, 6.39014104e-08, -0.68292886, 3.59963224e-08, 1, 5.50667032e-08, 0.68292886, 1.56424669e-08, -0.730484903))
							if (Vector3.new(-2779.83521, 72.9661407, -3574.02002) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.3)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
							end
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 1 then
							pcall(function()
								if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 1") then
									getgenv().ToTarget(game:GetService("Workspace").Flower1.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 2") then
									getgenv().ToTarget(game:GetService("Workspace").Flower2.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 3") then
									if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Swan Pirate [Lv. 775]" then
												repeat task.wait()
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													v.HumanoidRootPart.CanCollide = false
													v.HumanoidRootPart.Size = Vector3.new(50,50,50)
													PosMonEvo = v.HumanoidRootPart.CFrame
													StartEvoMagnet = true
												until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") or not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Evo_Race_V2 == false
												StartEvoMagnet = false
											end
										end
									else
										StartEvoMagnet = false
										getgenv().ToTarget(CFrame.new(980.0985107421875, 121.331298828125, 1287.2093505859375))
									end
								end
							end)
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 2 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
						end
					end
				end
			end
		end)
	end)
end
if World1 then
	page1:Toggle("Auto Saber",false,function(value)
		_G.AutoSaber = value
		StopTween(_G.AutoSaber)
	end)


	spawn(function()
		while task.wait() do
			pcall(function()
				if _G.AutoSaber then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
					if game:GetService("Workspace").Map.Jungle.Final.Part.Transparency == 0 then
						if game:GetService("Workspace").Map.Jungle.QuestPlates.Door.Transparency == 0 then
							if (CFrame.new(-1480.06018, 47.9773636, 4.53454018, -0.386713833, 1.11673025e-07, 0.922199786, 7.96717785e-08, 1, -8.76847395e-08, -0.922199786, 3.95643944e-08, -0.386713833).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
								getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
								task.wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate1.Button.CFrame
								task.wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate2.Button.CFrame
								task.wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate3.Button.CFrame
								task.wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate4.Button.CFrame
								task.wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate5.Button.CFrame
								task.wait(1) 
							end
							local CFrameSaber = CFrame.new(-1480.06018, 47.9773636, 4.53454018, -0.386713833, 1.11673025e-07, 0.922199786, 7.96717785e-08, 1, -8.76847395e-08, -0.922199786, 3.95643944e-08, -0.386713833)
							if _G.Auto_Farm_Level and _G.AutoSaber and (CFrameSaber.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
								getgenv().ToTarget(CFrameSaber)
							end
							getgenv().ToTarget(CFrameSaber)
						else
							if game:GetService("Workspace").Map.Desert.Burn.Part.Transparency == 0 then
								if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Torch") then
									EquipWeapon("Torch")
									getgenv().ToTarget(CFrame.new(1113.7229, 5.04679585, 4350.33691, -0.541527212, 5.27007726e-09, 0.840683222, 8.74004868e-08, 1, 5.00303372e-08, -0.840683222, 1.00568911e-07, -0.541527212))
									EquipWeapon("Torch")
									EquipWeapon("Torch")
									task.wait(0.5)
								else
									getgenv().ToTarget(CFrame.new(-1610.56824, 12.1773882, 162.830322, -0.907543361, -2.88120088e-08, -0.419958383, -4.66550922e-08, 1, 3.22163096e-08, 0.419958383, 4.88308949e-08, -0.907543361))                 
								end
							else
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
									task.wait(0.5)
									EquipWeapon("Cup")
									task.wait(0.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","FillCup",game:GetService("Players").LocalPlayer.Character.Cup)
									task.wait(0)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") 
								else
									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == nil then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
									elseif  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
										if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
											for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
												if v.Name == "Mob Leader [Lv. 120] [Boss]" then
													if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
														repeat task.wait()
															EquipWeapon(_G.Select_Weapon)
															v.HumanoidRootPart.CanCollide = false
															v.Humanoid.WalkSpeed = 0
															v.Head.CanCollide = false
															v.HumanoidRootPart.Size = Vector3.new(100,100,100)
															v.HumanoidRootPart.Transparency = 1
															EquipWeapon(_G.Select_Weapon)
															getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
														until v.Humanoid.Health <= 0 or _G.AutoSaber == false
													end
												end
												for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
													if v.Name == "Mob Leader [Lv. 120] [Boss]" then
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												end
											end
										end
									elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
										task.wait(0.5)
										EquipWeapon("Relic")
										task.wait(0.5)
										getgenv().ToTarget(CFrame.new(-1406.37512, 29.9773273, 4.45027685, 0.877344251, -3.82776442e-08, 0.479861468, 4.93218133e-09, 1, 7.07504668e-08, -0.479861468, -5.9705755e-08, 0.877344251))
									end
								end
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Saber Expert [Lv. 200] [Boss]" then
									repeat task.wait()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.HumanoidRootPart.Transparency = 1
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until v.Humanoid.Health <= 0 or _G.AutoSaber == false
									if v.Humanoid.Health <= 0 then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","PlaceRelic")
									end
								end
							end
						end
					end
				end
			end)
		end
	end)

	page1:Toggle("Auto Pole",false,function(value)
		_G.Auto_Pole = value
		StopTween(_G.Auto_Pole)
	end)

	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Pole and game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if _G.Auto_Pole and v.Name == "Thunder God [Lv. 575] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()  
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Pole or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					else
						getgenv().ToTarget(CFrame.new(-7900.66406, 5606.90918, -2267.46436))
					end
				else
					if _G.Auto_Pole_Hop then
						Hop()
					end
				end
			end)
		end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Brimob then
						if _G.Auto_Farm_Ectoplasm and MagnetEctoplasm and string.find(v.Name, "Ship") and (v.HumanoidRootPart.Position - PosMonEctoplasm.Position).magnitude <= 225 then
							v.HumanoidRootPart.CFrame = PosMonEctoplasm
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						end
					end
				end
			end)
		end)
	end)
end

if World2 then
	page1:Label("Ectoplasm")

	local CheckingEctoplasm = page1:Seperator("")

	spawn(function()
		pcall(function()
			while wait() do
				CheckingEctoplasm:Set("Checking Ectoplasm : "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check").." Ectoplasm")
			end
		end)
	end)

	page1:Toggle("Auto Ectoplasm", false, function(value)
		_G.Auto_Farm_Ectoplasm = value
		StopTween(_G.Auto_Farm_Ectoplasm)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Ectoplasm then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if string.find(v.Name, "Ship") then
								repeat wait()
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMonEctoplasm = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(50,50,50)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									MagnetEctoplasm = true
								until _G.Auto_Farm_Ectoplasm == false or not v.Parent or v.Humanoid.Health <= 0
								MagnetEctoplasm = false
							else
								MagnetEctoplasm = false
								getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
							end
						end
					else
						MagnetEctoplasm = false
						local Distance = (Vector3.new(904.4072265625, 181.05767822266, 33341.38671875) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
						if Distance > 20000 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
						end
						getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
					end
				end)
			end
		end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Brimob then
						if _G.Auto_Farm_Ectoplasm and MagnetEctoplasm and string.find(v.Name, "Ship") and (v.HumanoidRootPart.Position - PosMonEctoplasm.Position).magnitude <= 225 then
							v.HumanoidRootPart.CFrame = PosMonEctoplasm
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						end
					end
				end
			end)
		end)
	end)

end

if World2 then

	page1:Label("Swan Glasses")

	page1:Toggle("Auto Swan Glasses",false,function(value)
		_G.AutoFarmSwanGlasses = value
		StopTween(_G.AutoFarmSwanGlasses)
	end)

	page1:Toggle("Auto Swan Glasses Hop",false,function(value)
		_G.Auto_Swan_Glasses_Hop = value
	end)

	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Swan_Glasses and game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if _G.Auto_Swan_Glasses and v.Name == "Don Swan [Lv. 1000] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()  
									EquipWeapon(_G.Select_Weapon)
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Swan_Glasses or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					else
						getgenv().ToTarget(CFrame.new(2289.47900390625, 15.152046203613281, 739.512939453125))
					end
				else
					if _G.Auto_Swan_Glasses_Hop then
						Hop()
					end
				end
			end)
		end
	end)
end



if World3 then
	page1:Label("Rainbow Haki")

	page1:Toggle("Auto Rainbow Haki",false,function(value)
		_G.Auto_Rainbow_Haki = value
	end)

	page1:Toggle("Auto Rainbow Haki Hop",false,function(value)
		_G.Auto_Dragon_Trident_Hop = value
	end)	


	spawn(function()
		pcall(function()
			while wait() do
				if _G.Auto_Rainbow_Haki then
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
					elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Stone") then
						if _G.Auto_Rainbow_Haki and game.ReplicatedStorage:FindFirstChild("Stone [Lv. 1550] [Boss]") or game.Workspace.Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Stone [Lv. 1550] [Boss]" then
										OldCFrameRainbow = v.HumanoidRootPart.CFrame
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.CFrame = OldCFrameRainbow
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Rainbow_Haki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									end
								end
							else
								getgenv().ToTarget(CFrame.new(-1086.11621, 38.8425903, 6768.71436, 0.0231462717, -0.592676699, 0.805107772, 2.03251839e-05, 0.805323839, 0.592835128, -0.999732077, -0.0137055516, 0.0186523199))
							end
						else
							if _G.Auto_Rainbow_Haki_Hop then
								Hop()
							end
						end
					elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Island Empress") then
						if _G.Auto_Rainbow_Haki and game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]") or game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Island Empress [Lv. 1675] [Boss]" then
										OldCFrameRainbow = v.HumanoidRootPart.CFrame
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.CFrame = OldCFrameRainbow
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Rainbow_Haki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									end
								end
							else
								getgenv().ToTarget(CFrame.new(5713.98877, 601.922974, 202.751251, -0.101080291, -0, -0.994878292, -0, 1, -0, 0.994878292, 0, -0.101080291))
							end
						else
							if _G.Auto_Rainbow_Haki_Hop then
								Hop()
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Kilo Admiral") then
						if _G.Auto_Rainbow_Haki and game.ReplicatedStorage:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") or game.Workspace.Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Kilo Admiral [Lv. 1750] [Boss]" then
										OldCFrameRainbow = v.HumanoidRootPart.CFrame
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											v.HumanoidRootPart.CFrame = OldCFrameRainbow
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Rainbow_Haki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									end
								end
							else
								getgenv().ToTarget(CFrame.new(2877.61743, 423.558685, -7207.31006, -0.989591599, -0, -0.143904909, -0, 1.00000012, -0, 0.143904924, 0, -0.989591479))
							end
						else
							if _G.Auto_Rainbow_Haki_Hop then
								Hop()
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") then
						if _G.Auto_Rainbow_Haki and game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") or game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
										OldCFrameRainbow = v.HumanoidRootPart.CFrame
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											v.HumanoidRootPart.CFrame = OldCFrameRainbow
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Rainbow_Haki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									end
								end
							else
								getgenv().ToTarget(CFrame.new(-13485.0283, 331.709259, -8012.4873, 0.714521289, 7.98849911e-08, 0.69961375, -1.02065748e-07, 1, -9.94383065e-09, -0.69961375, -6.43015241e-08, 0.714521289))
							end
						else 
							if _G.Auto_Rainbow_Haki_Hop then
								Hop()
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Beautiful Pirate") then
						if _G.Auto_Rainbow_Haki and game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") or game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" then
										OldCFrameRainbow = v.HumanoidRootPart.CFrame
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											v.HumanoidRootPart.CFrame = OldCFrameRainbow
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Rainbow_Haki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									end
								end
							else
								getgenv().ToTarget(CFrame.new(5312.3598632813, 20.141201019287, -10.158538818359))
							end
						else 
							if _G.Auto_Rainbow_Haki_Hop then
								Hop()
							end
						end
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
					end
				end
			end
		end)
	end)
end

if World2 then
	page1:Label("Dragon Trident")

	page1:Toggle("Auto Dragon Trident",false,function(value)
		_G.Auto_Dragon_Trident = value
	end)

	page1:Toggle("Auto Dragon Trident Hop",false,function(value)
		_G.Auto_Dragon_Trident_Hop = value
	end)	

	spawn(function()
		while wait() do
			if _G.Auto_Dragon_Trident then
				pcall(function()
					if _G.Auto_Dragon_Trident and game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Tide Keeper [Lv. 1475] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Dragon_Trident or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							getgenv().ToTarget(CFrame.new(-3914.830322265625, 123.29389190673828, -11516.8642578125))
						end
					else
						if _G.Auto_Dragon_Trident_Hop then
							Hop()
						end
					end
				end)
			end
		end
	end)
end

if World3 then	


	page1:Label("Cake Prince")

	local MobKilled = page1:Seperator('...')

	spawn(function()
		while wait() do
			pcall(function()
				if string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 88 then
					MobKilled:Set(" 🎂 Need Kill Mods : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,41))
				elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 87 then
					MobKilled:Set(" 🎂 Need Kill Mods : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,40))
				elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 86 then
					MobKilled:Set(" 🎂 Need Kill Mods : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,39))
				else
					MobKilled:Set(" 🎂 Katakuri Is Spawning")
				end
			end)
		end
	end)

	page1:Toggle("Auto Cake Prince",false,function(value)
		_G.Auto_Cake_Prince = value
		StopTween(_G.Auto_Cake_Prince)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Cake_Prince then
				pcall(function()
					if game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then   
						if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do 
								if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										v.HumanoidRootPart.CanCollide = false
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Cake_Prince == false or not v.Parent or v.Humanoid.Health <= 0
								end    
							end    
						else
							getgenv().ToTarget(CFrame.new(-2009.2802734375, 4532.97216796875, -14937.3076171875)) 
						end
					else
						if game.Workspace.Enemies:FindFirstChild("Baking Staff [Lv. 2250]") or game.Workspace.Enemies:FindFirstChild("Head Baker [Lv. 2275]") or game.Workspace.Enemies:FindFirstChild("Cake Guard [Lv. 2225]") or game.Workspace.Enemies:FindFirstChild("Cookie Crafter [Lv. 2200]")  then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do  
								if (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										StartCakeMagnet = true
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
										POSCAKE = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Cake_Prince == false or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						else
							StartCakeMagnet = false
							getgenv().ToTarget(CFrame.new(-1820.0634765625, 210.74781799316406, -12297.49609375))
						end
					end
				end)
			end
		end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				if _G.Brimob then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if _G.Auto_Cake_Prince and StartCakeMagnet and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and (v.HumanoidRootPart.Position - POSCAKE.Position).magnitude <= 225 then
							v.HumanoidRootPart.CFrame = POSCAKE
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						end
					end
				end
			end)
		end)
	end)


	page1:Toggle("Auto Spawn Cake Prince",true,function(value)
		_G.Auto_Spawn_Cake_Prince = value
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Spawn_Cake_Prince then
				local args = {
					[1] = "CakePrinceSpawner",
					[2] = true
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))                    
				local args = {
					[1] = "CakePrinceSpawner"
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)

	page1:Label("Elite Hunter")

	local Elite_Hunter_Status = page1:Seperator('...')
	spawn(function()
		while wait() do
			pcall(function()
				if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
					Elite_Hunter_Status:Set("EliteHunter : Is Spawn")	
				else
					Elite_Hunter_Status:Set("EliteHunter : Not Spawned")	
				end
			end)
		end
	end)


	page1:Toggle("Auto Elite Hunter",false,function(value)
		_G.Auto_Elite_Hunter = value
		StopTween(_G.Auto_Elite_Hunter)
	end)

	page1:Toggle("Auto Elite Hunter Hop",false,function(value)
		_G.Auto_Elite_Hunter_Hop = value
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Elite_Hunter and World3 then
				pcall(function()
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Diablo") or string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Deandre") or string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Urban") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Diablo [Lv. 1750]" or v.Name == "Deandre [Lv. 1750]" or v.Name == "Urban [Lv. 1750]" then
										if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
											repeat wait()
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.HumanoidRootPart.CanCollide = false
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
											until _G.Auto_Elite_Hunter == false or v.Humanoid.Health <= 0 or not v.Parent
										end
									end
								end
							else
								if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								end
							end                    
						end
					else
						if _G.Auto_Elite_Hunter_Hop and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
							Hop()
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
						end
					end
				end)
			end
		end
	end)

	page1:Label("Bone")

	local CheckingBone = page1:Seperator('...')

	spawn(function()
		pcall(function()
			while wait() do
				CheckingBone:Set(" 🦴 Bone : "..(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")))
			end
		end)
	end)

	page1:Toggle("Auto Farm Bone",false,function(value)
		_G.Auto_Farm_Bone = value
		StopTween(_G.Auto_Farm_Bone)
	end)

	page1:Toggle("Auto Trade Bone",false,function(value)
		_G.Auto_Trade_Bone = value
	end)

	spawn(function()
		while wait(.1) do
			if _G.Auto_Trade_Bone then
				local args = {
					[1] = "Bones",
					[2] = "Buy",
					[3] = 1,
					[4] = 1
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				if _G.Brimob then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if _G.Auto_Farm_Bone and StartMagnetBoneMon and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and (v.HumanoidRootPart.Position - PosMonBone.Position).magnitude <= 225 then
							v.HumanoidRootPart.CFrame = PosMonBone
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						end
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Bone and World3 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Domenic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										StartMagnetBoneMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonBone = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Farm_Bone == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetBoneMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Reborn Skeleton [Lv. 1975]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Living Zombie [Lv. 2000]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Demonic Soul [Lv. 2025]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Posessed Mummy [Lv. 2050]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							end
						end
						getgenv().ToTarget(CFrame.new(-9466.72949, 171.162918, 6132.01514))
					end
				end)
			end
		end
	end)

	page1:Label("Canvander")

	page1:Toggle("Auto Canvander",false,function(value)
		_G.Auto_Canvander = value
		StopTween(_G.Auto_Canvander)
	end)

	page1:Toggle("Auto Canvander Hop",false,function(value)
		_G.Auto_Canvander_Hop = value
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Canvander then
				pcall(function()
					if _G.Auto_Canvander and game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") or game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Canvander or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							getgenv().ToTarget(CFrame.new(5240.40869140625, 22.536449432373047, 17.463970184326172))
						end
					else
						if _G.Auto_Canvander_Hop then
							Hop()
						end
					end
				end)
			end
		end
	end)

	page1:Label("Twin Hook")

	page1:Toggle("Auto Twin Hook",false,function(value)
		_G.Auto_Twin_Hook = value
		StopTween(_G.Auto_Twin_Hook)
	end)

	page1:Toggle("Auto Twin Hook Hop",false,function(value)
		_G.Auto_Twin_Hook_Hop = value
	end)


	spawn(function()
		while wait() do
			if _G.Auto_Twin_Hook then
				pcall(function()
					if _G.Auto_Twin_Hook and game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") or game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Twin_Hook or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							getgenv().ToTarget(CFrame.new(-13348.0654296875, 405.8904113769531, -8570.62890625))
						end
					else
						if _G.Auto_Twin_Hook_Hop then
							Hop()
						end
					end
				end)
			end
		end
	end)

	page1:Label("Serpent Bow")

	page1:Toggle("Auto Serpent Bow",false,function(value)
		_G.Auto_Serpent_Bow = value
		StopTween(_G.Auto_Serpent_Bow)
	end)

	page1:Toggle("Auto Serpent Bow Hop",false,function(value)
		_G.Auto_Serpent_Bow_Hop = value
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Serpent_Bow then
				pcall(function()
					if _G.Auto_Serpent_Bow and game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]") or game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Island Empress [Lv. 1675] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Serpent_Bow or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							getgenv().ToTarget(CFrame.new(5764.1826171875, 700.425537109375, 141.11996459960938))
						end
					else
						if _G.Auto_Serpent_Bow_Hop then
							Hop()
						end
					end
				end)
			end
		end
	end)

	page1:Label("Tushita")

	page1:Toggle("Auto Tushita",false,function(value)
		_G.Auto_Tushita = value
		StopTween(_G.Auto_Tushita)
	end)

	page1:Toggle("Auto Tushita Hop",false,function(value)
		_G.Auto_Tushita_Hop = value
	end)

	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Tushita then
					if game:GetService("Workspace").Map.Turtle.TushitaGate:GetChildren()[2].Transparency == 1 or game:GetService("Workspace").Map.Turtle.TushitaGate:GetChildren()[1].Transparency == 1 then
						if #game:GetService("Workspace").Enemies:GetChildren() > 0 then
							if game:GetService("Workspace").Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]") then
								for _,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Longma [Lv. 2000] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat wait()
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.HumanoidRootPart.CanCollide = false
											v.Head.CanCollide = false
											BringMobFarm = true
											EquipWeapon(_G.Select_Weapon)
											v.HumanoidRootPart.Transparency = 1
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not _G.Auto_Tushita or not v.Humanoid.Health <= 0 or not v.Parent
									else
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]").HumanoidRootPart.CFrame * MethodFarm)
									end
								end
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							if game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == tostring(GetIsLand(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))) then
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-10752, 417, -9366)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-10752, 417, -9366)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-11672, 334, -9474)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-11672, 334, -9474)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-12132, 521, -10655)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-12132, 521, -10655)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-13336, 486, -6985)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13336, 486, -6985)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-13489, 332, -7925)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13489, 332, -7925)).Magnitude <= 1
							else
								getgenv().ToTarget(CFrame.new(5148.03613, 162.352493, 910.548218, 0, 0, -1, 0, 1, 0, 1, 0, 0))
								wait(2.5)
								return
							end
						end
					end
				else
					if _G.Auto_Tushita_Hop then
						Hop()
					end
				end
			end)
		end
	end)


	page1:Label("Yama")

	page1:Toggle("Auto Yama",false,function(value)
		_G.Auto_Yama = value
		StopTween(_G.Auto_Yama)
	end)

	page1:Toggle("Auto Yama Hop",false,function(value)
		_G.Auto_Yama_Hop = value
	end)



	if _G.Auto_Yama_Hop then
		Hop()
	end

	local Yama_All_Mon = {
		["Mon Quest"] = {"Diablo [Lv. 1750]","Deandre [Lv. 1750]","Urban [Lv. 1750]"},
		["Mon"] = {"Diablo","Deandre","Urban"},
		["Item"] = "God's Chalice",
	}

	spawn(function()
		while wait() do
			if _G.Auto_Yama then
				pcall(function()
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress") >= 30 then
						fireclickdetector(game:GetService("Workspace").Map.Waterfall.SealedKatana.Handle.ClickDetector)
					else
						local QuestUI = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
						for _,_l1 in ipairs(Yama_All_Mon["Mon Quest"]) do
							for _,l in ipairs(Yama_All_Mon["Mon"]) do
								if QuestUI.Visible == true then
									if game:GetService("Workspace").Enemies:FindFirstChild(_l1) or game:GetService("ReplicatedStorage"):FindFirstChild(_l1) then
										for _,_v1 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if _v1.Name == _l1 then
												if _v1:FindFirstChild("Humanoid") and _v1:FindFirstChild("HumanoidRootPart") and _v1.Humanoid.Health > 0 then
													repeat wait()
														_v1.HumanoidRootPart.Size = Vector3.new(60,60,60)
														_v1.HumanoidRootPart.CanCollide = false
														_v1.Head.CanCollide = false
														BringMobFarm = true
														EquipWeapon(_G.Select_Weapon)
														_v1.HumanoidRootPart.Transparency = 1
														getgenv().ToTarget(_v1.HumanoidRootPart.CFrame * MethodFarm)
														AutoHaki()
													until not _G.Auto_Yama or _v1.Humanoid.Health <= 0 or not _v1.Parent
												end
											else
												getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame * MethodFarm)
											end
										end
									end
								else
									if game.Players.LocalPlayer.Backpack:FindFirstChild(Yama_All_Mon["Item"]) or game.Players.LocalPlayer.Character:FindFirstChild(Yama_All_Mon["Item"]) then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
										_G.Auto_Yama = false
										return
									else
										if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." and not ( game:GetService("Workspace").Enemies:FindFirstChild(_l1) or game:GetService("ReplicatedStorage"):FindFirstChild(_l1) ) then
										else
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
											getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame * MethodFarm)
										end
									end
								end
							end
						end
					end
				end)
			end
		end
	end)
end


page1:Label("Legendary Sword")

page1:Toggle("Auto Buy Legendary Sword",_G.AutoBuyLegendarySword,function(Value)
	_G.AutoBuyLegendarySword = Value
end)

spawn(function()
	while wait() do
		if _G.AutoBuyLegendarySword then
			pcall(function()
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "1"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "3"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				if _G.AutoBuyLegendarySword_Hop and _G.AutoBuyLegendarySword and World2 then
					wait(10)
					Hop()
				end
			end)
		end 
	end
end)

page1:Toggle("Auto Buy Legendary Sword Hop",_G.AutoBuySwordHop,function(Value)
	_G.AutoBuyLegendarySword_Hop = Value
end)
spawn(function()
	while _G.AutoBuyLegendarySword_Hop do wait()
		if _G.AutoBuyLegendarySword_Hop then
			Hop()
		end 
	end
end)


page1:Label("Haki Legends")

HakiLegends = {
	"Snow White",
	"Plump Plump",
	"Absolute Zero",
	"Heat Wave",
	"Reinboe Saviour",
	"Slimy Green",
	"Green Lizard",
	"Fiery Rose",
	"Winter Sky",
	"Orange Soda",
	"Blue Jeans",
	"Yellow Sunshine",
	"Bright Yellow",
	"Pure Red"
}

page1:Dropdown("Select Haki Legends",HakiLegends,"Pure Red",function(value)
	HakiLegends = value
end)

page1:Toggle("Auto Buy Haki Legends",false,function(value)
	_G.Auto_Buy_Haki_Legends = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Enchancement then
			local args = {
				[1] = "ColorsDealer",
				[2] = HakiLegends
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end 
	end
end)



page1:Toggle("Auto Buy Haki Legends Hop",false,function(value)
	_G.Auto_Buy_Haki_Legends_Hop = value
end)



------------------------------------------------------------------------------------------------------------------------

page2:Label("Setting")


task.spawn(function()
	while wait() do
		pcall(function()
			if SelectWeapon == "Melee" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			elseif SelectWeapon == "Sword" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Sword" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			elseif SelectWeapon == "Fruit" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Blox Fruit" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			else
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			end
		end)
	end
end)

page2:Dropdown("Select Weapon",{"Melee","Sword","Fruit"},"Melee",function(value)
	SelectWeapon = value
end)

page2:Dropdown("Select Attack",{"Ultra Attack","Super Attack"},"Super Attack",function(value)
	_G.Attack = value
end)

pcall(function()
	if _G.Attack == "Ultra Attack" then
		_G.AttackNoCd = 0.0000000001
	elseif _G.Attack == "Super Attack" then
		_G.Attack = 0.8
	end
end)

page2:Toggle("Fast Attack",true,function(value)
	_G.FastAttack = value
	Fast = value
end)

getHits = function(Size)
	local Hits = {}
	if nearbymon then
		local Enemies = workspace.Enemies:GetChildren()
		local Characters = workspace.Characters:GetChildren()
		for i=1,#Enemies do local v = Enemies[i]
			local Human = v:FindFirstChildOfClass("Humanoid")
			if Human and Human.RootPart and Human.Health > 0 and dist(Human.RootPart.Position) < Size+5 then
				table.insert(Hits,Human.RootPart)
			end
		end
		for i=1,#Characters do local v = Characters[i]
			if v ~= Client.Character then
				local Human = v:FindFirstChildOfClass("Humanoid")
				if Human and Human.RootPart and Human.Health > 0 and dist(Human.RootPart.Position) < Size+5 then
					table.insert(Hits,Human.RootPart)
				end
			end
		end
	end
	return Hits
end
-- \\ 0 / 3 // --
Players = game.Players
Client = Players.LocalPlayer
Character = Client.Character:GetChildren()
Char = Client.Character
Root = Char.HumanoidRootPart
RunService = game:GetService("RunService")
vim = game:GetService('VirtualInputManager')
CollectionService = game:GetService("CollectionService")
-- \\ 1 / 3 // --
CurrentAllMob = {}
canHits = {}  
-- \\ 2 / 3 // --
require(game.ReplicatedStorage.Util.CameraShaker):Stop()
PC = require(Client.PlayerScripts.CombatFramework.Particle)
RL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
RigC = getupvalue(require(Client.PlayerScripts.CombatFramework.RigController),2)
Combat =  getupvalue(require(Client.PlayerScripts.CombatFramework),2)
-- \\ 3 / 3 // --
task.spawn(function()
	pcall(function ()
		local stacking = 0
		local printCooldown = 0
		while wait(.075) do
			nearbymon = false
			table.clear(CurrentAllMob)
			table.clear(canHits)
			local mobs = CollectionService:GetTagged("ActiveRig")
			for i=1,#mobs do local v = mobs[i]
				Human = v:FindFirstChildOfClass("Humanoid")
				if Human and Human.Health > 0 and Human.RootPart and v ~= Char then
					local IsPlayer = game.Players:GetPlayerFromCharacter(v)
					local IsAlly = IsPlayer and CollectionService:HasTag(IsPlayer,"Ally"..Client.Name)
					if not IsAlly then
						CurrentAllMob[#CurrentAllMob + 1] = v
						if not nearbymon and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
							nearbymon = true
						end
					end
				end
			end
			if nearbymon then
				local Enemies = workspace.Enemies:GetChildren()
				local Players = Players:GetPlayers()
				for i=1,#Enemies do local v = Enemies[i]
					local Human = v:FindFirstChildOfClass("Humanoid")
					if Human and Human.RootPart and Human.Health > 0 and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
						canHits[#canHits+1] = Human.RootPart
					end
				end
				for i=1,#Players do local v = Players[i].Character
					if not Players[i]:GetAttribute("PvpDisabled") and v and v ~= Client.Character then
						local Human = v:FindFirstChildOfClass("Humanoid")
						if Human and Human.RootPart and Human.Health > 0 and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
							canHits[#canHits+1] = Human.RootPart
						end
					end
				end
			end
		end
	end)
end)
local Data = Combat
local Blank = function() end
local RigEvent = game:GetService("ReplicatedStorage").RigControllerEvent
local Validator = game.ReplicatedStorage.Remotes.Validator
local Animation = Instance.new("Animation")
local RecentlyFired = 0
local AttackCD = 0
local Controller
local lastFireValid = 0
local MaxLag = 350
fucker = 0.07
TryLag = 0
local resetCD = function()
	local WeaponName = Controller.currentWeaponModel.Name
	local Cooldown = {
		combat = 0.07
	}
	AttackCD = tick() + (fucker and Cooldown[WeaponName:lower()] or fucker or 0.285) + ((TryLag/MaxLag)*0.3)
	RigEvent.FireServer(RigEvent,"weaponChange",WeaponName)
	TryLag += 0.0000000001
	task.delay((fucker or 0.285) + (TryLag+0.5/MaxLag)*0.3,function()
		TryLag -= _G.AttackNoCd
	end)
end
if not shared.orl then shared.orl = RL.wrapAttackAnimationAsync end
if not shared.cpc then shared.cpc = PC.play end
if not shared.dnew then shared.dnew = DMG.new end
if not shared.attack then shared.attack = RigC.attack end
RL.wrapAttackAnimationAsync = function(a,b,c,d,func)
	if not _G.FastAttack then
		PC.play = shared.cpc
		return shared.orl(a,b,c,65,func)
	end
	local Radius = (_G.FastAttack and _G.FastAttack) or 50
	if canHits and #canHits > 0 then
		PC.play = function() end
		a:Play(0.01,0.01,0.01)
		func(canHits)
		wait(a.length * 0.5)
		a:Stop()
	end
end
task.spawn(function()
	pcall(function ()
		local Data = Combat
		local Blank = function() end
		local RigEvent = game:GetService("ReplicatedStorage").RigControllerEvent
		local Animation = Instance.new("Animation")
		local RecentlyFired = 0
		local AttackCD = 0
		local Controller
		local lastFireValid = 0
		local MaxLag = 350
		fucker = 0.07
		TryLag = 0
		local resetCD = function()
			local WeaponName = Controller.currentWeaponModel.Name
			local Cooldown = {
				combat = 0.07
			}
			AttackCD = tick() + (fucker and Cooldown[WeaponName:lower()] or fucker or 0.285) + ((TryLag/MaxLag)*0.3)
			RigEvent.FireServer(RigEvent,"weaponChange",WeaponName)
			TryLag += 0.0000000001
			task.delay((fucker or 0.285) + (TryLag+0.5/MaxLag)*0.3,function()
				TryLag -= _G.AttackNoCd
			end)
		end
		if not shared.orl then shared.orl = RL.wrapAttackAnimationAsync end
		if not shared.cpc then shared.cpc = PC.play end
		if not shared.dnew then shared.dnew = DMG.new end
		if not shared.attack then shared.attack = RigC.attack end
		RL.wrapAttackAnimationAsync = function(a,b,c,d,func)
			if not _G.FastAttack and Fast then
				PC.play = shared.cpc
				return shared.orl(a,b,c,50,func)
			end
			local Radius = (_G.FastAttack and Fast and DamageAuraRadius) or 50
			if canHits and #canHits > 0 then
				PC.play = function() end
				a:Play(0.00075,0.01,0.01)
				func(canHits)
				wait(a.length * 0.5)
				a:Stop()
			end
		end
		while RunService.Stepped:Wait() do
			if #canHits > 0 then
				Controller = Data.activeController
				if NormalClick then
					pcall(task.spawn,Controller.attack,Controller)
					continue
				end
				if Controller and Controller.equipped and Controller.currentWeaponModel then
					if (_G.FastAttack and _G.FastAttack and Fast) then
						if _G.FastAttack and Fast and tick() > AttackCD and not DisableFastAttack then
							resetCD()
						end
						if tick() - lastFireValid > 0.5 or not _G.FastAttack and Fast then
							Controller.timeToNextAttack = 0
							Controller.hitboxMagnitude = 65
							pcall(task.spawn,Controller.attack,Controller)
							lastFireValid = tick()
							continue
						end
						local AID3 = Controller.anims.basic[3]
						local AID2 = Controller.anims.basic[2]
						local ID = AID3 or AID2
						Animation.AnimationId = ID
						local Playing = Controller.humanoid:LoadAnimation(Animation)
						Playing:Play(0.00075,0.01,0.01)
						RigEvent.FireServer(RigEvent,"hit",canHits,AID3 and 3 or 2,"")
						-- AttackSignal:Fire()
						delay(.5,function()
							Playing:Stop()
						end)
					end
				end
			end
		end
	end)
end)


local x2Code = {
	"3BVISITS",
	"UPD16",
	"FUDD10",
	"BIGNEWS",
	"THEGREATACE",
	"SUB2GAMERROBOT_EXP1",
	"StrawHatMaine",
	"Sub2OfficialNoobie",
	"SUB2NOOBMASTER123",
	"Sub2Daigrock",
	"Axiore",
	"TantaiGaming",
	"STRAWHATMAINE",
	"Enyu_is_Pro",
	"Sub2Fer999",
	"Bluxxy",
	"JCWK",
	"Magicbus",
	"Starcodeheo",
	"SUB2UNCLEKIZARU"
}

page2:Button('Redeem All Codes', function()
	for i,v in pairs(x2Code) do
		UseCode(v)
	end
end)

page2:Toggle("Notification",false,function(value)
	if value then
		game:GetService("Players")[_G.PlayerName].PlayerGui.Notifications.Enabled = false
	else
		game:GetService("Players")[_G.PlayerName].PlayerGui.Notifications.Enabled = true
	end
end)

page2:Toggle("Method Random",true,function(value)
	_G.Method = value
end)

page2:Toggle("Disnab Dame",false,function(value)
	_G.DisnableDame = value
end)



if _G.DisnableDame then
	game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = false
else
	game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = true
end


page2:Toggle("Bring mob",true,function(value)
	_G.Brimob = value
end)

page2:Toggle("Bypass Tp",false,function(value)
	_G.Bypass_TP = value
end)

page2:Toggle("Auto Rejoin",true,function(value)
	_G.AutoRejoin = value
end)

spawn(function()
	while wait() do
		if _G.AutoRejoin then
			_G.AutoRejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
				if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
					game:GetService("TeleportService"):Teleport(game.PlaceId)
				end
			end)
		end
	end
end)

page2:Label("Use Skill")

page2:Toggle("Skill Z",true,function(value)
	_G.Skill_Z = value
end)

page2:Toggle("Skill X",true,function(value)
	_G.Skill_X = value
end)

page2:Toggle("Skill C",true,function(value)
	_G.Skill_C = value
end)

page2:Toggle("Skill V",true,function(value)
	_G.Skill_V = value
end)

page2:Label("Stats")

page2:Toggle("Auto Stats Melee",false,function(value)
	_G.Auto_Stats_Melee = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Stats_Melee then
				local args = {
					[1] = "AddPoint",
					[2] = "Melee",
					[3] = _G.Point
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

			end
		end)
	end
end)


page2:Toggle("Auto Stats Defense",false,function(value)
	_G.Auto_Stats_Defense = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Stats_Defense then
			local args = {
				[1] = "AddPoint",
				[2] = "Defense",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

page2:Toggle("Auto Stats Sword",false,function(value)
	_G.Auto_Stats_Sword = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Stats_Sword then
			local args = {
				[1] = "AddPoint",
				[2] = "Sword",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

page2:Toggle("Auto Stats Gun",false,function(value)
	_G.Auto_Stats_Gun = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Stats_Gun then
			local args = {
				[1] = "AddPoint",
				[2] = "Gun",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

page2:Toggle("Auto Stats Devil Fruit",false,function(value)
	_G.Auto_Stats_Devil_Fruit = value
end)


spawn(function()
	while wait() do
		if _G.Auto_Stats_Devil_Fruit then
			local args = {
				[1] = "AddPoint",
				[2] = "Demon Fruit",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

page2:Slider("Select Point",true,1,100,25,function(value)
	_G.Point = value
end)

page2:Label("Fighting Style")

page2:Toggle("Auto Superhuman",false,function(value)
	_G.AutoSuperhuman = value
	StopTween(_G.AutoSuperhuman)
end)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoSuperhuman then
				if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
					if not game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") and not game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
								if not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") then
									if not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") then
										if not game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and not game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") then
											local args = {
												[1] = "BuyElectro"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
									end
								end
							end
						end
					end

					_G.Select_Weapon = "Melee"

					if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
						local args = {
							[1] = "BuyElectro"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 then
						local args = {
							[1] = "BuyBlackLeg"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 then
						local args = {
							[1] = "BuyBlackLeg"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 then
						local args = {
							[1] = "BuyFishmanKarate"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 then
						local args = {
							[1] = "BuyFishmanKarate"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300  then
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						HaveDragonClaw = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						if _G.AutoSuperhuman and game.Players.LocalPlayer.Data.Fragments.Value <= 1500 and HaveDragonClaw == 0 then
							if game.Players.LocalPlayer.Data.Level.Value > 1100 then
								_G.Select_Dungeon = "Flame"
								_G.Auto_Buy_Chips_Dungeon = true
								_G.Auto_Start_Dungeon = true
								_G.Auto_Next_Island = true
								if _G.Auto_Farm_Level then _G.Auto_Farm_Level = false end
							end
						else
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
							local args = {
								[1] = "BlackbeardReward",
								[2] = "DragonClaw",
								[3] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							_G.Auto_Start_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
						end
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300  then
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						HaveDragonClaw = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						if _G.AutoSuperhuman and game.Players.LocalPlayer.Data.Fragments.Value <= 1500 and HaveDragonClaw == 0 then
							if game.Players.LocalPlayer.Data.Level.Value > 1100 then
								_G.Select_Dungeon = "Flame"
								_G.Auto_Buy_Chips_Dungeon = true
								_G.Auto_Start_Dungeon = true
								_G.Auto_Next_Island = true
								if _G.Auto_Farm_Level then _G.Auto_Farm_Level = false end
							end
						else
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
							local args = {
								[1] = "BlackbeardReward",
								[2] = "DragonClaw",
								[3] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
						end
					end

					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 then
						_G.Auto_Farm_Level = _G.Auto_Farm_Level
						local args = {
							[1] = "BuySuperhuman"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 then
						_G.Auto_Farm_Level = _G.Auto_Farm_Level
						local args = {
							[1] = "BuySuperhuman"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end 
				end
			end
		end)
	end
end)
if World3 then
	page2:Toggle("Auto Electric Claw",false,function(value)
		_G.Auto_Electric_Claw = value
		StopTween(_G.Auto_Electric_Claw)
	end)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Electric_Claw then
					if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value < 400 then
							_G.Select_Weapon = "Electro"
						end  
						if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value < 400 then
							_G.Select_Weapon = "Electro"
						end  
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
							local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
							if v175 == 4 then
								local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
								if v176 == nil then
									game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
								end
							else
								local string_1 = "BuyElectricClaw";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
							local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
							if v175 == 4 then
								local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
								if v176 == nil then
									game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
								end
							else
								local string_1 = "BuyElectricClaw";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						end
					end
				end
			end)
		end
	end)
end

if World2 then
	page2:Toggle("Auto Death Step",false,function(value)
		_G.AutoDeathStep = value
		StopTween(_G.AutoDeathStep)
	end)

	page2:Toggle("Auto Fully Death Step",false,function(value)
		_G.Auto_Fully_DeathStep = value
		StopTween(_G.Auto_Fully_DeathStep)
	end)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.AutoDeathStep then
					if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
							local args = {
								[1] = "BuyDeathStep"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							_G.Select_Weapon = "Death Step"
						end  
						if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
							local args = {
								[1] = "BuyDeathStep"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

							_G.Select_Weapon = "Death Step"
						end  
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value < 400 then
							_G.Select_Weapon = "Black Leg"
						end 
					end
				elseif _G.Auto_Fully_DeathStep then
					if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
						if game:GetService("Workspace").Map.IceCastle.Hall.LibraryDoor.PhoeyuDoor.Transparency == 0 then  
							if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key") then
								EquipWeapon("Library Key")
								repeat wait() getgenv().ToTarget(CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375)) until (CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.AutoDeathStep
								if (CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
									wait(1.2)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
									wait(0.5)
								end
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450 or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450 then   
								if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
									if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then 	
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then    
												repeat wait()
													if game.Workspace.Enemies:FindFirstChild(v.Name) then
														if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 200 then
															Farmtween = getgenv().ToTarget(v.HumanoidRootPart.CFrame)
														elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 200 then
															if Farmtween then Farmtween:Stop() end
															AutoHaki()
															EquipWeapon(_G.Select_Weapon)
															v.HumanoidRootPart.Size = Vector3.new(60,60,60)
															v.Humanoid.JumpPower = 0
															v.Humanoid.WalkSpeed = 0
															v.HumanoidRootPart.CanCollide = false

															getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
														end
													end
												until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoDeathStep == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key")
											end
										end
									else
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
									end
								end
							end
						end
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
					end
				end
			end)
		end
	end)

	page2:Toggle("Auto SharkMan Karate",false,function(value)
		_G.AutoSharkManKarate = value
		StopTween(_G.AutoSharkManKarate)
	end)

	if World2 then
		page2:Toggle("Auto Fully SharkMan Karate",false,function(value)
			_G.Auto_Fully_SharkMan_Karate = value
			StopTween(_G.Auto_Fully_SharkMan_Karate)
		end)

		task.spawn(function()
			while wait() do
				pcall(function()
					if _G.AutoSharkManKarate then
						if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
							if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
								if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
									_G.Select_Weapon = "Sharkman Karate"
								end  
								if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
									_G.Select_Weapon = "Sharkman Karate"
								end  
								if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 400 then
									_G.Select_Weapon = "Fishman Karate"
								end 
							else 
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
							end
						end
					elseif _G.Auto_Fully_SharkMan_Karate then
						if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
							if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
								if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key") then
									repeat wait() getgenv().ToTarget(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365) until (CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Fully_SharkMan_Karate
									if (CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
										wait(1.2)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
										wait(0.5)
									end
								elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then   
									if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
										if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then 	
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then    
													repeat wait()
														if game.Workspace.Enemies:FindFirstChild(v.Name) then
															if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 200 then
																Farmtween = getgenv().ToTarget(v.HumanoidRootPart.CFrame)
															elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 200 then
																if Farmtween then Farmtween:Stop() end
																FastAttack = true
																AutoHaki()
																EquipWeapon(_G.Select_Weapon)
																v.HumanoidRootPart.Size = Vector3.new(60,60,60)
																v.Humanoid.JumpPower = 0
																v.Humanoid.WalkSpeed = 0
																v.HumanoidRootPart.CanCollide = false
																v.Humanoid:ChangeState(11)
																getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
															end
														end
													until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoDeathStep == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key")
												end
											end
										else
											getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
										end
									end
								end
							else 
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
							end
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
						end
					end
				end)
			end
		end)
	end
end

if World3 then
	page2:Toggle("Auto Dragon Talon",false,function(value)
		_G.Auto_Dragon_Talon = value
		StopTween(_G.Auto_Dragon_Talon)
	end)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Dragon_Talon then
					if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Select_Weapon = "Dragon Claw"
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Select_Weapon = "Dragon Claw"
						end

						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Select_Weapon = "Dragon Claw"
							if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
								local string_1 = "Bones";
								local string_2 = "Buy";
								local number_1 = 1;
								local number_2 = 1;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1, number_2);

								local string_1 = "BuyDragonTalon";
								local bool_1 = true;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, bool_1);
							elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
							else
								local string_1 = "BuyDragonTalon";
								local bool_1 = true;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, bool_1);
								local string_1 = "BuyDragonTalon";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end 
						end

						if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Select_Weapon = "Dragon Claw"
							if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
								local string_1 = "Bones";
								local string_2 = "Buy";
								local number_1 = 1;
								local number_2 = 1;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1, number_2);

								local string_1 = "BuyDragonTalon";
								local bool_1 = true;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, bool_1);
							elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
							else
								local string_1 = "BuyDragonTalon";
								local bool_1 = true;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, bool_1);
								local string_1 = "BuyDragonTalon";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end 
						end
					end
				end
			end)
		end
	end)
end

------------------------------------------------------------------------------------------------

page1:Label(" Mirage Island ")

page1:Toggle("Auto Mirage Island",false,function(value)
	if game:GetService("Workspace").Map:FindFirstChild("MysticIsland") then
		getgenv().ToTarget(game:GetService("Workspace").Map:FindFirstChild("MysticIsland").HumanoidRootPart.CFrame * CFrame.new(0,500,-100))
	else
		if _G.Mystichop then
			Hop()
		end
	end
end)

page1:Toggle("Auto Mirage Island Hop",false,function(value)
	_G.Mystichop = value
end)


------------------------------------------------------------------------------------------------

page1:Label("Full moon")

page1:Toggle("Auto Soul Guitar",false,function(value)
	_G.Auto_Soul_Guitar = value
	StopTween(_G.Auto_Soul_Guitar)
end)

page1:Toggle("Auto Soul Guitar Hop",false,function(value)
	_G.Auto_Soul_Guitar_Hop = value
end)


if _G.Auto_Soul_Guitar_Hop then
	Hop()
end



function getTrophies(Amount)
	for i,v in pairs(game:GetService("Workspace").Map["Haunted Castle"].Trophies.Quest:GetChildren()) do
		if v.Handle.Orientation then
			local NameTro = tonumber(tostring(v.Name:match("%d+")))
			if tonumber(Amount) == tonumber(NameTro) then
				if tonumber(v.Handle.Orientation.Y) == 90 or tonumber(v.Handle.Orientation.Y) == -90 then
					return {"A", 180, -180}
				elseif tonumber(v.Handle.Orientation.Y) == 0 or tonumber(v.Handle.Orientation.Y) == 180 then
					return {"B", -90, 90}
				end
			end
		end
	end
end

local function Check_Material(Material_Name)
	for i, v in pairs(game:GetService("ReplicatedStorage").Remotes['CommF_']:InvokeServer("getInventory")) do
		if v.Type == "Material" then
			if v.Name == Material_Name then
				return v.Count
			end
		end
	end
	return 0
end

local Number2 = 1
local BoneTabel = {
	["Mon"] = {"Reborn Skeleton [Lv. 1975]","Demonic Soul [Lv. 2025]","Living Zombie [Lv. 2000]","Posessed Mummy [Lv. 2050]"},
	["Boss"] = {"Soul Reaper [Lv. 2100] [Raid Boss]"},
	["Item"] = "Hallow Essence",
}

local SetCFarmeBone = 1
function GetBone_CFrame_Mon()
	local matchingCFrames = {}
	for _, Mon in ipairs(BoneTabel["Mon"]) do
		local result = Mon:gsub("Lv. ", ""):gsub("[%[%]]", ""):gsub("%d+", ""):gsub("%s+", "")
		for _, v in ipairs(game.workspace.EnemySpawns:GetChildren()) do
			if v.Name == result then
				table.insert(matchingCFrames, v.CFrame)
			end
		end
	end
	return matchingCFrames
end
_G.Poo = 1500
spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Soul_Guitar then
				local data = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress", "Check")
				if data == nil then
					if game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709149431" then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("gravestoneEvent", 2)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("gravestoneEvent", 2, true)
					elseif data == nil then
						return
					end
				end
				for i, v in pairs(data) do
					if i == "Swamp" then
						if v == false then
							if game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Living Zombie [Lv. 2000]" then
										if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
											repeat wait()
												PosMon = CFrame.new(-10164.7588, 138.652451, 5935.78418, -0.999782741, -8.01260214e-08, -0.0208426975, -7.95026338e-08, 1, -3.07377839e-08, 0.0208426975, -2.90740569e-08, -0.999782741)
												EquipWeapon(_G.Select_Weapon)
												v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
												BringMobFarmGuitar = true
												getgenv().ToTarget(CFrame.new(-10164.7588, 138.652451, 5935.78418, -0.999782741, -8.01260214e-08, -0.0208426975, -7.95026338e-08, 1, -3.07377839e-08, 0.0208426975, -2.90740569e-08, -0.999782741) * MethodFarm)
											until not _G.Auto_Soul_Guitar or v.Humanoid.Health <= 0 or not v.Parent or v.Humanoid.Health <= 0 
										end
									end
								end
							else
								getgenv().ToTarget(CFrame.new(-10164.7588, 138.652451, 5935.78418, -0.999782741, -8.01260214e-08, -0.0208426975, -7.95026338e-08, 1, -3.07377839e-08, 0.0208426975, -2.90740569e-08, -0.999782741))
							end
						else
							for _i,_v in pairs(data) do
								if _i == "Gravestones" then
									if _v == false then
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard7.Left.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard6.Left.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard5.Left.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard4.Right.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard3.Left.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard2.Right.ClickDetector)
										wait(0.2)
										fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Placard1.Right.ClickDetector)
									else
										for _i1,_v1 in pairs(data) do
											if _i1 == "Ghost" then
												if _v1 == false then
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress", "Ghost")
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress", "Ghost", true)
												else
													for _i2,_v2 in pairs(data) do
														if _i2 == "Trophies" then
															if _v2 == false then
																repeat wait()
																	fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment2:FindFirstChild("ClickDetector"))
																until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment2.Line.Position.Y == -1000 or not _G.Auto_Soul_Guitar
																repeat wait()
																	fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment5:FindFirstChild("ClickDetector"))
																until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment5.Line.Position.Y == -1000 or not _G.Auto_Soul_Guitar
																repeat wait()
																	fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment6:FindFirstChild("ClickDetector"))
																until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment6.Line.Position.Y == -1000 or not _G.Auto_Soul_Guitar
																repeat wait()
																	fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment8:FindFirstChild("ClickDetector"))
																until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment8.Line.Position.Y == -1000 or not _G.Auto_Soul_Guitar
																repeat wait()
																	fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment9:FindFirstChild("ClickDetector"))
																until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment9.Line.Position.Y == -1000 or not _G.Auto_Soul_Guitar
																if getTrophies(1)[1] then
																	repeat wait()
																		fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment1:FindFirstChild("ClickDetector"))
																	until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment1.Line.Rotation.Z == getTrophies(1)[2] or game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment1.Line.Rotation.Z == getTrophies(1)[3] or not _G.Auto_Soul_Guitar or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress","Check").Trophies == true
																end
																if getTrophies(2)[1] then
																	repeat wait()
																		fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment3:FindFirstChild("ClickDetector"))
																	until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment3.Line.Rotation.Z == getTrophies(2)[2] or game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment3.Line.Rotation.Z == getTrophies(1)[3] or not _G.Auto_Soul_Guitar or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress","Check").Trophies == true
																end
																if getTrophies(3)[1] then
																	repeat wait()
																		fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment4:FindFirstChild("ClickDetector"))
																	until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment4.Line.Rotation.Z == getTrophies(3)[2] or game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment4.Line.Rotation.Z == getTrophies(1)[3] or not _G.Auto_Soul_Guitar or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress","Check").Trophies == true
																end
																if getTrophies(4)[1] then
																	repeat wait()
																		fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment7:FindFirstChild("ClickDetector"))
																	until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment7.Line.Rotation.Z == getTrophies(4)[2] or game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment7.Line.Rotation.Z == getTrophies(1)[3] or not _G.Auto_Soul_Guitar or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress","Check").Trophies == true
																end
																if getTrophies(5)[1] then
																	repeat wait()
																		fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment10:FindFirstChild("ClickDetector"))
																	until game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment10.Line.Rotation.Z == getTrophies(5)[2] or  game:GetService("Workspace").Map["Haunted Castle"].Tablet.Segment10.Line.Rotation.Z == getTrophies(1)[3] or not _G.Auto_Soul_Guitar or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GuitarPuzzleProgress","Check").Trophies == true
																end
															else
																for _i3,_v3 in pairs(data) do
																	if _i3 == "Pipes" then
																		if _v3 == false then
																			repeat task.wait() getgenv().ToTarget(CFrame.new(-9628.02734375, 6.13064432144165, 6157.47802734375)) until not _G.Auto_Soul_Guitar or (CFrame.new(-9628.02734375, 6.13064432144165, 6157.47802734375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10               
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part10.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part10.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part10.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part8.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part6.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part6.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part4.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part4.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part4.ClickDetector)
																			wait()
																			fireclickdetector(game:GetService("Workspace").Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model.Part3.ClickDetector)
																		else
																			for _i4,_v4 in pairs(data) do
																				if _i4 == "CraftedOnce" then
																					if _v4 == false then
																						if Check_Material("Bones") < 500 and World3 then
																							for _, _Boss in ipairs(BoneTabel["Boss"]) do
																								local _Item = BoneTabel["Item"]
																								if game:GetService("Workspace").Enemies:FindFirstChild(_Boss) or game:GetService("ReplicatedStorage"):FindFirstChild(_Boss) then
																									for _, _v1 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
																										if _v1.Name == _Boss then
																											if _v1:FindFirstChild("Humanoid") and _v1:FindFirstChild("HumanoidRootPart") and _v1.Humanoid.Health > 0 then
																												repeat wait()
																													EquipWeapon(_G.Select_Weapon)
																													_v1.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
																													BringMobFarm = true
																													getgenv().ToTarget(_v1.HumanoidRootPart.CFrame * MethodFarm)
																													if (_v1.HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
																													end
																												until not _G.Auto_Soul_Guitar or v.Humanoid.Health <= 0 or not v.Parent or v.Humanoid.Health <= 0
																												BringMobFarm = false
																											end
																										end
																									end
																								else
																									if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(_Item) or game:GetService("Players").LocalPlayer.Character:FindFirstChild(_Item) then
																										EquipWeapon(_Item)
																										getgenv().ToTarget(workspace.Map["Haunted Castle"].Summoner.Detection.CFrame)
																									else
																										for _, _Mon in next, BoneTabel["Mon"] do
																											if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Demonic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
																												print(_Mon)
																												for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
																													if v.Name == _Mon then
																														if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
																															repeat wait()
																																PosMon = v.HumanoidRootPart.CFrame
																																EquipWeapon(_G.Select_Weapon)
																																v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
																																BringMobFarm = true
																																getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
																															until not _G.Auto_Soul_Guitar or v.Humanoid.Health <= 0 or not v.Parent or v.Humanoid.Health <= 0
																														else
																															getgenv().ToTarget(GetBone_CFrame_Mon()[SetCFarmeBone] * MethodFarm)
																															if (GetBone_CFrame_Mon()[SetCFarmeBone].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
																																if SetCFarmeBone == nil or SetCFarmeBone == '' then
																																	SetCFarmeBone = 1
																																elseif SetCFarmeBone >= #GetBone_CFrame_Mon() then
																																	SetCFarmeBone = 1
																																end
																																SetCFarmeBone =  SetCFarmeBone + 1

																																print(SetCFarmeBone)
																																wait(0.5)
																															end
																														end
																													end
																												end
																											else
																												getgenv().ToTarget(GetBone_CFrame_Mon()[SetCFarmeBone] * MethodFarm)
																												if (GetBone_CFrame_Mon()[SetCFarmeBone].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
																													if SetCFarmeBone == nil or SetCFarmeBone == '' then
																														SetCFarmeBone = 1
																													elseif SetCFarmeBone >= #GetBone_CFrame_Mon() then
																														SetCFarmeBone = 1
																													end
																													SetCFarmeBone =  SetCFarmeBone + 1

																													print(SetCFarmeBone)
																													wait(0.5)
																												end
																											end
																										end
																									end
																								end
																							end
																						else
																							if Check_Material("Bones") > 500 then
																								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check") < 250 then
																									if not World2 then
																										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
																									else
																										if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
																											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
																												if string.find(v.Name, "Ship") then
																													repeat wait()
																														AutoHaki()
																														EquipWeapon(_G.Select_Weapon)
																														PosMonEctoplasm = v.HumanoidRootPart.CFrame
																														v.HumanoidRootPart.CanCollide = false
																														v.HumanoidRootPart.Size = Vector3.new(50,50,50)
																														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
																														MagnetEctoplasm = true
																														game:GetService'VirtualUser':CaptureController()
																														game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
																													until _G.Auto_Soul_Guitar == false or not v.Parent or v.Humanoid.Health <= 0
																													MagnetEctoplasm = false
																												else
																													MagnetEctoplasm = false
																													getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
																												end
																											end
																										else 
																											MagnetEctoplasm = false
																											local Distance = (Vector3.new(904.4072265625, 181.05767822266, 33341.38671875) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
																											if Distance > 20000 then
																												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
																											end
																											getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
																										end
																									end
																								elseif Check_Material("Dark Fragment") < 1 then
																									if not World2 then
																										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
																									end
																									if game.ReplicatedStorage:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
																										getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
																										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
																											if v.Name == "Darkbeard [Lv. 1000] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
																												repeat wait()  
																													EquipWeapon(_G.Select_Weapon)
																													v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
																													getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
																												until not _G.Auto_Soul_Guitar or v.Humanoid.Health <= 0 or not v.Parent
																											end
																										end
																									else
																										if game.Players.LocalPlayer.Backpack:FindFirstChild("Fist of Darkness") or game.Players.LocalPlayer.Character:FindFirstChild("Fist of Darkness") then
																											EquipWeapon("Fist of Darkness")
																											getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375) * CFrame.new(0,-10,0))
																										else
																											if not World2 then
																												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
																											end
																											for i,v in pairs(game:GetService("Workspace"):GetChildren()) do 
																												if v.Name:find("Chest") then
																													if game:GetService("Workspace"):FindFirstChild(v.Name) then
																														if (v.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5000+_G.Poo then
																															repeat task.wait()
																																if game:GetService("Workspace"):FindFirstChild(v.Name) then
																																	getgenv().ToTarget(v.CFrame)
																																	if (v.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1 then
																																		EquipWeapon(_G.Select_Weapon)
																																	else
																																		EquipWeapon(_G.Select_Weapon)
																																	end
																																else
																																	_G.Poo = _G.Poo + 1000
																																end
																															until _G.Auto_Soul_Guitar  == false or not v.Parent
																															_G.Poo = _G.Poo + 1000
																															break
																														else
																															_G.Poo = _G.Poo + 1000
																														end
																													end
																												end
																											end
																										end
																									end
																								else
																									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check") > 250 then
																										if World3 then
																											print("Buy")
																											_G.Auto_Soul_Guitar = false
																										else
																											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
																										end
																									end
																								end
																							end
																						end
																					end
																				end
																			end
																		end
																	end
																end
															end
														end
													end
												end
											end
										end
									end
								end
							end
						end
					end
				end
			end 
		end)
	end
end)
spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.brimob and MagnetEctoplasm and string.find(v.Name, "Ship") and (v.HumanoidRootPart.Position - PosMonEctoplasm.Position).magnitude <= 255 then
					v.HumanoidRootPart.CFrame = PosMonEctoplasm
					v.HumanoidRootPart.CanCollide = false
					v.HumanoidRootPart.Size = Vector3.new(50,50,50)
					if v.Humanoid:FindFirstChild("Animator") then
						v.Humanoid.Animator:Destroy()
					end
					sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
				end
			end
		end)
	end)
end)

------------------------------------------------------------------------------------------------

island1:Label("Teleport World")

island1:Button('Teleport to First World', function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end)

island1:Button('Teleport to Second World', function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
end)

island1:Button('Teleport to Third World', function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end)

island1:Label("Teleport Island")

if World1 then
	Island = {
		"nil",
		"WindMill",
		"Marine",
		"Middle Town",
		"Jungle",
		"Pirate Village",
		"Desert",
		"Snow Island",
		"MarineFord",
		"Colosseum",
		"Sky Island 1",
		"Sky Island 2",
		"Sky Island 3",
		"Prison",
		"Magma Village",
		"Under Water Island",
		"Fountain City",
		"Shank Room",
		"Mob Island"
	}
elseif World2 then  
	Island = {
		"nil",
		"The Cafe",
		"Frist Spot",
		"Dark Area",
		"Flamingo Mansion",
		"Flamingo Room",
		"Green Zone",
		"Factory",
		"Colossuim",
		"Zombie Island",
		"Two Snow Mountain",
		"Punk Hazard",
		"Cursed Ship",
		"Ice Castle",
		"Forgotten Island",
		"Ussop Island",
		"Mini Sky Island"
	}
else
	Island = {
		"nil",
		"Mansion",
		"Port Town",
		"Great Tree",
		"Castle On The Sea",
		"MiniSky", 
		"Hydra Island",
		"Floating Turtle",
		"Haunted Castle",
		"Ice Cream Island",
		"Peanut Island",
		"Cake Island"
	}	
end

island1:Dropdown("Select Island",Island,true,function(value)
	_G.Select_Island = value
end)

island1:Toggle("Start Tween Island",false,function(value)
	_G.Start_Tween_Island = value
	if _G.Start_Tween_Island == true then
		repeat wait()
			if _G.Select_Island == "WindMill" then
				getgenv().ToTarget(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
			elseif _G.Select_Island == "Marine" then
				getgenv().ToTarget(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
			elseif _G.Select_Island == "Middle Town" then
				getgenv().ToTarget(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
			elseif _G.Select_Island == "Jungle" then
				getgenv().ToTarget(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
			elseif _G.Select_Island == "Pirate Village" then
				getgenv().ToTarget(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
			elseif _G.Select_Island == "Desert" then
				getgenv().ToTarget(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
			elseif _G.Select_Island == "Snow Island" then
				getgenv().ToTarget(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
			elseif _G.Select_Island == "MarineFord" then
				getgenv().ToTarget(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
			elseif _G.Select_Island == "Colosseum" then
				getgenv().ToTarget( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
			elseif _G.Select_Island == "Sky Island 1" then
				getgenv().ToTarget(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
			elseif _G.Select_Island == "Sky Island 2" then  
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			elseif _G.Select_Island == "Sky Island 3" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			elseif _G.Select_Island == "Prison" then
				getgenv().ToTarget( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
			elseif _G.Select_Island == "Magma Village" then
				getgenv().ToTarget(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
			elseif _G.Select_Island == "Under Water Island" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			elseif _G.Select_Island == "Fountain City" then
				getgenv().ToTarget(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
			elseif _G.Select_Island == "Shank Room" then
				getgenv().ToTarget(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
			elseif _G.Select_Island == "Mob Island" then
				getgenv().ToTarget(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
			elseif _G.Select_Island == "The Cafe" then
				getgenv().ToTarget(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
			elseif _G.Select_Island == "Frist Spot" then
				getgenv().ToTarget(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
			elseif _G.Select_Island == "Dark Area" then
				getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
			elseif _G.Select_Island == "Flamingo Mansion" then
				getgenv().ToTarget(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
			elseif _G.Select_Island == "Flamingo Room" then
				getgenv().ToTarget(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
			elseif _G.Select_Island == "Green Zone" then
				getgenv().ToTarget( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
			elseif _G.Select_Island == "Factory" then
				getgenv().ToTarget(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
			elseif _G.Select_Island == "Colossuim" then
				getgenv().ToTarget( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
			elseif _G.Select_Island == "Zombie Island" then
				getgenv().ToTarget(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
			elseif _G.Select_Island == "Two Snow Mountain" then
				getgenv().ToTarget(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
			elseif _G.Select_Island == "Punk Hazard" then
				getgenv().ToTarget(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
			elseif _G.Select_Island == "Cursed Ship" then
				getgenv().ToTarget(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
			elseif _G.Select_Island == "Ice Castle" then
				getgenv().ToTarget(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
			elseif _G.Select_Island == "Forgotten Island" then
				getgenv().ToTarget(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
			elseif _G.Select_Island == "Ussop Island" then
				getgenv().ToTarget(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
			elseif _G.Select_Island == "Mini Sky Island" then
				getgenv().ToTarget(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
			elseif _G.Select_Island == "Great Tree" then
				getgenv().ToTarget(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
			elseif _G.Select_Island == "Castle On The Sea" then
				getgenv().ToTarget(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
			elseif _G.Select_Island == "MiniSky" then
				getgenv().ToTarget(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
			elseif _G.Select_Island == "Port Town" then
				getgenv().ToTarget(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
			elseif _G.Select_Island == "Hydra Island" then
				getgenv().ToTarget(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
			elseif _G.Select_Island == "Floating Turtle" then
				getgenv().ToTarget(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
			elseif _G.Select_Island == "Mansion" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
			elseif _G.Select_Island == "Haunted Castle" then
				getgenv().ToTarget(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
			elseif _G.Select_Island == "Ice Cream Island" then
				getgenv().ToTarget(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
			elseif _G.Select_Island == "Peanut Island" then
				getgenv().ToTarget(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
			elseif _G.Select_Island == "Cake Island" then
				getgenv().ToTarget(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
			end
		until not _G.Start_Tween_Island
	end
	StopTween(_G.Start_Tween_Island)
end)

island1:Label("Server")

JobiJoin = ""

island1:Textbox("JOJ ID","",function(value)
	JobiJoin = value
end)

island1:Button('Join Server', function()
	game:GetService("TeleportService"):TeleportToPlaceInstance(game.placeId, JobiJoin, game.Players.LocalPlayer)
end)

island1:Button('Rejoin', function()
	local ts = game:GetService("TeleportService")
	local p = game:GetService("Players").LocalPlayer
	ts:Teleport(game.PlaceId, p)
end)

island1:Button('Server Hop', function()
	Hop()
end)

island1:Label("Joins")

island1:Button("Join Pirates Team",function()
	local args = {
		[1] = "SetTeam",
		[2] = "Pirates"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
	local args = {
		[1] = "BartiloQuestProgress"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)


island1:Button("Join Marines Team",function()
	local args = {
		[1] = "SetTeam",
		[2] = "Marines"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	local args = {
		[1] = "BartiloQuestProgress"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)


island2:Label("Main Dungeon")


Dungeon = {
	"Flame", 
	"Ice", 
	"Quake", 
	"Light",
	"Dark",
	"String",
	"Rumble",
	"Magma",
	"Human: Buddha",
	"Sand",
	"Bird: Phoenix"
}

island2:Dropdown("Select Dungeon",Dungeon,true,function(value)
	_G.Select_Dungeon = value
end)

island2:Toggle("Auto Buy Chip Dungeon",false,function(value)
	_G.Auto_Buy_Chips_Dungeon = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Chips_Dungeon then
			pcall(function()
				local args = {
					[1] = "RaidsNpc",
					[2] = "Select",
					[3] = _G.Select_Dungeon
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
	end
end)

island2:Toggle("Auto Dungeon",false,function(value)
	_G.Auto_Start_Dungeon = value
end)


spawn(function()
	while wait() do
		if _G.Auto_Start_Dungeon then
			pcall(function()
				if World2 then
					if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") then 
							fireclickdetector(game.Workspace.Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
						end
					end
				elseif World3 then
					if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") then
							fireclickdetector(game.Workspace.Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
						end
					end
				end
			end)
		end
	end
end)


island2:Toggle("Auto Next Island",false,function(value)
	_G.Auto_Next_Island = value
	StopTween(_G.Auto_Next_Island)
end)

spawn(function()
	while wait() do
		if _G.Auto_Next_Island then
			if not game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
				if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame * CFrame.new(0,70,100))
				end
			end
		end
	end
end)

island2:Toggle("Kill Aura",false,function(value)
	_G.Kill_Aura = value
end)

spawn(function()
	while wait() do
		if _G.Kill_Aura then
			for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
				if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
					pcall(function()
						repeat wait(.1)
							v.Humanoid.Health = 0
							v.HumanoidRootPart.CanCollide = false
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
						until not _G.Kill_Aura  or not v.Parent or v.Humanoid.Health <= 0
					end)
				end
			end
		end
	end
end)


island2:Toggle("Auto Awake",false,function(value)
	_G.Auto_Awake = value
end)


spawn(function()
	while wait(.1) do
		if _G.Auto_Awake then
			pcall(function()
				local args = {
					[1] = "Awakener",
					[2] = "Check"
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				local args = {
					[1] = "Awakener",
					[2] = "Awaken"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
	end
end)


island2:Label("Law Dungeon")

island2:Toggle("Auto Buy Law Chip",false,function(value)
	_G.Auto_Buy_Law_Chip = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Law_Chip then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") or game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") then

				else
					local args = {
						[1] = "BlackbeardReward",
						[2] = "Microchip",
						[3] = "2"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end)
		end
	end
end)


island2:Toggle("Auto Start Law Dungeon",false,function(value)
	_G.Auto_Start_Law_Dungeon = value
end)

spawn(function()
	while wait() do
		if _G.Auto_Start_Law_Dungeon then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") then
					fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
				end
			end)
		end
	end
end)

island2:Toggle("Auto Kill Law",false,function(value)
	_G.Auto_Kill_Law = value
	StopTween(_G.Auto_Kill_Law)
end)


spawn(function()
	while wait() do
		if _G.Auto_Kill_Law then
			pcall(function()
				if game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if _G.Auto_Kill_Law and v.Name == "Order [Lv. 1250] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat task.wait()
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							until not _G.Auto_Kill_Law or v.Humanoid.Health <= 0 or not v.Parent
						end
					end
				end 
			end)
		end
	end
end)

------------------------------------------------------------------------------------------------

Visuals1:Label("Rage Kill Player")

PlayerName = {}
for i,v in pairs(game.Players:GetChildren()) do  
	if v.Name ~= game.Players.LocalPlayer.Name then
		table.insert(PlayerName ,v.Name)
	end
end


spawn(function()
	while wait() do
		pcall(function()
			table.clear(PlayerName)
			for i,v in pairs(game.Players:GetChildren()) do  
				if v.Name ~= game.Players.LocalPlayer.Name then
					table.insert(PlayerName ,v.Name)
				end
			end
		end)
	end
end)

Visuals1:Dropdown("Select Player",PlayerName,true,function(value)
	_G.Select_Player = value
end)

Visuals1:Button("Rest Player",function(value)
	for i,v in pairs(game.Players:GetChildren()) do  
		if v.Name ~= game.Players.LocalPlayer.Name then
			table.insert(PlayerName ,v.Name)
		end
	end

end)

Visuals1:Toggle("Spectate Player",false,function(value)
	_G.Spectate_Player = value
end)

spawn(function()
	while wait() do
		if _G.Spectate_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					game.Workspace.Camera.CameraSubject = game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid
				end
			end)
		else
			game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
		end
	end
end)

Visuals1:Toggle("Teleport to Player",false,function(value)
	_G.Teleport_to_Player = value
	StopTween(_G.Teleport_to_Player)
end)

spawn(function()
	while wait() do
		if _G.Teleport_to_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					getgenv().ToTarget(game.Players[_G.Select_Player].Character.HumanoidRootPart.CFrame)
				end
			end)
		end
	end
end)

Visuals1:Toggle("Enabled PvP",false,function(value)
	_G.Enabled_PvP = value
end)


spawn(function()
	pcall(function()
		while wait() do
			if _G.Enabled_PvP then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
				end
			end
		end
	end)
end)

Visuals1:Label("Players Misc")

Visuals1:Dropdown("Select Haki State",{"State 0","State 1","State 2","State 3","State 4","State 5"},true,function(value)
	_G.SelectStateHaki = value
end)

Visuals1:Button("Change Buso Haki State",function()
	if _G.SelectStateHaki == "State 0" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",0)
	elseif _G.SelectStateHaki == "State 1" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",1)
	elseif _G.SelectStateHaki == "State 2" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",2)
	elseif _G.SelectStateHaki == "State 3" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",3)
	elseif _G.SelectStateHaki == "State 4" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",4)
	elseif _G.SelectStateHaki == "State 5" then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",5)
	end
end)


Visuals1:Toggle("No Clip",false,function(value)
	_G.No_clip = value
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.No_clip or _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			end
		end)
	end)
end)

Visuals1:Toggle("Infinit Energy",false,function(value)
	if value then
		game:GetService("Players").LocalPlayer.Character.Energy.Changed:connect(function()
			if value then
				game:GetService("Players").LocalPlayer.Character.Energy.Value = game:GetService("Players").LocalPlayer.Character.Energy.MaxValue
			end 
		end)
	end
end)
game.Players.LocalPlayer.CameraMinZoomDistance = 10
Visuals1:Toggle("Infinit CameraMaxZoom",false,function(value)
	if value then
		game.Players.LocalPlayer.CameraMaxZoomDistance = (math.huge^math.huge^math.huge)
	else
		game.Players.LocalPlayer.CameraMaxZoomDistance = 200
	end
end)


Visuals1:Toggle("Walk on Water",false,function(value)
	_G.WalkWater = value
end)

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.WalkWater then
				game:GetService("Workspace").Map["WaterBase-Plane"].Size = Vector3.new(1000,112,1000)
			else
				game:GetService("Workspace").Map["WaterBase-Plane"].Size = Vector3.new(1000,80,1000)
			end
		end)
	end
end)

Visuals1:Toggle("Dodge No CoolDown",false,function(value)
	_G.Dodge_No_CoolDown = value
end)

_G.Dodge_No_CoolDown = false
function DodgeNoCoolDown()
	if _G.Dodge_No_CoolDown then
		for i,v in next, getgc() do
			if game.Players.LocalPlayer.Character.Dodge then
				if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
					for i2,v2 in next, getupvalues(v) do
						if tostring(v2) == "0.4" then
							repeat wait(.1)
								setupvalue(v,i2,0)
							until not _G.Dodge_No_CoolDown
						end
					end
				end
			end
		end
	end
end

Visuals1:Toggle("Super Mink",false,function(value)
	local character = game:GetService("Players").LocalPlayer.Character
	if value then
		local Agility = game:GetService("ReplicatedStorage").FX['Agility']:Clone();
		game:GetService("Players")[_G.PlayerName].Data.Race.Value = "Mink"
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart;
	else
		game:GetService("Players")[_G.PlayerName].Data.Race.Value = tostring(readfile("SaveOldRace.txt"))
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Agility:Destroy()
	end
	character.Humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
		if game:GetService("Workspace").Characters[_G.PlayerName].HumanoidRootPart:FindFirstChild("Agility") then
			character.Humanoid.WalkSpeed = 250
		else
			character.Humanoid.WalkSpeed = 65
		end
	end)
end)

Visuals1:Toggle("Infinit Soru",false,function(value)
	while wait() do
		pcall(function()
			if value and game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") ~= nil  then
				for i,v in next, getgc() do
					if game:GetService("Players").LocalPlayer.Character.Soru then
						if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.Character.Soru then
							for i2,v2 in next, getupvalues(v) do
								if typeof(v2) == "table" then
									repeat wait(.1)
										v2.LastUse = 0
									until not value or game:GetService("Players").LocalPlayer.Character.Humanoid.Health <= 0
								end
							end
						end
					end
				end
			end
		end)
	end
end)

Visuals1:Toggle("Infinit Jump",false,function(value)
	_G.Infinit_SkyJump = value
end)

function SkyJumpNoCoolDown()
	if _G.Infinit_SkyJump then
		for i,v in next, getgc() do
			if game.Players.LocalPlayer.Character.Geppo then
				if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Geppo then
					for i2,v2 in next, getupvalues(v) do
						if tostring(v2) == "0" then
							repeat wait(.1)
								setupvalue(v,i2,0)
							until not _G.Infinit_SkyJump
						end
					end
				end
			end
		end
	end
end


Visuals1:Label(" Fake Race V4 ")


Visuals1:Button("Mink Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Mink V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(102, 255, 153),
		Color2 = Color3.fromRGB(102, 255, 153),
		Color3 = Color3.fromRGB(102, 255, 153),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)

end)
Visuals1:Button("Fishman Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Fishman V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(5, 115, 166),
		Color2 = Color3.fromRGB(5, 115, 166),
		Color3 = Color3.fromRGB(5, 115, 166),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)

end)
Visuals1:Button("Skypeian Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Skypeian V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(222, 222, 0),
		Color2 = Color3.fromRGB(222, 222, 0),
		Color3 = Color3.fromRGB(222, 222, 0),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)

end)
Visuals1:Button("Ghoul Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Ghoul V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(155, 155, 155),
		Color2 = Color3.fromRGB(0, 0, 0),
		Color3 = Color3.fromRGB(155, 155, 155),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)


end)
Visuals1:Button("Cyborg Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Cyborg V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(166, 0, 111),
		Color2 = Color3.fromRGB(166, 0, 111),
		Color3 = Color3.fromRGB(166, 0, 111),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)

end)
Visuals1:Button("Human Fake Transform",function()
	require(game:GetService("ReplicatedStorage").Notification).new("Human V4!"):Display();
	wait()
	setthreadcontext(5)

	local ReplicatedStorage = game:GetService("ReplicatedStorage")

	local Player = game:GetService("Players").LocalPlayer

	local ArgsTransform = {
		Character = game.Players.LocalPlayer.Character,
		CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame,
		Color1 = Color3.fromRGB(166, 0, 0),
		Color2 = Color3.fromRGB(166, 0, 0),
		Color3 = Color3.fromRGB(166, 0, 0),
	}

	Player.Character.Humanoid:LoadAnimation(ReplicatedStorage.Util.Anims.Storage["2"].RaceTransform):Play()

	delay(1, function()
		pcall(function() require(ReplicatedStorage.Effect.Container.RaceTransformation.Main)(ArgsTransform) end)
	end)

end)

Visuals2:Label("Esp")

Visuals2:Toggle("Esp Player",false,function(value)
	_G.EspPlayer = value
end)

Visuals2:Toggle("Esp Island",false,function(value)
	_G.EspIsland = value
end)

Visuals2:Toggle("Esp Fruit",false,function(value)
	_G.EspFruit = value
end)

Visuals2:Toggle("Esp Flower",false,function(value)
	_G.EspFlower = value
end)

Visuals2:Toggle("Esp Chest",false,function(value)
	_G.EspChest = value
end)

Visuals2:Label("Other")

Visuals2:Button('Click TP Tool', function()
	ClickTpTool()
end)

function ClickTpTool()
	local plr = game:GetService("Players").LocalPlayer
	local mouse = plr:GetMouse()
	local tool = Instance.new("Tool")
	tool.RequiresHandle = false
	tool.Name = "Teleport Tool"
	tool.Activated:Connect(function()
		local root = plr.Character.HumanoidRootPart
		local pos = mouse.Hit.Position+Vector3.new(0,2.5,0)
		local offset = pos-root.Position
		root.CFrame = root.CFrame+offset
	end)
	tool.Parent = plr.Backpack
end

Visuals2:Button('Boost Fps', function()
	FPSBooster()
end)

function FPSBooster()
	local decalsyeeted = true
	local g = game
	local w = g.Workspace
	local l = g.Lighting
	local t = w.Terrain
	sethiddenproperty(l,"Technology",2)
	sethiddenproperty(t,"Decoration",false)
	t.WaterWaveSize = 0
	t.WaterWaveSpeed = 0
	t.WaterReflectance = 0
	t.WaterTransparency = 0
	l.GlobalShadows = false
	l.FogEnd = 9e9
	l.Brightness = 0
	settings().Rendering.QualityLevel = "Level01"
	for i, v in pairs(g:GetDescendants()) do
		if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
		elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
			v.Transparency = 1
		elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
			v.Lifetime = NumberRange.new(0)
		elseif v:IsA("Explosion") then
			v.BlastPressure = 1
			v.BlastRadius = 1
		elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
			v.Enabled = false
		elseif v:IsA("MeshPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
			v.TextureID = 10385902758728957
		end
	end
	for i, e in pairs(l:GetChildren()) do
		if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
			e.Enabled = false
		end
	end
end

Shop1:Label("Devil Fruit Shop")

local Remote_GetFruits = game.ReplicatedStorage:FindFirstChild("Remotes").CommF_:InvokeServer("GetFruits");

Table_DevilFruitSniper = {}
ShopDevilSell = {}

for i,v in next,Remote_GetFruits do
	table.insert(Table_DevilFruitSniper,v.Name)
	if v.OnSale then 
		table.insert(ShopDevilSell,v.Name)
	end
end

Shop1:Dropdown("Select Devil Fruit",Table_DevilFruitSniper,true,function(value)
	_G.Select_Devil_Fruit = value
end)

Shop1:Toggle("Auto Buy Devil Fruit", false, function(t)
	_G.Auto_Buy_Devil_Fruit = t
end)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Devil_Fruit then
			pcall(function()
				local string_1 = "PurchaseRawFruit";
				local string_2 = _G.Select_Devil_Fruit;
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);
			end)
		end                              
	end
end)

Shop1:Toggle("Auto Random Fruit", false, function(t)
	_G.Auto_Random_Fruit = t
end)

spawn(function()
	while wait() do
		if _G.Auto_Random_Fruit then	
			local args = {
				[1] = "Cousin",
				[2] = "Buy"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

Shop1:Toggle("Auto Bring Fruit", false, function(t)
	_G.Auto_Bring_Fruit = t
end)

spawn(function()
	while wait() do
		if _G.Auto_Bring_Fruit then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
					if v:IsA("Tool") and string.find(v.Name,"Fruit") then 
						if (v.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(v.Name,"Fruit")  
						end
					end
				end
			end)
		end
	end
end)

Shop1:Toggle("Auto Store Fruit", false, function(t)
	_G.Auto_Store_Fruit = t
end)

spawn(function()
	while wait() do
		if _G.Auto_Store_Fruit then
			pcall(function()
				wait()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String",game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Leopard Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Leopard Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Leopard-Leopard",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Leopard Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Leopard Fruit"))
				end
			end)
		end
	end
end)


Shop1:Label("Open Menu")

Shop1:Button("Inventory",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")
	game.Players.localPlayer.PlayerGui.Main.Inventory.Visible = true
end)

Shop1:Button("Devil Fruit Shop",function()
	local args = {
		[1] = "GetFruits"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
end)


Shop1:Button("Title Name",function()
	local args = {
		[1] = "getTitles"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
end)


Shop1:Button("Color Haki",function()
	game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
end)

Shop2:Label("Abilities")

Shop2:Button("Buy Geppo [ $10,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
end)

Shop2:Button("Buy Buso Haki [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
end)

Shop2:Button("Buy Soru [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
end)

Shop2:Button("Buy Observation Haki [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
end)

Shop2:Toggle("Auto Buy Abilities", false, function(t)
	_G.Abilities = t
end)

spawn(function()
	while wait() do
		if _G.Abilities then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
		end
	end
end)

Shop2:Label("Boats")

BoatList = {
	"Pirate Sloop",
	"Enforcer",
	"Rocket Boost",
	"Dinghy",
	"Pirate Basic",
	"Pirate Brigade"
}

spawn(function()
	while wait() do
		pcall(function()
			if SelectBoat == "Pirate Sloop" then
				_G.SelectBoat = "PirateSloop"
			else
				if SelectBoat == "Enforcer" then
					_G.SelectBoat = "Enforcer"
				else
					if SelectBoat == "RocketBoost" then
						_G.SelectBoat = "RocketBoost"
					else
						if SelectBoat == "PirateBasic" then
							_G.SelectBoat = "PirateBasic"
						else
							if SelectBoat == "PirateBrigade" then
								_G.SelectBoat = "PirateBrigade"
							end
						end
					end
				end
			end
		end)
	end
end)

Shop2:Dropdown("Select Boats",BoatList,true,function(value)
	SelectBoat = value
end)

Shop2:Button("Buy Boat",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat",_G.SelectBoat)
end)

Shop2:Label("Fighting Style")

Shop2:Button("Buy Black Leg [ $150,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
end)

Shop2:Button("Buy Electro [ $550,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
end)

Shop2:Button("Buy Fishman Karate [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
end)

Shop2:Button("Buy Dragon Claw [ $1,500 Fragments ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
end)

Shop2:Button("Buy Superhuman [ $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
end)

Shop2:Button("Buy Death Step [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
end)

Shop2:Button("Buy Sharkman Karate [ $5,000 Fragments $2,500,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
end)

Shop2:Button("Buy Electric Claw [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
end)

Shop2:Button("Buy Dragon Talon [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
end)

Shop2:Button("Buy God Human [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
end)
-----Shop----------------

Shop2:Label("Sword")

Shop2:Button("Cutlass [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end)

Shop2:Button("Katana [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end)

Shop2:Button("Iron Mace [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end)

Shop2:Button("Dual Katana [ $12,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end)

Shop2:Button("Triple Katana [ $60,000 Beli ]", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end)

Shop2:Button("Pipe [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end)

Shop2:Button("Dual-Headed Blade [ $400,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end)

Shop2:Button("Bisento [ $1,200,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end)

Shop2:Button("Soul Cane [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end)

Shop2:Button("Pole v.2 [ 5,000 Fragments ]",function()
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ThunderGodTalk")
end)

Shop2:Toggle("Yama Sword [ Elite Hunter 30 ]",_G.AutoYama,function(value)
	_G.AutoYama = value
end)

spawn(function()
	while wait() do
		if _G.AutoYama then
			if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress") >= 30 then
				repeat wait(.1)
					fireclickdetector(game:GetService("Workspace").Map.Waterfall.SealedKatana.Handle.ClickDetector)
				until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Yama") or not _G.AutoYama
			end
		end
	end
end)

Shop2:Label("Gun")

Shop2:Button("Slingshot [ $5,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end)

Shop2:Button("Musket [ $8,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end)

Shop2:Button("Flintlock [ $10,500 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end)

Shop2:Button("Refined Slingshot [ $30,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
end)

Shop2:Button("Refined Flintlock [ $65,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Refined Flintlock"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Shop2:Button("Cannon [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
end)

Shop2:Button("Kabucha [ 1,500 Fragments]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end)

Shop2:Button("Bizarre Rifle [ 250 Ectoplasm ]", function()
	local A_1 = "Ectoplasm"
	local A_2 = "Buy"
	local A_3 = 1
	local Event = game:GetService("ReplicatedStorage").Remotes["CommF_"]
	Event:InvokeServer(A_1, A_2, A_3) 
	local A_1 = "Ectoplasm"
	local A_2 = "Buy"
	local A_3 = 1
	local Event = game:GetService("ReplicatedStorage").Remotes["CommF_"]
	Event:InvokeServer(A_1, A_2, A_3)
end)

------------Bone------------------

Shop2:Label("Bones")

Shop2:Button("Buy Surprise [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
end)

Shop2:Button("Stat Refund [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,2)
end)

Shop2:Button("Race Reroll [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,3)
end)

------------Stat------------------

Shop2:Label("Stat")

Shop2:Button("Reset Stats (Use 2.5K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end)

Shop2:Button("Random Race (Use 3K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","2")
end)
--------------Accessories-----------------
Shop2:Label("Accessories")
Shop2:Button("Black Cape [ $50,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Black Cape"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop2:Button("Swordsman Hat [ 150k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Swordsman Hat"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop2:Button("Tomoe Ring [ $500k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Tomoe Ring"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

------------------------------------------------------------------------------------------------


if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
	game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
end
if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
	game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
end


pcall(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama or _G.Auto_Kill_Law or _G.Auto_Soul_Guitar or _G.Auto_Farm_Chest_Fast then
			if not game:GetService("Workspace"):FindFirstChild("Part") then
				local Paertaiteen = Instance.new("Part")
				Paertaiteen.Name = "Part"
				Paertaiteen.Parent = game.Workspace
				Paertaiteen.Anchored = true
				Paertaiteen.Transparency = 1
				Paertaiteen.Size = Vector3.new(40, 0.5, 40)
				Paertaiteen.Material = "Neon"
			elseif game:GetService("Workspace"):FindFirstChild("Part") then
				game.Workspace["Part"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y - 3.92,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
			end
		else
			if game:GetService("Workspace"):FindFirstChild("Part") then
				game:GetService("Workspace"):FindFirstChild("Part"):Destroy()
			end
		end
	end)
end)

while wait() do
	if _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama or _G.Auto_Kill_Law or _G.Auto_Soul_Guitar or _G.Auto_Farm_Chest_Fast then
		if not game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI') then
			local Test = Instance.new('Highlight')
			Test.Name = "MAKEHI"
			Test.Enabled = true
			Test.FillColor = Color3.fromRGB(140, 255, 211)
			Test.OutlineColor = Color3.fromRGB(39, 255, 154)
			Test.FillTransparency = 0.2
			Test.OutlineTransparency = 0.1
			Test.Parent = game.Players.LocalPlayer.Character
		end
	else
		if game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI') then
			game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI'):Destroy()
		end
	end
end
