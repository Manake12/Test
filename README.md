local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton.Size = UDim2.new(0, 65, 0, 65)
ImageButton.Draggable = true
ImageButton.Image = "rbxassetid://14223355318"
ImageButton.MouseButton1Down:connect(function()
	game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
	game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)

UICorner.Parent = ImageButton

repeat wait(1) until game:IsLoaded()

do
	local ui = game.CoreGui:FindFirstChild("KumaHubGui")
	if ui then
		ui:Destroy()
	end
end



_G.ColorMethod = Color3.fromRGB(0, 210, 220)
_G.NameHub = "                                                                                                             Kuma Hub | Premium Script - Blox Fruits |"..os.date('%A, %B %d %Y ')

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local tween = game:GetService("TweenService")
local Red = {RainbowColorValue = 0, HueSelectionPosition = 0}
local PresetColor = _G.ColorMethod


coroutine.wrap(
	function()
		while wait() do
			Red.RainbowColorValue = Red.RainbowColorValue + 1 / 255
			Red.HueSelectionPosition = Red.HueSelectionPosition + 1

			if Red.RainbowColorValue >= 1 then
				Red.RainbowColorValue = 0
			end

			if Red.HueSelectionPosition == 160 then
				Red.HueSelectionPosition = 0
			end
		end
	end
)()

local Reduisceen = Instance.new("ScreenGui")
Reduisceen.Parent = game.CoreGui
Reduisceen.Name = "KumaHubGui"
Reduisceen.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

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

local function Tween(instance, properties,style,wa)
	if style == nil or "" then
		return Back
	end
	tween:Create(instance,TweenInfo.new(wa,Enum.EasingStyle[style]),{properties}):Play()
end


function Windows()

	local MainSceen = Instance.new("Frame")
	MainSceen.Name = "MainSceen"
	MainSceen.Parent = Reduisceen
	MainSceen.AnchorPoint = Vector2.new(0.5, 0.5)
	MainSceen.BackgroundColor3 = Color3.fromRGB(10,10,10)
	MainSceen.BorderSizePixel = 0
	MainSceen.Position = UDim2.new(0.5, 0, 0.5, 0)
	MainSceen.Size = UDim2.new(0, 0, 0, 0)
	MainSceen.ClipsDescendants = true

	local Main_UiConner  = Instance.new("UICorner")

	Main_UiConner.CornerRadius = UDim.new(0, 4)
	Main_UiConner.Name = "Main_UiConner"
	Main_UiConner.Parent = MainSceen

	local ClickFrame = Instance.new("Frame")
	ClickFrame.Name = "ClickFrame"
	ClickFrame.Parent = MainSceen
	ClickFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	ClickFrame.BackgroundColor3 = Color3.fromRGB(255,255,255)
	ClickFrame.BorderSizePixel = 0
	ClickFrame.Position = UDim2.new(0.5, 0, 0.036, 0)
	ClickFrame.Size = UDim2.new(0, 534-20, 0, 30)
	ClickFrame.ClipsDescendants = true
	ClickFrame.BackgroundTransparency = 1

	MakeDraggable(MainSceen,ClickFrame)
	local tween = game:GetService("TweenService")
	local library = {currenttab = '',toggledui = false}
	tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back),{Size = UDim2.new(0, 550, 0, 375)}):Play()


	game:GetService("UserInputService").InputBegan:Connect(function(input)
		if input.KeyCode == Enum.KeyCode.RightControl then 
			if library.toggledui == false then
				library.toggledui = true  
				tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back,Enum.EasingDirection.In),{Size = UDim2.new(0, 0, 0, 0)}):Play()
			else 
				library.toggledui = false 
				tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back),{Size = UDim2.new(0, 550, 0, 375)}):Play()
			end 
		end
	end)
	
   --[[ local TextButton7 = Instance.new("TextButton")
    TextButton7.AnchorPoint = Vector2.new(0.5, 0.5)
    TextButton7.ClipsDescendants = true
    TextButton7.Position = UDim2.new(0.94, 0, 0.3, 0)
    TextButton7.BorderSizePixel = 0
    TextButton7.BackgroundColor3 = Color3.fromRGB(85, 170, 255)
    TextButton7.AutoButtonColor = false
    TextButton7.FontSize = Enum.FontSize.Size11
    TextButton7.TextSize = 11
    TextButton7.TextColor3 = Color3.fromRGB(109, 109, 109)
    TextButton7.Text = ""
    TextButton7.Font = Enum.Font.GothamSemibold
    TextButton7.TextXAlignment = Enum.TextXAlignment.Left
    TextButton7.Parent = Reduisceen
    
    local TextButton7_UiConner = Instance.new("UICorner")

    TextButton7_UiConner.CornerRadius = UDim.new(0, 9)
    TextButton7_UiConner.Name = "Main_UiConner"
    TextButton7_UiConner.Parent = TextButton7

    local TextButton8 = Instance.new("TextButton")
    TextButton8.AnchorPoint = Vector2.new(0.5, 0.5)
    TextButton8.Size = UDim2.new(0, 198, 0, 48)
    TextButton8.ClipsDescendants = true
    TextButton8.Position = UDim2.new(0.5, 0, 0.5, 0)
    TextButton8.BorderSizePixel = 0
    TextButton8.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    TextButton8.AutoButtonColor = false
    TextButton8.FontSize = Enum.FontSize.Size11
    TextButton8.TextSize = 11
    TextButton8.TextColor3 = Color3.fromRGB(45, 45, 45)
    TextButton8.Text = ""
    TextButton8.Font = Enum.Font.GothamSemibold
    TextButton8.Parent = TextButton7

    local TextButton8_UiConner = Instance.new("UICorner")

    TextButton8_UiConner.CornerRadius = UDim.new(0, 9)
    TextButton8_UiConner.Name = "Main_UiConner"
    TextButton8_UiConner.Parent = TextButton8

    local TextLabel13 = Instance.new("TextLabel")
    TextLabel13.AnchorPoint = Vector2.new(0.5, 0.5)
    TextLabel13.Size = UDim2.new(0, 198, 0, 50)
    TextLabel13.ClipsDescendants = true
    TextLabel13.BackgroundTransparency = 1
    TextLabel13.Position = UDim2.new(0.5, 0, 0.5, 0)
    TextLabel13.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel13.TextSize = 13
    TextLabel13.TextColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel13.Text = "Ui Toggle : \nRightControl"
    TextLabel13.TextWrap = true
    TextLabel13.Font = Enum.Font.GothamSemibold
    TextLabel13.TextWrapped = true
    TextLabel13.Parent = TextButton8]]--


    --[[KeyButton.MouseButton1Click:Connect(function()
        KeyButton.Text = "..."
        local inputwait = UserInputService.InputBegan:wait()
        if inputwait.KeyCode.Name ~= "Unknown" then
            getgenv().Settings.Key = inputwait.KeyCode
            KeyButton.Text = "[ " .. inputwait.KeyCode.Name .. " ]"
            TextLabel13.Text = "Ui Toggle : " .. inputwait.KeyCode.Name

            Key = inputwait.KeyCode.Name
        end
    end)]]--


	local library = {toggledui = false;}
	game:GetService("UserInputService").InputBegan:Connect(function(input)
		if input.KeyCode == Enum.KeyCode.RightControl then
			if library.toggledui == false then
				library.toggledui = true
				tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back,Enum.EasingDirection.In),{Size = UDim2.new(0, 0, 0, 0)}):Play()
				wait(0.2)
				TweenService:Create(
					TextButton7,
					TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 220, 0, 50)}
				):Play()
				TweenService:Create(
					TextButton77,
					TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 217, 0, 47)}
				):Play()
                --[[wait(9000)
                wait(.51)
                if TextButton7.Size.Y.Offset == UDim2.new(0, 0, 0, 0) then
                    Reduisceen.Enabled = false
                end]]--
			else
				Reduisceen.Enabled = true
				TweenService:Create(
					TextButton7,
					TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
					{Size = UDim2.new(0, 0, 0, 0)}
				):Play()
				TweenService:Create(
					TextButton77,
					TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
					{Size = UDim2.new(0, 0, 0, 0)}
				):Play()
				tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back),{Size = UDim2.new(0, 550, 0, 375)}):Play()
				repeat wait() until MainSceen.Size == UDim2.new(0, 550, 0, 375)
				library.toggledui = false
				if MainSceen.Size == UDim2.new(0, 550, 0, 375) then
					Reduisceen.Enabled = true
				end
			end
		end
	end)
	function UISetToggle(Set)
		if not Set then
			library.toggledui = true
			TweenService:Create(
				MainSceen,
				TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
				{Size = UDim2.new(0, 0, 0, 0)}
			):Play()
			wait(0.2)
			TweenService:Create(
				TextButton7,
				TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out),
				{Size = UDim2.new(0, 220, 0, 50)}
			):Play()
			TweenService:Create(
				TextButton77,
				TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
				{Size = UDim2.new(0, 210, 0, 50)}
			):Play()
			wait(2)
			TweenService:Create(
				TextButton7,
				TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
				{Size = UDim2.new(0, 0, 0, 0)}
			):Play()
			TweenService:Create(
				TextButton77,
				TweenInfo.new(.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In),
				{Size = UDim2.new(0, 0, 0, 0)}
			):Play()
			wait(.5)
			Reduisceen.Enabled = false
		else
			Reduisceen.Enabled = true
			tween:Create(MainSceen,TweenInfo.new(0.4,Enum.EasingStyle.Back),{Size = UDim2.new(0, 450,0, 325)}):Play()
			repeat wait() until MainSceen.Size == UDim2.new(0, 450,0, 325)
			library.toggledui = true
			Reduisceen.Enabled = true
		end
	end

	if Config and Config.HideUI then
		UISetToggle(false)
	end

	local NameReal = Instance.new("TextLabel")

	NameReal.Parent = MainSceen
	NameReal.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	NameReal.BackgroundTransparency = 1
	NameReal.BorderSizePixel = 0
	NameReal.Position = UDim2.new(0.1, 0, 0.04, 0)
	NameReal.AnchorPoint = Vector2.new(0.5, 0.5)
	NameReal.Size = UDim2.new(0, 136, 0, 34)
	NameReal.Font = Enum.Font.GothamBold
	NameReal.Text = _G.NameHub
	NameReal.TextColor3 = Color3.fromRGB(255, 255, 255)
	NameReal.TextSize = 14.000

	local MainSceen2 = Instance.new("Frame")
	MainSceen2.Name = "MainSceen2"
	MainSceen2.Parent = MainSceen
	MainSceen2.AnchorPoint = Vector2.new(0.5, 0.5)
	MainSceen2.BackgroundColor3 = Color3.fromRGB(15,15,15)--Color3.fromRGB(18,18,18)
	MainSceen2.BorderSizePixel = 0
	MainSceen2.Position = UDim2.new(0.5, 0, 0.5, 0)
	MainSceen2.Size = UDim2.new(0, 530-15, 0,300)
	MainSceen2.ClipsDescendants = true

	local Main_UiConner2  = Instance.new("UICorner")

	Main_UiConner2.CornerRadius = UDim.new(0, 4)
	Main_UiConner2.Name = "Main_UiConner"
	Main_UiConner2.Parent = MainSceen

	local ScolTapBarFrame = Instance.new("Frame")
	ScolTapBarFrame.Name = "MainSceen2"
	ScolTapBarFrame.Parent = MainSceen2
	ScolTapBarFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	ScolTapBarFrame.BackgroundColor3 = Color3.fromRGB(255,255,255)
	ScolTapBarFrame.BorderSizePixel = 0
	ScolTapBarFrame.BackgroundTransparency = 1
	ScolTapBarFrame.Position = UDim2.new(0.5, 0, 0.07, 0)
	ScolTapBarFrame.Size = UDim2.new(0, 500, 0, 35)
	ScolTapBarFrame.ClipsDescendants = true

	local ScrollingFrame_Menubar = Instance.new("ScrollingFrame")

	ScrollingFrame_Menubar.Parent = ScolTapBarFrame
	ScrollingFrame_Menubar.Active = true
	ScrollingFrame_Menubar.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScrollingFrame_Menubar.BackgroundTransparency = 1.000
	ScrollingFrame_Menubar.BorderSizePixel = 0
	ScrollingFrame_Menubar.Position = UDim2.new(0, 0, 0.086, 0)
	ScrollingFrame_Menubar.Size = UDim2.new(0, 500, 0, 30)
	ScrollingFrame_Menubar.CanvasSize = UDim2.new(0, 0, 0, 0)
	ScrollingFrame_Menubar.ScrollBarThickness = 0.00


	local UIListLayout_Menubar = Instance.new("UIListLayout")

	UIListLayout_Menubar.Parent = ScrollingFrame_Menubar
	UIListLayout_Menubar.FillDirection = Enum.FillDirection.Horizontal
	UIListLayout_Menubar.SortOrder = Enum.SortOrder.LayoutOrder
	UIListLayout_Menubar.Padding = UDim.new(0, 10)

	local UIPadding_Menubar = Instance.new("UIPadding")

	UIPadding_Menubar.Parent = ScrollingFrame_Menubar
	UIPadding_Menubar.PaddingTop = UDim.new(0, 2)


	local PageOrders = -1

	local Container_Page = Instance.new('Frame',MainSceen2)
	Container_Page.Size = UDim2.new(0, 518, 0, 200)
	Container_Page.Position = UDim2.new(0.5, 0, 0.45, 0)
	Container_Page.BackgroundTransparency = 1
	Container_Page.Name = "Page "
	Container_Page.AnchorPoint = Vector2.new(0.5, 0.5)

	local pagesFolder = Instance.new("Folder")

	pagesFolder.Name = "pagesFolder"
	pagesFolder.Parent = Container_Page


	local UIPage = Instance.new('UIPageLayout',pagesFolder)
	UIPage.SortOrder = Enum.SortOrder.LayoutOrder
	UIPage.EasingDirection = Enum.EasingDirection.InOut
	UIPage.EasingStyle = Enum.EasingStyle.Quad
	UIPage.Padding = UDim.new(0, 10)
	UIPage.TweenTime = 0.500

	local top = {}

	local NotiFrame = Instance.new("Frame")
	NotiFrame.Name = "NotiFrame"
	NotiFrame.Parent = Reduisceen
	NotiFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	NotiFrame.BackgroundColor3 = Color3.fromRGB(18,18,18)
	NotiFrame.BorderSizePixel = 0
	NotiFrame.Position =  UDim2.new(1, -210, 1, -500)
	NotiFrame.Size = UDim2.new(0, 300,0, 320)
	NotiFrame.ClipsDescendants = true
	NotiFrame.BackgroundTransparency = 1


	local Notilistlayout = Instance.new("UIListLayout")
	Notilistlayout.Parent = NotiFrame
	Notilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
	Notilistlayout.Padding = UDim.new(0, 5)

	function top:AddTab(text)
		PageOrders = PageOrders + 1
		local name = tostring(text) or tostring(math.random(1,5000))

		local Frame_Tap = Instance.new("Frame")
		Frame_Tap.Parent = ScrollingFrame_Menubar
		Frame_Tap.Name = text.."Server"
		Frame_Tap.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Frame_Tap.BackgroundTransparency = 1
		Frame_Tap.Position = UDim2.new(0.0, 0, 0.0, 0)
		Frame_Tap.Size = UDim2.new(0, 100, 0, 25)
		Frame_Tap.Visible = true

		local TextLabel_Tap = Instance.new("TextLabel")

		TextLabel_Tap.Parent = Frame_Tap
		TextLabel_Tap.Name = "TextLabel_Tap"
		TextLabel_Tap.BackgroundColor3 = _G.ColorMethod
		TextLabel_Tap.Position = UDim2.new(0.5, 0, 0.8, 0)
		TextLabel_Tap.Size = UDim2.new(0, 0, 0, 0)
		TextLabel_Tap.Font = Enum.Font.SourceSans
		TextLabel_Tap.Text = " "
		TextLabel_Tap.TextColor3 = Color3.fromRGB(0, 0, 0)
		TextLabel_Tap.TextSize = 14.000
		TextLabel_Tap.AnchorPoint = Vector2.new(0.5, 0.5)

		local TextButton_Tap = Instance.new("TextButton")

		TextButton_Tap.Parent = Frame_Tap
		TextButton_Tap.Name = "TextButton_Tap"
		TextButton_Tap.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TextButton_Tap.BackgroundTransparency = 1.000
		TextButton_Tap.Position = UDim2.new(0.114, 0,-0.001, 0)
		TextButton_Tap.Size = UDim2.new(0, 80, 0, 20)
		TextButton_Tap.Font = Enum.Font.GothamSemibold
		TextButton_Tap.TextColor3 = Color3.fromRGB(155, 155, 155)
		TextButton_Tap.TextSize = 13.000
		TextButton_Tap.Text = tostring(text)

		local MainPage = Instance.new("Frame")

		MainPage.Name = name.."_MainPage"
		MainPage.Parent = pagesFolder
		MainPage.BackgroundColor3 = Color3.fromRGB(255,255, 255)
		MainPage.BorderSizePixel = 0
		MainPage.Position = UDim2.new(0.5, 0, 0.5, 0) -- UDim2.new(0.0149812736, 0, 0.13, 0)
		MainPage.Size = UDim2.new(0, 518, 0, 375)
		MainPage.BackgroundTransparency = 1
		MainPage.ClipsDescendants = true
		MainPage.Visible = true
		MainPage.LayoutOrder = PageOrders




		TextButton_Tap.MouseButton1Click:connect(function()
			if MainPage.Name == text.."_MainPage" then
				UIPage:JumpToIndex(MainPage.LayoutOrder)

			end
			for i ,v in next , ScrollingFrame_Menubar:GetChildren() do
				if v:IsA("Frame") then
					TweenService:Create(
						v.TextButton_Tap,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)}
					):Play()
				end

				TweenService:Create(
					TextButton_Tap,
					TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{TextColor3 = _G.ColorMethod}
				):Play()
			end
		end)

		if fs == false then
			-- TweenService:Create(
			--     TextLabel_Tap,
			--     TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
			--     {Size = UDim2.new(0, 70, 0, 2)}
			-- ):Play()
			TweenService:Create(
				TextButton_Tap,
				TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{TextColor3 = _G.ColorMethod}
			):Play()

			MainPage.Visible = true
			Frame_Tap.Name  = text .. "Server"
			fs  = true
		end
		local ScrollingFrame_Pagefrist = Instance.new("ScrollingFrame")

		ScrollingFrame_Pagefrist.Parent = MainPage
		ScrollingFrame_Pagefrist.Active = true
		ScrollingFrame_Pagefrist.BackgroundColor3 = Color3.fromRGB(10, 10, 10) -- 249, 53, 139
		ScrollingFrame_Pagefrist.BorderSizePixel = 0
		ScrollingFrame_Pagefrist.Size = UDim2.new(0, 518, 0, 250)
		ScrollingFrame_Pagefrist.ScrollBarThickness = 4
		ScrollingFrame_Pagefrist.ScrollBarImageColor3 = _G.ColorMethod -- 249, 53, 139

		local UIGridLayout_Pagefrist = Instance.new("UIGridLayout")
		local UIPadding_Pagefrist = Instance.new("UIPadding")

		UIGridLayout_Pagefrist.Archivable = false
		UIGridLayout_Pagefrist.Parent = ScrollingFrame_Pagefrist
		UIGridLayout_Pagefrist.SortOrder = Enum.SortOrder.LayoutOrder
		UIGridLayout_Pagefrist.CellPadding = UDim2.new(0, 13, 0, 15)
		UIGridLayout_Pagefrist.CellSize = UDim2.new(0, 240, 0, 370)

		UIPadding_Pagefrist.Parent = ScrollingFrame_Pagefrist
		UIPadding_Pagefrist.PaddingLeft = UDim.new(0, 10)
		UIPadding_Pagefrist.PaddingTop = UDim.new(0, 20)

		local page = {}

		function page:newpage()

			local Pageframe = Instance.new("Frame")


			Pageframe.Parent = ScrollingFrame_Pagefrist
			Pageframe.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Pageframe.BorderSizePixel = 0
			Pageframe.Position = UDim2.new(0.028957529, 0, 0.0496277921, 0)
			Pageframe.Size = UDim2.new(0, 240, 0, 379)


			local ScrollingFrame_Pageframe = Instance.new("ScrollingFrame")


			ScrollingFrame_Pageframe.Parent = Pageframe
			ScrollingFrame_Pageframe.Active = true
			ScrollingFrame_Pageframe.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			ScrollingFrame_Pageframe.BorderSizePixel = 0
			ScrollingFrame_Pageframe.Position = UDim2.new(0, 0, -0.0101253344, 0)
			ScrollingFrame_Pageframe.Size = UDim2.new(0, 240, 0, 379)
			ScrollingFrame_Pageframe.ScrollBarThickness = 4
			ScrollingFrame_Pageframe.ScrollBarImageColor3 = Color3.fromRGB(222, 222, 222)



			local UIPadding_Pageframe = Instance.new("UIPadding")
			local UIListLayout_Pageframe = Instance.new("UIListLayout")


			UIPadding_Pageframe.Parent = ScrollingFrame_Pageframe
			UIPadding_Pageframe.PaddingLeft = UDim.new(0, 15)
			UIPadding_Pageframe.PaddingTop = UDim.new(0, 10)


			UIListLayout_Pageframe.Parent = ScrollingFrame_Pageframe
			UIListLayout_Pageframe.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout_Pageframe.Padding = UDim.new(0, 7)

			UIListLayout_Pageframe:GetPropertyChangedSignal('AbsoluteContentSize'):Connect(function()
				ScrollingFrame_Pageframe.CanvasSize = UDim2.new(0,0,0,UIListLayout_Pageframe.AbsoluteContentSize.Y + 120 )
			end)

			UIGridLayout_Pagefrist:GetPropertyChangedSignal('AbsoluteContentSize'):Connect(function()
				ScrollingFrame_Pagefrist.CanvasSize = UDim2.new(0,0,0,UIGridLayout_Pagefrist.AbsoluteContentSize.Y + 50 )
			end)

			game:GetService("RunService").Stepped:Connect(function ()
				pcall(function ()
					ScrollingFrame_Menubar.CanvasSize = UDim2.new(0,  UIListLayout_Menubar.AbsoluteContentSize.X, 0,0)
					ScrollingFrame_Pageframe.CanvasSize = UDim2.new(0,0,0,UIListLayout_Pageframe.AbsoluteContentSize.Y +20 )
					ScrollingFrame_Pagefrist.CanvasSize = UDim2.new(0,0,0,UIGridLayout_Pagefrist.AbsoluteContentSize.Y + 40)
				end)
			end)
			local items = {}

			function items:AddToggle(text,config,callback)
				local Toggle = Instance.new("Frame")

				Toggle.Parent = ScrollingFrame_Pageframe
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.BorderSizePixel = 0
				Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
				Toggle.Size = UDim2.new(0, 213, 0, 35)
				Toggle.BackgroundTransparency = 1
				Toggle.AnchorPoint = Vector2.new(0.5, 0.5)

				local TextButton_Toggle = Instance.new("TextButton")

				TextButton_Toggle.Parent = Toggle
				TextButton_Toggle.BackgroundTransparency =1
				TextButton_Toggle.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TextButton_Toggle.BorderSizePixel = 0
				TextButton_Toggle.Size = UDim2.new(0, 213, 0, 35)
				TextButton_Toggle.AutoButtonColor = false
				TextButton_Toggle.Font = Enum.Font.SourceSans
				TextButton_Toggle.Text = " "
				TextButton_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_Toggle.TextSize = 12.000

				local TextButton_2_Toggle = Instance.new("TextButton")

				TextButton_2_Toggle.Parent = TextButton_Toggle
				TextButton_2_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155, 155)
				--        TextButton_2_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_2_Toggle.BorderSizePixel = 0
				TextButton_2_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_2_Toggle.Position = UDim2.new(0.9, 0, 0.5, 0)
				TextButton_2_Toggle.Size = UDim2.new(0, 30, 0, 13)
				TextButton_2_Toggle.Font = Enum.Font.SourceSans
				TextButton_2_Toggle.Text = " "
				TextButton_2_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_2_Toggle.TextSize = 12.000
				TextButton_2_Toggle.AutoButtonColor = false

				local TextButton_Pageframe_Uiconner = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner.Name = ""
				TextButton_Pageframe_Uiconner.Parent = TextButton_2_Toggle

				local TextButton_3_Toggle = Instance.new("TextButton")

				TextButton_3_Toggle.Parent = TextButton_2_Toggle
				TextButton_3_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255,255)
				--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_3_Toggle.BorderSizePixel = 0
				TextButton_3_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_3_Toggle.Position = UDim2.new(0.1, 0, 0.5, 0)
				TextButton_3_Toggle.Size = UDim2.new(0, 19, 0, 19)
				TextButton_3_Toggle.Font = Enum.Font.SourceSans
				TextButton_3_Toggle.Text = " "
				TextButton_3_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_3_Toggle.TextSize = 12.000
				TextButton_3_Toggle.AutoButtonColor = false

				local TextButton_Pageframe_Uiconner2 = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner2.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner2.Name = ""
				TextButton_Pageframe_Uiconner2.Parent = TextButton_3_Toggle

				local TextButton_4_Toggle = Instance.new("TextButton")

				TextButton_4_Toggle.Parent = TextButton_3_Toggle
				TextButton_4_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155,155)
				--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_4_Toggle.BorderSizePixel = 0
				TextButton_4_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_4_Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
				TextButton_4_Toggle.Size = UDim2.new(0, 27, 0, 27-2)
				TextButton_4_Toggle.Font = Enum.Font.SourceSans
				TextButton_4_Toggle.Text = " "
				TextButton_4_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_4_Toggle.TextSize = 12.000
				TextButton_4_Toggle.AutoButtonColor = false
				TextButton_4_Toggle.BackgroundTransparency = 1
				TextButton_4_Toggle.Visible = true

				local TextButton_Pageframe_Uiconner4 = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner4.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner4.Name = ""
				TextButton_Pageframe_Uiconner4.Parent = TextButton_4_Toggle

				local TextLabel_Toggle = Instance.new("TextLabel")

				TextLabel_Toggle.Parent = Toggle
				TextLabel_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextLabel_Toggle.BackgroundTransparency = 1
				TextLabel_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextLabel_Toggle.Position = UDim2.new(0.4, 0, 0.5, 0)
				TextLabel_Toggle.BorderSizePixel = 0
				TextLabel_Toggle.Size = UDim2.new(0, 130, 0, 25)
				TextLabel_Toggle.Font = Enum.Font.GothamSemibold
				TextLabel_Toggle.Text = text
				TextLabel_Toggle.TextColor3 = Color3.fromRGB(200, 200, 200)
				TextLabel_Toggle.TextSize = 13.000
				TextLabel_Toggle.ClipsDescendants = true
				TextLabel_Toggle.TextWrapped = true
				TextLabel_Toggle.TextXAlignment = Enum.TextXAlignment.Left

				local TextButton_Toggle2 = Instance.new("TextButton")

				TextButton_Toggle2.Parent = TextButton_Toggle
				TextButton_Toggle2.BackgroundTransparency =1
				TextButton_Toggle2.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TextButton_Toggle2.BorderSizePixel = 0
				TextButton_Toggle2.Size = UDim2.new(0, 213, 0, 35)
				TextButton_Toggle2.AutoButtonColor = false
				TextButton_Toggle2.Font = Enum.Font.SourceSans
				TextButton_Toggle2.Text = " "
				TextButton_Toggle2.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_Toggle2.TextSize = 12.000

				TextButton_Toggle2.MouseEnter:Connect(function()
					TweenService:Create(
						TextButton_4_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.6} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextLabel_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				TextButton_Toggle2.MouseLeave:Connect(function()
					TweenService:Create(
						TextButton_4_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextLabel_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(200, 200, 200)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				local check = {toogle = false ; loacker = true ; togfunction = {

				};
				}
				TextButton_Toggle2.MouseButton1Click:Connect(function()
					if check.toogle == false and check.loacker == true  then
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255,255,255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
					elseif  check.loacker ==  true then
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(0.1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
					end
					if  check.loacker == true  then
						check.toogle = not check.toogle
						callback(check.toogle)
					end
				end
				)

				if config == true then
					TweenService:Create(
						TextButton_4_Toggle,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 =  Color3.fromRGB(200, 200, 200)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextButton_3_Toggle,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 =  Color3.fromRGB(200, 200, 200)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						TextButton_2_Toggle,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
					check.toogle = true
					callback(check.toogle)
				end

				local lockerframe = Instance.new("Frame")

				lockerframe.Name = "lockerframe"
				lockerframe.Parent = Toggle
				lockerframe.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				lockerframe.BackgroundTransparency = 1
				lockerframe.Size = UDim2.new(0, 320, 0, 35)
				lockerframe.Position = UDim2.new(0.5, 0, 0.5, 0)
				lockerframe.AnchorPoint = Vector2.new(0.5, 0.5)

				local LockerImageLabel = Instance.new("ImageLabel")
				LockerImageLabel.Parent = lockerframe
				LockerImageLabel.BackgroundTransparency = 1.000
				LockerImageLabel.BorderSizePixel = 0
				LockerImageLabel.Position = UDim2.new(0.5, 0, 0.5, 0)
				LockerImageLabel.AnchorPoint = Vector2.new(0.5, 0.5)
				LockerImageLabel.Size = UDim2.new(0, 0, 0, 0)
				LockerImageLabel.Image = "http://www.roblox.com/asset/?id=6031082533"


				function check.togfunction:lock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 0.7}
					):Play()
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 30, 0, 30)}
					):Play()

					check.loacker  = false
					--    pcall(callback,locker)
				end
				function check.togfunction:unlock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 1}
					):Play()
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 0, 0, 0)}
					):Play()
					check.loacker  = true
					--   pcall(callback,locker)
				end

				return  check.togfunction
			end

			function items:Button(text,callback)

				local ButtonFrame = Instance.new("Frame")

				ButtonFrame.Name = "ButtonFrame"
				ButtonFrame.Parent = ScrollingFrame_Pageframe
				ButtonFrame.BackgroundColor3 = _G.ColorMethod
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
				MheeFrameStroke.Color = _G.ColorMethod
				MheeFrameStroke.Transparency = 0.7

				local Button = Instance.new("TextButton")

				Button.Parent = ButtonFrame
				Button.Name = "Button"
				Button.BackgroundColor3 = _G.ColorMethod
				Button.Size = UDim2.new(0,150, 0, 25)
				Button.Font = Enum.Font.SourceSansSemibold
				Button.Text = tostring(text)
				Button.TextColor3 = Color3.fromRGB(155, 155, 155)
				Button.TextSize = 13.000
				Button.AnchorPoint = Vector2.new(0.5, 0.5)
				Button.Position = UDim2.new(0.5, 0, 0.5, 0)
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
						{Size =  UDim2.new(0, 213, 0, 25)} -- UDim2.new(0, 128, 0, 25)
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
					--    Ripple(Button)
					callback()
					TweenService:Create(
						Button,
						TweenInfo.new(0.2, Enum.EasingStyle.Back, Enum.EasingDirection.Out),
						{TextSize =  16} -- UDim2.new(0, 128, 0, 25)
					):Play()
					wait(0.1)
					TweenService:Create(
						Button,
						TweenInfo.new(0.2, Enum.EasingStyle.Back, Enum.EasingDirection.Out),
						{TextSize =  13} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

			end

			function items:AddSlider(text,check,floor,min,max,de,lol,tog,callback)

				if check then

					local SliderFrame = Instance.new("Frame")

					SliderFrame.Name = "SliderFrame"
					SliderFrame.Parent = ScrollingFrame_Pageframe
					SliderFrame.BackgroundColor3 =  Color3.fromRGB(28, 28, 28)-- _G.ColorMethod
					SliderFrame.BorderSizePixel = 0
					SliderFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
					SliderFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					SliderFrame.Size = UDim2.new(0, 213, 0, 75) -- UDim2.new(0, 213, 0, 35)
					SliderFrame.BackgroundTransparency  = 0
					SliderFrame.ClipsDescendants = true

					local SliderFrameConner = Instance.new("UICorner")

					SliderFrameConner.CornerRadius = UDim.new(0, 4)
					SliderFrameConner.Name = ""
					SliderFrameConner.Parent = SliderFrame

					local SliderFrameStroke = Instance.new("UIStroke")

					SliderFrameStroke.Thickness = 1
					SliderFrameStroke.Name = ""
					SliderFrameStroke.Parent = SliderFrame
					SliderFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
					SliderFrameStroke.Color = _G.ColorMethod
					SliderFrameStroke.Transparency = 0.7


					SliderFrame.MouseEnter:Connect(function()
						TweenService:Create(
							SliderFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					SliderFrame.MouseLeave:Connect(function()
						TweenService:Create(
							SliderFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0.7} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)


					local LabelNameSliderxd = Instance.new("TextLabel")

					LabelNameSliderxd.Parent = SliderFrame
					LabelNameSliderxd.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					LabelNameSliderxd.BackgroundTransparency = 1
					LabelNameSliderxd.BorderSizePixel = 0
					LabelNameSliderxd.Position = UDim2.new(0.35, 0, 0.2, 0)
					LabelNameSliderxd.AnchorPoint = Vector2.new(0.5, 0.5)
					LabelNameSliderxd.Size = UDim2.new(0, 120, 0, 20)
					LabelNameSliderxd.Font = Enum.Font.GothamBold
					LabelNameSliderxd.Text = tostring(text)
					LabelNameSliderxd.TextColor3 = Color3.fromRGB(255, 255, 255)
					LabelNameSliderxd.TextSize = 11.000
					LabelNameSliderxd.TextXAlignment = Enum.TextXAlignment.Left


					local ShowValueFarm = Instance.new("Frame")

					ShowValueFarm.Name = "ShowValueFarm"
					ShowValueFarm.Parent = SliderFrame
					ShowValueFarm.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
					ShowValueFarm.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					ShowValueFarm.Size = UDim2.new(0, 75, 0, 15)
					ShowValueFarm.BackgroundTransparency = 0
					ShowValueFarm.BorderSizePixel = 0
					ShowValueFarm.AnchorPoint = Vector2.new(0.5, 0.5)
					ShowValueFarm.Position = UDim2.new(0.8, 0, 0.2, 0)
					ShowValueFarm.ClipsDescendants = false

					local CustomValue = Instance.new("TextBox")

					CustomValue.Parent = ShowValueFarm
					CustomValue.BackgroundColor3 = Color3.fromRGB(45,45, 45)
					CustomValue.BorderSizePixel = 0
					CustomValue.ClipsDescendants = true
					CustomValue.AnchorPoint = Vector2.new(0.5, 0.5)
					CustomValue.Position = UDim2.new(0.5, 0, 0.5, 0)
					CustomValue.Size = UDim2.new(0, 158, 0, 26)
					CustomValue.Font = Enum.Font.GothamSemibold
					CustomValue.PlaceholderColor3 = Color3.fromRGB(222, 222, 222)
					CustomValue.PlaceholderText =  ""
					if floor == true then
						CustomValue.Text =  tostring(de and string.format("%.1f",(de / max) * (max - min) + min) or 0)
					else
						CustomValue.Text =  tostring(de and math.floor( (de / max) * (max - min) + min) or 0)
					end
					CustomValue.TextColor3 = Color3.fromRGB(255, 255, 255)
					CustomValue.TextSize = 8.000
					CustomValue.BackgroundTransparency = 1

					local ValueFrame = Instance.new("Frame")

					ValueFrame.Name = "ValueFrame"
					ValueFrame.Parent = SliderFrame
					ValueFrame.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
					ValueFrame.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					ValueFrame.Size = UDim2.new(0, 140, 0, 5)
					ValueFrame.BackgroundTransparency = 0
					ValueFrame.BorderSizePixel = 0
					ValueFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					ValueFrame.Position = UDim2.new(0.4, 0, 0.8, 0)
					ValueFrame.ClipsDescendants = false


					local PartValue = Instance.new("Frame")

					PartValue.Name = "PartValue"
					PartValue.Parent = ValueFrame
					PartValue.BackgroundColor3 = Color3.fromRGB(222, 222, 222)
					PartValue.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					PartValue.Size = UDim2.new(0, 140, 0, 5)
					PartValue.BackgroundTransparency = 1
					PartValue.BorderSizePixel = 0
					PartValue.AnchorPoint = Vector2.new(0.5, 0.5)
					PartValue.Position = UDim2.new(0.5, 0, 0.5, 0)
					PartValue.ClipsDescendants = false

					local MainValue = Instance.new("Frame")

					MainValue.Name = "MainValue"
					MainValue.Parent = PartValue
					MainValue.BackgroundColor3 = _G.ColorMethod
					MainValue.Size = UDim2.new((de or 0) / max, 0, 0, 5)
					MainValue.BackgroundTransparency = 0
					MainValue.BorderSizePixel = 0
					-- MainValue.AnchorPoint = Vector2.new(0.5, 0.5)
					MainValue.Position = UDim2.new(0., 0, 0.0, 0)
					MainValue.ClipsDescendants = false

					local Conner_S1 = Instance.new("UICorner")

					Conner_S1.CornerRadius = UDim.new(0, 8)
					Conner_S1.Name = ""
					Conner_S1.Parent = MainValue

					local Conner_S2 = Instance.new("UICorner")

					Conner_S2.CornerRadius = UDim.new(0, 8)
					Conner_S2.Name = ""
					Conner_S2.Parent = ValueFrame

					local ConneValue = Instance.new("Frame")

					ConneValue.Name = "ConneValue"
					ConneValue.Parent = PartValue
					ConneValue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					ConneValue.Size = UDim2.new(0, 13, 0,13)
					ConneValue.BackgroundTransparency = 0
					ConneValue.BorderSizePixel = 0
					ConneValue.AnchorPoint = Vector2.new(0.5, 0.5)
					ConneValue.Position = UDim2.new((de or 0)/max, 0.5, 0.3,0.5, 0)
					ConneValue.ClipsDescendants = false


					local Conner_Conne = Instance.new("UICorner")

					Conner_Conne.CornerRadius = UDim.new(0, 300)
					Conner_Conne.Name = ""
					Conner_Conne.Parent = ConneValue

					local Addvalue = Instance.new("ImageButton")

					Addvalue.Name = "Imatog"
					Addvalue.Parent = SliderFrame
					Addvalue.BackgroundTransparency = 1.000
					Addvalue.BorderSizePixel = 0
					Addvalue.Position = UDim2.new(0.85, 0, 0.35, 0)
					Addvalue.Size = UDim2.new(0, 15, 0, 15)
					Addvalue.Image = "http://www.roblox.com/asset/?id=6035067836"
					Addvalue.ImageColor3 =  _G.ColorMethod

					local Deletevalue = Instance.new("ImageButton")

					Deletevalue.Name = "Imatog"
					Deletevalue.Parent = SliderFrame
					Deletevalue.BackgroundTransparency = 1.000
					Deletevalue.BorderSizePixel = 0
					Deletevalue.Position = UDim2.new(0.7, 0, 0.35, 0)
					Deletevalue.Size = UDim2.new(0, 15, 0, 15)
					Deletevalue.Image = "http://www.roblox.com/asset/?id=6035047377"
					Deletevalue.ImageColor3 =  _G.ColorMethod


					local TextButton_2_Toggle = Instance.new("TextButton")

					TextButton_2_Toggle.Parent = ValueFrame
					TextButton_2_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155, 155)
					--        TextButton_2_Toggle.BorderColor3 = _G.ColorMethod
					TextButton_2_Toggle.BorderSizePixel = 0
					TextButton_2_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
					TextButton_2_Toggle.Position = UDim2.new(1.25, 0, 0.4, 0)
					TextButton_2_Toggle.Size = UDim2.new(0, 30, 0, 13)
					TextButton_2_Toggle.Font = Enum.Font.SourceSans
					TextButton_2_Toggle.Text = " "
					TextButton_2_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
					TextButton_2_Toggle.TextSize = 12.000
					TextButton_2_Toggle.AutoButtonColor = false

					local TextButton_Pageframe_Uiconner = Instance.new("UICorner")

					TextButton_Pageframe_Uiconner.CornerRadius = UDim.new(0, 30)
					TextButton_Pageframe_Uiconner.Name = ""
					TextButton_Pageframe_Uiconner.Parent = TextButton_2_Toggle

					local TextButton_3_Toggle = Instance.new("TextButton")

					TextButton_3_Toggle.Parent = TextButton_2_Toggle
					TextButton_3_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255,255)
					--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
					TextButton_3_Toggle.BorderSizePixel = 0
					TextButton_3_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
					TextButton_3_Toggle.Position = UDim2.new(0.1, 0, 0.5, 0)
					TextButton_3_Toggle.Size = UDim2.new(0, 19, 0, 19)
					TextButton_3_Toggle.Font = Enum.Font.SourceSans
					TextButton_3_Toggle.Text = " "
					TextButton_3_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
					TextButton_3_Toggle.TextSize = 12.000
					TextButton_3_Toggle.AutoButtonColor = false

					local TextButton_Pageframe_Uiconner2 = Instance.new("UICorner")

					TextButton_Pageframe_Uiconner2.CornerRadius = UDim.new(0, 30)
					TextButton_Pageframe_Uiconner2.Name = ""
					TextButton_Pageframe_Uiconner2.Parent = TextButton_3_Toggle

					local TextButton_4_Toggle = Instance.new("TextButton")

					TextButton_4_Toggle.Parent = TextButton_3_Toggle
					TextButton_4_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155,155)
					--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
					TextButton_4_Toggle.BorderSizePixel = 0
					TextButton_4_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
					TextButton_4_Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
					TextButton_4_Toggle.Size = UDim2.new(0, 27, 0, 27-2)
					TextButton_4_Toggle.Font = Enum.Font.SourceSans
					TextButton_4_Toggle.Text = " "
					TextButton_4_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
					TextButton_4_Toggle.TextSize = 12.000
					TextButton_4_Toggle.AutoButtonColor = false
					TextButton_4_Toggle.BackgroundTransparency = 1
					TextButton_4_Toggle.Visible = true

					local TextButton_Pageframe_Uiconner4 = Instance.new("UICorner")

					TextButton_Pageframe_Uiconner4.CornerRadius = UDim.new(0, 30)
					TextButton_Pageframe_Uiconner4.Name = ""
					TextButton_Pageframe_Uiconner4.Parent = TextButton_4_Toggle


					local TextButton_Toggle = Instance.new("TextButton")

					TextButton_Toggle.Parent = ValueFrame
					TextButton_Toggle.BackgroundTransparency =1
					TextButton_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					TextButton_Toggle.BorderSizePixel = 0
					TextButton_Toggle.Size = UDim2.new(0, 50, 0, 20)
					TextButton_Toggle.AutoButtonColor = false
					TextButton_Toggle.Font = Enum.Font.SourceSans
					TextButton_Toggle.Text = " "
					TextButton_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
					TextButton_Toggle.TextSize = 12.000
					TextButton_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
					TextButton_Toggle.Position = UDim2.new(1.25, 0, 0.4, 0)



					-- local value = de
					local check2 = {toogle2 = false;}
					local function move(input)
						local pos =
							UDim2.new(
								math.clamp((input.Position.X - ValueFrame.AbsolutePosition.X) / ValueFrame.AbsoluteSize.X, 0, 1),
								0,
								0.3,
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
							local value = string.format("%.1f",((pos.X.Scale * max) / max) * (max - min) + min)
							CustomValue.Text = tostring(value)
							--   callback[2] = value
							callback({
								["s"] = value;
								["t"] = check2.toogle2
							})
							--callback({value,check2.toogle2})
							--callback(value)
						else
							local value = math.floor(((pos.X.Scale * max) / max) * (max - min) + min)
							CustomValue.Text = tostring(value)
							callback({
								["s"] = value;
								["t"] = check2.toogle2
							})
							--       callback({value,check2.toogle2})

						end



					end

					local dragging = false
					ConneValue.InputBegan:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = true

							end
						end
					)
					ConneValue.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)
					SliderFrame.InputBegan:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = true

							end
						end
					)
					SliderFrame.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)


					ValueFrame.InputBegan:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = true

							end
						end
					)
					ValueFrame.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)

					game:GetService("UserInputService").InputChanged:Connect(
					function(input)
						if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
							move(input)
						end
					end
					)

					CustomValue.FocusLost:Connect(function()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						if  tonumber(CustomValue.Text) <= min then
							CustomValue.Text  = min
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text or 0) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						callback({
							["s"] =  CustomValue.Text;
							["t"] = check2.toogle2;
						})
						--       callback({ tonumber(CustomValue.Text),check2.toogle2})
						--  pcall(callback, CustomValue.Text)
					end)


					Addvalue.MouseButton1Click:Connect(function ()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						pcall(function()
							CustomValue.Text  = CustomValue.Text  - tonumber(lol)
						end)
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						if  tonumber(CustomValue.Text) < min then
							CustomValue.Text  = min
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text  or 0  ) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0.5, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						callback({
							["s"] =  CustomValue.Text;
							["t"] = check2.toogle2
						})
						--   callback({ tonumber(CustomValue.Text),check2.toogle2})
						--  pcall(callback, CustomValue.Text)
					end)

					Deletevalue.MouseButton1Click:Connect(function ()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						pcall(function()
							CustomValue.Text  = CustomValue.Text  + tonumber(lol)
						end)
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						if  tonumber(CustomValue.Text) < min then
							CustomValue.Text  = min
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text  or 0  ) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0.5, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						callback({
							["s"] =  CustomValue.Text;
							["t"] = check2.toogle2;
						})
						--callback({ tonumber(CustomValue.Text),check2.toogle2})
						--  pcall(callback, CustomValue.Text)
					end)




					---
					TextButton_Toggle.MouseEnter:Connect(function()
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundTransparency = 0.6} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					TextButton_Toggle.MouseLeave:Connect(function()
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundTransparency = 1} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)



					TextButton_Toggle.MouseButton1Click:Connect(function()
						if check2.toogle2 == false   then
							TweenService:Create(
								TextButton_4_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								TextButton_3_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								TextButton_2_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  Color3.fromRGB(153, 0, 102)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
						else
							TweenService:Create(
								TextButton_4_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								TextButton_3_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								TextButton_2_Toggle,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(0.1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
						end
						check2.toogle2 = not check2.toogle2
						callback({
							["t"] = check2.toogle2;

						})
						--   callback({value,check2.toogle2})
						--callback(check2.toogle2)
					end
					)

					if tog == true then
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(153, 0, 102)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
						check2.toogle2 = true
						callback({
							["t"] = check2.toogle2;
						})
						--        callback({value,check2.toogle2})
						--  callback(check2.toogle2)
					end


				else
					tog = nil
					local SliderFrame = Instance.new("Frame")

					SliderFrame.Name = "SliderFrame"
					SliderFrame.Parent = ScrollingFrame_Pageframe
					SliderFrame.BackgroundColor3 =  Color3.fromRGB(28, 28, 28)-- _G.ColorMethod
					SliderFrame.BorderSizePixel = 0
					SliderFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
					SliderFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					SliderFrame.Size = UDim2.new(0, 213, 0, 75) -- UDim2.new(0, 213, 0, 35)
					SliderFrame.BackgroundTransparency  = 0
					SliderFrame.ClipsDescendants = true

					local SliderFrameConner = Instance.new("UICorner")

					SliderFrameConner.CornerRadius = UDim.new(0, 4)
					SliderFrameConner.Name = ""
					SliderFrameConner.Parent = SliderFrame

					local SliderFrameStroke = Instance.new("UIStroke")

					SliderFrameStroke.Thickness = 1
					SliderFrameStroke.Name = ""
					SliderFrameStroke.Parent = SliderFrame
					SliderFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
					SliderFrameStroke.Color = _G.ColorMethod
					SliderFrameStroke.Transparency = 0.7



					SliderFrame.MouseEnter:Connect(function()
						TweenService:Create(
							SliderFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					SliderFrame.MouseLeave:Connect(function()
						TweenService:Create(
							SliderFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0.7} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					local LabelNameSliderxd = Instance.new("TextLabel")

					LabelNameSliderxd.Parent = SliderFrame
					LabelNameSliderxd.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					LabelNameSliderxd.BackgroundTransparency = 1
					LabelNameSliderxd.BorderSizePixel = 0
					LabelNameSliderxd.Position = UDim2.new(0.35, 0, 0.2, 0)
					LabelNameSliderxd.AnchorPoint = Vector2.new(0.5, 0.5)
					LabelNameSliderxd.Size = UDim2.new(0, 120, 0, 20)
					LabelNameSliderxd.Font = Enum.Font.GothamBold
					LabelNameSliderxd.Text = tostring(text)
					LabelNameSliderxd.TextColor3 = Color3.fromRGB(255, 255, 255)
					LabelNameSliderxd.TextSize = 11.000
					LabelNameSliderxd.TextXAlignment = Enum.TextXAlignment.Left


					local ShowValueFarm = Instance.new("Frame")

					ShowValueFarm.Name = "ShowValueFarm"
					ShowValueFarm.Parent = SliderFrame
					ShowValueFarm.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
					ShowValueFarm.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					ShowValueFarm.Size = UDim2.new(0, 75, 0, 15)
					ShowValueFarm.BackgroundTransparency = 0
					ShowValueFarm.BorderSizePixel = 0
					ShowValueFarm.AnchorPoint = Vector2.new(0.5, 0.5)
					ShowValueFarm.Position = UDim2.new(0.8, 0, 0.2, 0)
					ShowValueFarm.ClipsDescendants = false

					local CustomValue = Instance.new("TextBox")

					CustomValue.Parent = ShowValueFarm
					CustomValue.BackgroundColor3 = Color3.fromRGB(45,45, 45)
					CustomValue.BorderSizePixel = 0
					CustomValue.ClipsDescendants = true
					CustomValue.AnchorPoint = Vector2.new(0.5, 0.5)
					CustomValue.Position = UDim2.new(0.5, 0, 0.5, 0)
					CustomValue.Size = UDim2.new(0, 158, 0, 26)
					CustomValue.Font = Enum.Font.GothamSemibold
					CustomValue.PlaceholderColor3 = Color3.fromRGB(222, 222, 222)
					CustomValue.PlaceholderText =  ""
					if floor == true then
						CustomValue.Text =  tostring(de and string.format("%.1f",(de / max) * (max - min) + min) or 0)
					else
						CustomValue.Text =  tostring(de and math.floor( (de / max) * (max - min) + min) or 0)
					end
					CustomValue.TextColor3 = Color3.fromRGB(255, 255, 255)
					CustomValue.TextSize = 8.000
					CustomValue.BackgroundTransparency = 1

					local ValueFrame = Instance.new("Frame")

					ValueFrame.Name = "ValueFrame"
					ValueFrame.Parent = SliderFrame
					ValueFrame.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
					ValueFrame.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					ValueFrame.Size = UDim2.new(0, 190, 0, 5)
					ValueFrame.BackgroundTransparency = 0
					ValueFrame.BorderSizePixel = 0
					ValueFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					ValueFrame.Position = UDim2.new(0.5, 0, 0.8, 0)
					ValueFrame.ClipsDescendants = false


					local PartValue = Instance.new("Frame")

					PartValue.Name = "PartValue"
					PartValue.Parent = ValueFrame
					PartValue.BackgroundColor3 = Color3.fromRGB(222, 222, 222)
					PartValue.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
					PartValue.Size = UDim2.new(0, 190, 0, 5)
					PartValue.BackgroundTransparency = 1
					PartValue.BorderSizePixel = 0
					PartValue.AnchorPoint = Vector2.new(0.5, 0.5)
					PartValue.Position = UDim2.new(0.5, 0, 0.5, 0)
					PartValue.ClipsDescendants = false

					local MainValue = Instance.new("Frame")

					MainValue.Name = "MainValue"
					MainValue.Parent = PartValue
					MainValue.BackgroundColor3 = _G.ColorMethod
					MainValue.Size = UDim2.new((de or 0) / max, 0, 0, 5)
					MainValue.BackgroundTransparency = 0
					MainValue.BorderSizePixel = 0
					-- MainValue.AnchorPoint = Vector2.new(0.5, 0.5)
					MainValue.Position = UDim2.new(0., 0, 0.0, 0)
					MainValue.ClipsDescendants = false

					local Conner_S1 = Instance.new("UICorner")

					Conner_S1.CornerRadius = UDim.new(0, 8)
					Conner_S1.Name = ""
					Conner_S1.Parent = MainValue

					local Conner_S2 = Instance.new("UICorner")

					Conner_S2.CornerRadius = UDim.new(0, 8)
					Conner_S2.Name = ""
					Conner_S2.Parent = ValueFrame

					local ConneValue = Instance.new("Frame")

					ConneValue.Name = "ConneValue"
					ConneValue.Parent = PartValue
					ConneValue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					ConneValue.Size = UDim2.new(0, 13, 0,13)
					ConneValue.BackgroundTransparency = 0
					ConneValue.BorderSizePixel = 0
					ConneValue.AnchorPoint = Vector2.new(0.5, 0.5)
					ConneValue.Position = UDim2.new((de or 0)/max, 0.5, 0.3,0.5, 0)
					ConneValue.ClipsDescendants = false


					local Conner_Conne = Instance.new("UICorner")

					Conner_Conne.CornerRadius = UDim.new(0, 300)
					Conner_Conne.Name = ""
					Conner_Conne.Parent = ConneValue

					local Addvalue = Instance.new("ImageButton")

					Addvalue.Name = "Imatog"
					Addvalue.Parent = SliderFrame
					Addvalue.BackgroundTransparency = 1.000
					Addvalue.BorderSizePixel = 0
					Addvalue.Position = UDim2.new(0.85, 0, 0.35, 0)
					Addvalue.Size = UDim2.new(0, 15, 0, 15)
					Addvalue.Image = "http://www.roblox.com/asset/?id=6035067836"
					Addvalue.ImageColor3 =  _G.ColorMethod

					local Deletevalue = Instance.new("ImageButton")

					Deletevalue.Name = "Imatog"
					Deletevalue.Parent = SliderFrame
					Deletevalue.BackgroundTransparency = 1.000
					Deletevalue.BorderSizePixel = 0
					Deletevalue.Position = UDim2.new(0.7, 0, 0.35, 0)
					Deletevalue.Size = UDim2.new(0, 15, 0, 15)
					Deletevalue.Image = "http://www.roblox.com/asset/?id=6035047377"
					Deletevalue.ImageColor3 =  _G.ColorMethod

					local function move(input)
						local pos =
							UDim2.new(
								math.clamp((input.Position.X - ValueFrame.AbsolutePosition.X) / ValueFrame.AbsoluteSize.X, 0, 1),
								0,
								0.3,
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
							local value = string.format("%.1f",((pos.X.Scale * max) / max) * (max - min) + min)
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
						end
					)
					ConneValue.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)
					SliderFrame.InputBegan:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = true

							end
						end
					)
					SliderFrame.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)


					ValueFrame.InputBegan:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = true

							end
						end
					)
					ValueFrame.InputEnded:Connect(
						function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								dragging = false

							end
						end
					)

					game:GetService("UserInputService").InputChanged:Connect(
					function(input)
						if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
							move(input)
						end
					end
					)

					CustomValue.FocusLost:Connect(function()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text or 0) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						pcall(callback, CustomValue.Text)
					end)


					Addvalue.MouseButton1Click:Connect(function ()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						CustomValue.Text  = CustomValue.Text  - tonumber(lol)
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						if  tonumber(CustomValue.Text) < min then
							CustomValue.Text  = min
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text  or 0  ) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0.5, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						pcall(callback, CustomValue.Text)
					end)

					Deletevalue.MouseButton1Click:Connect(function ()
						if CustomValue.Text == "" then
							CustomValue.Text  = de
						end
						CustomValue.Text  = CustomValue.Text  + tonumber(lol)
						if  tonumber(CustomValue.Text) > max then
							CustomValue.Text  = max
						end
						if  tonumber(CustomValue.Text) < min then
							CustomValue.Text  = min
						end
						MainValue:TweenSize(UDim2.new((CustomValue.Text  or 0  ) / max, 0, 0, 5), "Out", "Sine", 0.2, true)
						ConneValue:TweenPosition(UDim2.new((CustomValue.Text or 0)/max, 0,0.5, 0) , "Out", "Sine", 0.2, true)
						if floor == true then
							CustomValue.Text = tostring(CustomValue.Text and string.format("%.1f",(CustomValue.Text / max) * (max - min) + min) )
						else
							CustomValue.Text = tostring(CustomValue.Text and math.floor( (CustomValue.Text / max) * (max - min) + min) )
						end
						pcall(callback, CustomValue.Text)
					end)

				end

			end

			function items:Drop(text,use,option,callback)

				if use == false then
					local DropFrame = Instance.new("Frame")

					DropFrame.Name = "DropFrame"
					DropFrame.Parent = ScrollingFrame_Pageframe
					DropFrame.BackgroundColor3 =  Color3.fromRGB(23, 23, 23)-- _G.ColorMethod
					DropFrame.BorderSizePixel = 0
					DropFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
					DropFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					DropFrame.Size = UDim2.new(0, 213, 0, 30) -- UDim2.new(0, 213, 0, 35)
					DropFrame.BackgroundTransparency  = 0
					DropFrame.ClipsDescendants = true

					local ConnerDropFrame = Instance.new("UICorner")

					ConnerDropFrame.CornerRadius = UDim.new(0, 4)
					ConnerDropFrame.Name = ""
					ConnerDropFrame.Parent = DropFrame

					local DropFrameStroke = Instance.new("UIStroke")

					DropFrameStroke.Thickness = 1
					DropFrameStroke.Name = ""
					DropFrameStroke.Parent = DropFrame
					DropFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
					DropFrameStroke.Color = _G.ColorMethod
					DropFrameStroke.Transparency = 0.7





					local LabelFrameDrop = Instance.new("TextLabel")

					LabelFrameDrop.Parent = DropFrame
					LabelFrameDrop.Name = "LabelFrameDrop"
					LabelFrameDrop.BackgroundColor3 = _G.ColorMethod
					LabelFrameDrop.Position = UDim2.new(0., 0, 0., 0)
					LabelFrameDrop.Size =    UDim2.new(0, 213, 0, 30)
					LabelFrameDrop.Font = Enum.Font.SourceSansSemibold
					LabelFrameDrop.Text = ""
					LabelFrameDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					LabelFrameDrop.TextSize = 14.000
					--   LabelFrameDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					LabelFrameDrop.BackgroundTransparency = 1
					LabelFrameDrop.TextXAlignment = Enum.TextXAlignment.Left


					local TextLabel_TapDrop = Instance.new("TextLabel")

					TextLabel_TapDrop.Parent = LabelFrameDrop
					TextLabel_TapDrop.Name = "TextLabel_TapDrop"
					TextLabel_TapDrop.BackgroundColor3 = _G.ColorMethod
					TextLabel_TapDrop.Position = UDim2.new(0.04, 0, 0.14, 0)
					TextLabel_TapDrop.Size =    UDim2.new(0, 140, 0, 20)
					TextLabel_TapDrop.Font = Enum.Font.SourceSansSemibold
					TextLabel_TapDrop.Text = tostring(text).." :"
					TextLabel_TapDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					TextLabel_TapDrop.TextSize = 14.000
					--     TextLabel_TapDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					TextLabel_TapDrop.BackgroundTransparency = 1
					TextLabel_TapDrop.TextXAlignment = Enum.TextXAlignment.Left


					local DropArbt_listimage = Instance.new("ImageButton")

					DropArbt_listimage.Parent = LabelFrameDrop
					DropArbt_listimage.BackgroundTransparency = 1.000
					DropArbt_listimage.AnchorPoint = Vector2.new(0.5, 0.5)
					DropArbt_listimage.Position = UDim2.new(0.9, 0, 0.5, 0)
					DropArbt_listimage.BorderSizePixel = 0
					DropArbt_listimage.Size = UDim2.new(0, 25, 0, 25)
					DropArbt_listimage.Image = "http://www.roblox.com/asset/?id=6031091004"
					DropArbt_listimage.ImageColor3 = Color3.fromRGB(155, 155, 155)

					local ScolDown = Instance.new("ScrollingFrame")

					ScolDown.Name = "ScolDown"
					ScolDown.Position = UDim2.new(0.02, 0, 1., 0)
					ScolDown.Parent = LabelFrameDrop
					ScolDown.Active = true
					ScolDown.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					ScolDown.BorderSizePixel = 0
					ScolDown.Size = UDim2.new(0, 205, 0, 115)
					ScolDown.ScrollBarThickness = 3
					ScolDown.ClipsDescendants = true
					ScolDown.BackgroundTransparency = 1
					ScolDown.CanvasSize = UDim2.new(0, 0, 0, 2)

					local UIListLayoutlist = Instance.new("UIListLayout")
					local UIPaddinglist = Instance.new("UIPadding")

					UIListLayoutlist.Name = "UIListLayoutlist"
					UIListLayoutlist.Parent = ScolDown
					UIListLayoutlist.SortOrder = Enum.SortOrder.LayoutOrder
					UIListLayoutlist.Padding = UDim.new(0, 5)

					UIPaddinglist.Name = "UIPaddinglist"
					UIPaddinglist.Parent = ScolDown
					UIPaddinglist.PaddingTop = UDim.new(0, 5)
					UIPaddinglist.PaddingLeft = UDim.new(0, 12)

					local ButtonDrop = Instance.new("TextButton")

					ButtonDrop.Parent = DropFrame
					ButtonDrop.Name = "ButtonDrop"
					ButtonDrop.BackgroundColor3 = _G.ColorMethod
					ButtonDrop.Size = UDim2.new(0, 213, 0, 30)
					ButtonDrop.Font = Enum.Font.SourceSansSemibold
					ButtonDrop.Text = ""
					ButtonDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					ButtonDrop.TextSize = 13.000
					--   ButtonDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					ButtonDrop.Position = UDim2.new(0., 0, 0., 0)
					ButtonDrop.TextXAlignment = Enum.TextXAlignment.Center
					ButtonDrop.BackgroundTransparency = 1
					ButtonDrop.TextWrapped = true
					ButtonDrop.AutoButtonColor = false
					ButtonDrop.ClipsDescendants = true

					local dog = false

					local FrameSize = 75
					local cout = 0
					for i , v in pairs(option) do
						cout =cout + 1
						if cout == 1 then
							FrameSize = 75
						elseif cout == 2 then
							FrameSize = 110
						elseif cout >= 3 then
							FrameSize = 150
						end

						local ListFrame = Instance.new("Frame")

						ListFrame.Name = "ListFrame"
						ListFrame.Parent = ScolDown
						ListFrame.BackgroundColor3 =  Color3.fromRGB(22553, 23, 23)-- _G.ColorMethod
						ListFrame.BorderSizePixel = 0
						ListFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
						ListFrame.AnchorPoint = Vector2.new(0.5, 0.5)
						ListFrame.Size = UDim2.new(0, 180, 0, 30) -- UDim2.new(0, 213, 0, 35)
						ListFrame.BackgroundTransparency  = 1
						ListFrame.ClipsDescendants = true

						local TextLabel_TapDro2p = Instance.new("TextLabel")

						TextLabel_TapDro2p.Parent = ListFrame
						TextLabel_TapDro2p.Name =  tostring(v).."Dropdown"
						TextLabel_TapDro2p.BackgroundColor3 = _G.ColorMethod
						TextLabel_TapDro2p.Position = UDim2.new(0.5, 0, 0.5, 0)
						TextLabel_TapDro2p.Size =  UDim2.new(0, 180, 0, 30)
						TextLabel_TapDro2p.Font = Enum.Font.SourceSansSemibold
						TextLabel_TapDro2p.Text = tostring(v)
						TextLabel_TapDro2p.TextColor3 = Color3.fromRGB(155, 155, 155)
						TextLabel_TapDro2p.TextSize = 14.000
						TextLabel_TapDro2p.AnchorPoint = Vector2.new(0.5, 0.5)
						TextLabel_TapDro2p.BackgroundTransparency = 1
						TextLabel_TapDro2p.TextXAlignment = Enum.TextXAlignment.Center

						local ButtonDrop2 = Instance.new("TextButton")

						ButtonDrop2.Parent = ListFrame
						ButtonDrop2.Name = "ButtonDrop2"
						ButtonDrop2.BackgroundColor3 = _G.ColorMethod
						ButtonDrop2.Size = UDim2.new(0, 213, 0, 30)
						ButtonDrop2.Font = Enum.Font.SourceSansSemibold
						ButtonDrop2.Text = ""
						ButtonDrop2.TextColor3 = Color3.fromRGB(155, 155, 155)
						ButtonDrop2.TextSize = 13.000
						--   ButtonDrop2.AnchorPoint = Vector2.new(0.5, 0.5)
						ButtonDrop2.Position = UDim2.new(0., 0, 0., 0)
						ButtonDrop2.TextXAlignment = Enum.TextXAlignment.Center
						ButtonDrop2.BackgroundTransparency = 1
						ButtonDrop2.TextWrapped = true
						ButtonDrop2.AutoButtonColor = false
						ButtonDrop2.ClipsDescendants = true

						ButtonDrop2.MouseEnter:Connect(function ()
							TweenService:Create(
								TextLabel_TapDro2p,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
							):Play()
						end)

						ButtonDrop2.MouseLeave:Connect(function ()
							TweenService:Create(
								TextLabel_TapDro2p,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
							):Play()
						end)

						ButtonDrop2.MouseButton1Click:Connect(function()
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, 30)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = 0}
							):Play()
							TextLabel_TapDrop.Text =  text.." : "..tostring(v)
							callback(v)
							dog = not dog
						end
						)


						ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
					end


					DropFrame.MouseEnter:Connect(function()
						TweenService:Create(
							DropFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextLabel_TapDrop,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							DropArbt_listimage,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					DropFrame.MouseLeave:Connect(function()
						TweenService:Create(
							DropFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0.7} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextLabel_TapDrop,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							DropArbt_listimage,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)


					ButtonDrop.MouseButton1Click:Connect(function()
						if dog == false then
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, FrameSize)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = -180}
							):Play()
							ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
						else
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, 30)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = 0}
							):Play()
							ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
						end
						dog = not dog
					end
					)
					ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )

					local dropfunc = {}

					function dropfunc:Clear()
						TextLabel_TapDrop.Text = tostring(text).." :"
						for i, v in next, ScolDown:GetChildren() do
							if v:IsA("Frame") then
								v:Destroy()
							end
						end
						ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
					end

					function dropfunc:Add(t)
						local ListFrame = Instance.new("Frame")

						ListFrame.Name = "ListFrame"
						ListFrame.Parent = ScolDown
						ListFrame.BackgroundColor3 =  Color3.fromRGB(22553, 23, 23)-- _G.ColorMethod
						ListFrame.BorderSizePixel = 0
						ListFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
						ListFrame.AnchorPoint = Vector2.new(0.5, 0.5)
						ListFrame.Size = UDim2.new(0, 180, 0, 30) -- UDim2.new(0, 213, 0, 35)
						ListFrame.BackgroundTransparency  = 1
						ListFrame.ClipsDescendants = true

						local TextLabel_TapDro2p = Instance.new("TextLabel")

						TextLabel_TapDro2p.Parent = ListFrame
						TextLabel_TapDro2p.Name =  tostring(t).."Dropdown"
						TextLabel_TapDro2p.BackgroundColor3 = _G.ColorMethod
						TextLabel_TapDro2p.Position = UDim2.new(0.5, 0, 0.5, 0)
						TextLabel_TapDro2p.Size =  UDim2.new(0, 180, 0, 30)
						TextLabel_TapDro2p.Font = Enum.Font.SourceSansSemibold
						TextLabel_TapDro2p.Text = tostring(t)
						TextLabel_TapDro2p.TextColor3 = Color3.fromRGB(155, 155, 155)
						TextLabel_TapDro2p.TextSize = 14.000
						TextLabel_TapDro2p.AnchorPoint = Vector2.new(0.5, 0.5)
						TextLabel_TapDro2p.BackgroundTransparency = 1
						TextLabel_TapDro2p.TextXAlignment = Enum.TextXAlignment.Center

						local ButtonDrop2 = Instance.new("TextButton")

						ButtonDrop2.Parent = ListFrame
						ButtonDrop2.Name = "ButtonDrop2"
						ButtonDrop2.BackgroundColor3 = _G.ColorMethod
						ButtonDrop2.Size = UDim2.new(0, 213, 0, 30)
						ButtonDrop2.Font = Enum.Font.SourceSansSemibold
						ButtonDrop2.Text = ""
						ButtonDrop2.TextColor3 = Color3.fromRGB(155, 155, 155)
						ButtonDrop2.TextSize = 13.000
						--   ButtonDrop2.AnchorPoint = Vector2.new(0.5, 0.5)
						ButtonDrop2.Position = UDim2.new(0., 0, 0., 0)
						ButtonDrop2.TextXAlignment = Enum.TextXAlignment.Center
						ButtonDrop2.BackgroundTransparency = 1
						ButtonDrop2.TextWrapped = true
						ButtonDrop2.AutoButtonColor = false
						ButtonDrop2.ClipsDescendants = true

						ButtonDrop2.MouseEnter:Connect(function ()
							TweenService:Create(
								TextLabel_TapDro2p,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
							):Play()
						end)

						ButtonDrop2.MouseLeave:Connect(function ()
							TweenService:Create(
								TextLabel_TapDro2p,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
							):Play()
						end)

						ButtonDrop2.MouseButton1Click:Connect(function()
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, 30)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = 0}
							):Play()
							TextLabel_TapDrop.Text =  text.." : "..tostring(t)
							callback(t)
							dog = not dog
						end
						)

						ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
					end
					return dropfunc

				else

					local location = option.location or self.flags
					local flag = not use and option.flag or ""
					local callback = callback or function() end
					local list = option.list or {}
					local default = list.default or list[1].Name

					if not use then
						location[flag] = default
					end


					local DropFrame = Instance.new("Frame")

					DropFrame.Name = "DropFrame"
					DropFrame.Parent = ScrollingFrame_Pageframe
					DropFrame.BackgroundColor3 =  Color3.fromRGB(23, 23, 23)-- _G.ColorMethod
					DropFrame.BorderSizePixel = 0
					DropFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
					DropFrame.AnchorPoint = Vector2.new(0.5, 0.5)
					DropFrame.Size = UDim2.new(0, 213, 0, 30) -- UDim2.new(0, 213, 0, 35)
					DropFrame.BackgroundTransparency  = 0
					DropFrame.ClipsDescendants = true

					local ConnerDropFrame = Instance.new("UICorner")

					ConnerDropFrame.CornerRadius = UDim.new(0, 4)
					ConnerDropFrame.Name = ""
					ConnerDropFrame.Parent = DropFrame

					local DropFrameStroke = Instance.new("UIStroke")

					DropFrameStroke.Thickness = 1
					DropFrameStroke.Name = ""
					DropFrameStroke.Parent = DropFrame
					DropFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
					DropFrameStroke.Color = _G.ColorMethod
					DropFrameStroke.Transparency = 0.7





					local LabelFrameDrop = Instance.new("TextLabel")

					LabelFrameDrop.Parent = DropFrame
					LabelFrameDrop.Name = "LabelFrameDrop"
					LabelFrameDrop.BackgroundColor3 = _G.ColorMethod
					LabelFrameDrop.Position = UDim2.new(0., 0, 0., 0)
					LabelFrameDrop.Size =    UDim2.new(0, 213, 0, 30)
					LabelFrameDrop.Font = Enum.Font.SourceSansSemibold
					LabelFrameDrop.Text = ""
					LabelFrameDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					LabelFrameDrop.TextSize = 14.000
					--   LabelFrameDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					LabelFrameDrop.BackgroundTransparency = 1
					LabelFrameDrop.TextXAlignment = Enum.TextXAlignment.Left


					local TextLabel_TapDrop = Instance.new("TextLabel")

					TextLabel_TapDrop.Parent = LabelFrameDrop
					TextLabel_TapDrop.Name = "TextLabel_TapDrop"
					TextLabel_TapDrop.BackgroundColor3 = _G.ColorMethod
					TextLabel_TapDrop.Position = UDim2.new(0.04, 0, 0.14, 0)
					TextLabel_TapDrop.Size =    UDim2.new(0, 140, 0, 20)
					TextLabel_TapDrop.Font = Enum.Font.SourceSansSemibold
					TextLabel_TapDrop.Text = tostring(text).." :"
					TextLabel_TapDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					TextLabel_TapDrop.TextSize = 14.000
					--     TextLabel_TapDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					TextLabel_TapDrop.BackgroundTransparency = 1
					TextLabel_TapDrop.TextXAlignment = Enum.TextXAlignment.Left


					local DropArbt_listimage = Instance.new("ImageButton")

					DropArbt_listimage.Parent = LabelFrameDrop
					DropArbt_listimage.BackgroundTransparency = 1.000
					DropArbt_listimage.AnchorPoint = Vector2.new(0.5, 0.5)
					DropArbt_listimage.Position = UDim2.new(0.9, 0, 0.5, 0)
					DropArbt_listimage.BorderSizePixel = 0
					DropArbt_listimage.Size = UDim2.new(0, 25, 0, 25)
					DropArbt_listimage.Image = "http://www.roblox.com/asset/?id=6031091004"
					DropArbt_listimage.ImageColor3 = Color3.fromRGB(155, 155, 155)

					local ScolDown = Instance.new("ScrollingFrame")

					ScolDown.Name = "ScolDown"
					ScolDown.Position = UDim2.new(0.02, 0, 1., 0)
					ScolDown.Parent = LabelFrameDrop
					ScolDown.Active = true
					ScolDown.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					ScolDown.BorderSizePixel = 0
					ScolDown.Size = UDim2.new(0, 205, 0, 115)
					ScolDown.ScrollBarThickness = 3
					ScolDown.ClipsDescendants = true
					ScolDown.BackgroundTransparency = 1
					ScolDown.CanvasSize = UDim2.new(0, 0, 0, 2)

					local UIListLayoutlist = Instance.new("UIListLayout")
					local UIPaddinglist = Instance.new("UIPadding")

					UIListLayoutlist.Name = "UIListLayoutlist"
					UIListLayoutlist.Parent = ScolDown
					UIListLayoutlist.SortOrder = Enum.SortOrder.LayoutOrder
					UIListLayoutlist.Padding = UDim.new(0, 5)

					UIPaddinglist.Name = "UIPaddinglist"
					UIPaddinglist.Parent = ScolDown
					UIPaddinglist.PaddingTop = UDim.new(0, 5)
					UIPaddinglist.PaddingLeft = UDim.new(0, 12)

					local ButtonDrop = Instance.new("TextButton")

					ButtonDrop.Parent = DropFrame
					ButtonDrop.Name = "ButtonDrop"
					ButtonDrop.BackgroundColor3 = _G.ColorMethod
					ButtonDrop.Size = UDim2.new(0, 213, 0, 30)
					ButtonDrop.Font = Enum.Font.SourceSansSemibold
					ButtonDrop.Text = ""
					ButtonDrop.TextColor3 = Color3.fromRGB(155, 155, 155)
					ButtonDrop.TextSize = 13.000
					--   ButtonDrop.AnchorPoint = Vector2.new(0.5, 0.5)
					ButtonDrop.Position = UDim2.new(0., 0, 0., 0)
					ButtonDrop.TextXAlignment = Enum.TextXAlignment.Center
					ButtonDrop.BackgroundTransparency = 1
					ButtonDrop.TextWrapped = true
					ButtonDrop.AutoButtonColor = false
					ButtonDrop.ClipsDescendants = true

					local dog = false

					local FrameSize = 75
					local cout = 0
					for i , v in pairs(list) do
						cout =cout + 1
						if cout == 1 then
							FrameSize = 75
						elseif cout == 2 then
							FrameSize = 110
						elseif cout >= 3 then
							FrameSize = 150
						end

						local listtog = Instance.new("Frame")

						listtog.Name = "listtog"
						listtog.Parent = ScolDown
						listtog.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
						listtog.BackgroundTransparency =1
						listtog.BorderSizePixel = 0
						listtog.ClipsDescendants = true
						listtog.AnchorPoint = Vector2.new(0.5, 0.5)
						listtog.Position = UDim2.new(0.5, 0, 0.5, 0)
						listtog.Size = UDim2.new(0, 210, 0, 33)


						local listtextbutton = Instance.new("TextButton")

						listtextbutton.Parent = listtog
						listtextbutton.BackgroundTransparency =1
						listtextbutton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
						listtextbutton.BorderSizePixel = 0
						listtextbutton.Size =  UDim2.new(0, 210, 0, 33)
						listtextbutton.AutoButtonColor = false
						listtextbutton.Font = Enum.Font.SourceSans
						listtextbutton.Text = " "
						listtextbutton.TextColor3 = Color3.fromRGB(0, 0, 0)
						listtextbutton.TextSize = 14.000

						local farmtoglist = Instance.new("TextButton")

						farmtoglist.Parent = listtextbutton
						farmtoglist.BackgroundColor3 = _G.ColorMethod
						farmtoglist.BorderColor3 = _G.ColorMethod
						farmtoglist.BorderSizePixel = 0
						farmtoglist.AnchorPoint = Vector2.new(0.5, 0.5)
						farmtoglist.Position = UDim2.new(0.1, 0, 0.5, 0)
						farmtoglist.Size = UDim2.new(0, 23, 0, 23)
						farmtoglist.Font = Enum.Font.SourceSans
						farmtoglist.Text = " "
						farmtoglist.TextColor3 = Color3.fromRGB(0, 0, 0)
						farmtoglist.TextSize = 14.000
						farmtoglist.AutoButtonColor = false


						local farmtoglist2 = Instance.new("TextButton")

						farmtoglist2.Parent = farmtoglist
						farmtoglist2.BackgroundColor3 = Color3.fromRGB(32, 32,32)
						farmtoglist2.BorderColor3 = _G.ColorMethod
						farmtoglist2.BorderSizePixel = 0
						farmtoglist2.AnchorPoint = Vector2.new(0.5, 0.5)
						farmtoglist2.Position = UDim2.new(0.5, 0, 0.5, 0)
						farmtoglist2.Size = UDim2.new(0, 21, 0, 21)
						farmtoglist2.Font = Enum.Font.SourceSans
						farmtoglist2.Text = " "
						farmtoglist2.TextColor3 = Color3.fromRGB(0, 0, 0)
						farmtoglist2.TextSize = 14.000
						farmtoglist2.AutoButtonColor = false


						local listimage = Instance.new("ImageButton")

						listimage.Parent = farmtoglist2
						listimage.BackgroundTransparency = 1.000
						listimage.AnchorPoint = Vector2.new(0.5, 0.5)
						listimage.Position = UDim2.new(0.5, 0, 0.5, 0)
						listimage.BorderSizePixel = 0
						listimage.Size = UDim2.new(0, 0, 0, 0)
						listimage.Image = "http://www.roblox.com/asset/?id=5880482965"


						local textlist = Instance.new("TextLabel")


						textlist.Parent = listtextbutton
						textlist.Name = "textlist"
						textlist.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
						textlist.BackgroundTransparency = 1.000
						textlist.AnchorPoint = Vector2.new(0.5, 0.5)
						textlist.Position = UDim2.new(0.5, 0, 0.5, 0)
						textlist.BorderSizePixel = 0
						textlist.Size = UDim2.new(0, 91, 0, 25)
						textlist.Font = Enum.Font.GothamSemibold
						textlist.Text = tostring(v.Name)
						textlist.TextColor3 = Color3.fromRGB(255, 255, 255)
						textlist.TextSize = 13.000



						local TextButton_Pageframe_Uiconner2 = Instance.new("UICorner")

						TextButton_Pageframe_Uiconner2.CornerRadius = UDim.new(0, 5)
						TextButton_Pageframe_Uiconner2.Name = ""
						TextButton_Pageframe_Uiconner2.Parent = farmtoglist

						local TextButton_Pageframe_Uiconner22 = Instance.new("UICorner")

						TextButton_Pageframe_Uiconner22.CornerRadius = UDim.new(0, 5)
						TextButton_Pageframe_Uiconner22.Name = ""
						TextButton_Pageframe_Uiconner22.Parent = farmtoglist2



						listtextbutton.MouseButton1Click:Connect(function()
							if not  location[v.flag] then
								listimage:TweenSizeAndPosition(UDim2.new(0, 30, 0, 30), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)
								wait(0.1)
								listimage:TweenSizeAndPosition(UDim2.new(0, 23, 0, 23), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)
							else
								listimage:TweenSizeAndPosition(UDim2.new(0, 30, 0, 30), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)
								wait(0.1)
								listimage:TweenSizeAndPosition(UDim2.new(0, 0, 0, 0), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)
							end
							location[v.flag] = not location[v.flag]
							callback(location[v.flag])
						end
						)

						if  location[v.flag] then
							listimage:TweenSizeAndPosition(UDim2.new(0, 30, 0, 30), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)
							wait(0.1)
							listimage:TweenSizeAndPosition(UDim2.new(0, 23, 0, 23), UDim2.new(0.5, 0, 0.5, 0), "In", "Bounce", 0.1, true)

							callback(location[v.flag])
						end

						ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
					end


					DropFrame.MouseEnter:Connect(function()
						TweenService:Create(
							DropFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextLabel_TapDrop,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							DropArbt_listimage,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)

					DropFrame.MouseLeave:Connect(function()
						TweenService:Create(
							DropFrameStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Transparency = 0.7} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextLabel_TapDrop,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							DropArbt_listimage,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{ImageColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
					end
					)


					ButtonDrop.MouseButton1Click:Connect(function()
						if dog == false then
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, FrameSize)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = -180}
							):Play()
							ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
						else
							TweenService:Create(
								DropFrame,
								TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, 213, 0, 30)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							TweenService:Create(
								DropArbt_listimage,
								TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
								{Rotation = 0}
							):Play()
							ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )
						end
						dog = not dog
					end
					)
					ScolDown.CanvasSize = UDim2.new(0,0,0,UIListLayoutlist.AbsoluteContentSize.Y + 10  )



				end



			end

			function items:AddTextbox(text,text2,callback)
				local TextFrame = Instance.new("Frame")

				TextFrame.Name = "TextFrame"
				TextFrame.Parent = ScrollingFrame_Pageframe
				TextFrame.BackgroundColor3 =  Color3.fromRGB(23, 23, 23)
				TextFrame.BorderSizePixel = 0
				TextFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
				TextFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				TextFrame.Size = UDim2.new(0, 213, 0, 70)
				TextFrame.BackgroundTransparency  = 1
				TextFrame.ClipsDescendants = true

				local LabelNameSliderxd = Instance.new("TextLabel")

				LabelNameSliderxd.Parent = TextFrame
				LabelNameSliderxd.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelNameSliderxd.BackgroundTransparency = 1
				LabelNameSliderxd.BorderSizePixel = 0
				LabelNameSliderxd.Position = UDim2.new(0.5, 0, 0.2, 0)
				LabelNameSliderxd.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelNameSliderxd.Size = UDim2.new(0, 160, 0, 20)
				LabelNameSliderxd.Font = Enum.Font.GothamBold
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
				FrameBox.BackgroundColor3 =  Color3.fromRGB(23, 23, 23)
				FrameBox.BorderSizePixel = 0
				FrameBox.Position = UDim2.new(0.5, 0, 0.65, 0)
				FrameBox.AnchorPoint = Vector2.new(0.5, 0.5)
				FrameBox.Size = UDim2.new(0, 158, 0, 30)
				FrameBox.BackgroundTransparency  = 0.2
				FrameBox.ClipsDescendants = true
				FrameBox.AnchorPoint = Vector2.new(0.5, 0.5)

				local TextFrame2 = Instance.new("TextBox")

				TextFrame2.Parent = FrameBox
				TextFrame2.BackgroundColor3 = _G.ColorMethod
				TextFrame2.BorderSizePixel = 0
				TextFrame2.ClipsDescendants = true
				TextFrame2.Position = UDim2.new(0.5, 0, 0.5, 0)
				TextFrame2.AnchorPoint = Vector2.new(0.5, 0.5)
				TextFrame2.Size = UDim2.new(0, 158, 0, 35)
				TextFrame2.Font = Enum.Font.GothamSemibold
				TextFrame2.PlaceholderColor3 = Color3.fromRGB(155, 155, 155)
				TextFrame2.PlaceholderText = text2
				TextFrame2.Text = ""
				TextFrame2.TextColor3 = Color3.fromRGB(155, 155, 155)
				TextFrame2.TextSize = 12.000
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
				TextBoxStroke.Color = _G.ColorMethod
				TextBoxStroke.Transparency = 0.7


				TextFrame.MouseEnter:Connect(function()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 213, 0, 30)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						FrameBox,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
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

			function items:Bind(text,bi,callback)
				local BindFrame = Instance.new("Frame")

				BindFrame.Name = "BindFrame"
				BindFrame.Parent = ScrollingFrame_Pageframe
				BindFrame.BackgroundColor3 =  Color3.fromRGB(23, 23, 23)
				BindFrame.BorderSizePixel = 0
				BindFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
				BindFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				BindFrame.Size = UDim2.new(0, 213, 0, 35)
				BindFrame.BackgroundTransparency  = 0
				BindFrame.ClipsDescendants = true

				local BindConner = Instance.new("UICorner")

				BindConner.CornerRadius = UDim.new(0, 4)
				BindConner.Name = ""
				BindConner.Parent = BindFrame

				local BindStroke = Instance.new("UIStroke")

				BindStroke.Thickness = 1
				BindStroke.Name = ""
				BindStroke.Parent = BindFrame
				BindStroke.LineJoinMode = Enum.LineJoinMode.Round
				BindStroke.Color = _G.ColorMethod
				BindStroke.Transparency = 0.7

				local LabelBind = Instance.new("TextLabel")

				LabelBind.Parent = BindFrame
				LabelBind.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelBind.BackgroundTransparency = 1
				LabelBind.BorderSizePixel = 0
				LabelBind.Position = UDim2.new(0.4, 0, 0.5, 0)
				LabelBind.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelBind.Size = UDim2.new(0, 140, 0, 35)
				LabelBind.Font = Enum.Font.GothamBold
				LabelBind.Text = tostring(text)
				LabelBind.TextColor3 = Color3.fromRGB(155, 155, 155)
				LabelBind.TextSize = 11.000
				LabelBind.TextXAlignment = Enum.TextXAlignment.Left

				local key = bi.Name
				local LabelBind2 = Instance.new("TextButton")

				LabelBind2.Parent = BindFrame
				LabelBind2.Name = "LabelBind2"
				LabelBind2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelBind2.Size = UDim2.new(0, 100, 0, 19)
				LabelBind2.Font = Enum.Font.GothamBold
				LabelBind2.Text =  "KEY : "..key
				LabelBind2.TextColor3 = Color3.fromRGB(155, 155, 155)
				LabelBind2.TextSize = 11.000
				LabelBind2.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelBind2.Position = UDim2.new(0.75, 0, 0.5, 0)
				LabelBind2.TextXAlignment = Enum.TextXAlignment.Center
				LabelBind2.BackgroundTransparency = 1
				LabelBind2.TextWrapped = true

				local LabelBind22 = Instance.new("TextButton")

				LabelBind22.Parent = BindFrame
				LabelBind22.Name = "LabelBind22"
				LabelBind22.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelBind22.Size = UDim2.new(0, 213, 0, 35)
				LabelBind22.Font = Enum.Font.GothamBold
				LabelBind22.Text =  ""
				LabelBind22.TextColor3 = Color3.fromRGB(155, 155, 155)
				LabelBind22.TextSize = 11.000
				LabelBind22.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelBind22.Position = UDim2.new(0.5, 0, 0.5, 0)
				LabelBind22.TextXAlignment = Enum.TextXAlignment.Center
				LabelBind22.BackgroundTransparency = 1
				LabelBind22.TextWrapped = true

				BindFrame.MouseEnter:Connect(function()
					TweenService:Create(
						BindStroke,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Transparency = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind22,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)
				BindFrame.MouseLeave:Connect(function()
					TweenService:Create(
						BindStroke,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Transparency = 0.7} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind22,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind2,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						LabelBind,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				LabelBind22.MouseButton1Click:Connect(function ()


					LabelBind2.Text = "KEY : ".."..."
					local inputwait = game:GetService("UserInputService").InputBegan:wait()
					local fuckulop = inputwait.KeyCode == Enum.KeyCode.Unknown and inputwait.UserInputType or inputwait.KeyCode

					if
						fuckulop.Name ~= "Focus" and fuckulop.Name ~= "MouseMovement" and fuckulop.Name ~= "Focus"
					then
						LabelBind2.Text =  "KEY : "..fuckulop.Name
						key = fuckulop.Name
					end
					-- if fuckulop.Name ~= "Unknown" then
					--     LabelBind2.Text = fuckulop.Name
					--     key = fuckulop.Name
					-- end

				end)


				game:GetService("UserInputService").InputBegan:connect(
				function(current)
					local fuckulop2 = current.KeyCode == Enum.KeyCode.Unknown and current.UserInputType or current.KeyCode

					if fuckulop2.Name ==  key then
						pcall(callback)

					end
				end
				)

			end

			function items:AddLine()
				local LineFrame = Instance.new("Frame")

				LineFrame.Name = "LineFrame"
				LineFrame.Parent = ScrollingFrame_Pageframe
				LineFrame.BackgroundColor3 =  _G.ColorMethod
				LineFrame.BorderSizePixel = 0
				LineFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
				LineFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				LineFrame.Size = UDim2.new(0, 213, 0, 1)
				LineFrame.BackgroundTransparency  = 0
				LineFrame.ClipsDescendants = true

				local LineFrame_BindConner = Instance.new("UICorner")

				LineFrame_BindConner.CornerRadius = UDim.new(0, 30)
				LineFrame_BindConner.Name = ""
				LineFrame_BindConner.Parent = LineFrame

			end

			function items:Color(text,preset,callback)
				local Pixker = Instance.new("Frame")

				Pixker.Name = "Pixker"
				Pixker.Parent = ScrollingFrame_Pageframe
				Pixker.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
				Pixker.Position = UDim2.new(0.0833333358, 0, 0.235135213, 0)
				Pixker.Size = UDim2.new(0, 213, 0, 33)
				Pixker.BackgroundTransparency = 0
				Pixker.BorderSizePixel = 0
				Pixker.AnchorPoint = Vector2.new(0.5, 0.5)
				Pixker.Position = UDim2.new(0.5, 0, 0.5, 0)
				Pixker.ClipsDescendants = true


				local BoxColorCorner2 = Instance.new("UICorner")

				BoxColorCorner2.CornerRadius = UDim.new(0, 4)
				BoxColorCorner2.Name = "BoxColorCorner"
				BoxColorCorner2.Parent = Pixker

				local MheeFrameStroke = Instance.new("UIStroke")

				MheeFrameStroke.Thickness = 1
				MheeFrameStroke.Name = ""
				MheeFrameStroke.Parent = Pixker
				MheeFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
				MheeFrameStroke.Color = _G.ColorMethod
				MheeFrameStroke.Transparency = 0.7


				local TextFrameColor = Instance.new("TextLabel")

				TextFrameColor.Parent = Pixker
				TextFrameColor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextFrameColor.BorderSizePixel = 0
				TextFrameColor.Size = UDim2.new(0, 200, 0, 34)
				TextFrameColor.Font = Enum.Font.SourceSans
				TextFrameColor.Text = "  "
				TextFrameColor.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextFrameColor.TextSize = 14.000
				TextFrameColor.BackgroundTransparency = 1
				TextFrameColor.Position = UDim2.new(0., 0, 0., 0)

				local TextReal = Instance.new("TextLabel")

				TextReal.Parent = TextFrameColor
				TextReal.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextReal.BorderSizePixel = 0
				TextReal.Size = UDim2.new(0, 140, 0, 34)
				TextReal.Font = Enum.Font.GothamSemibold
				TextReal.Text = text
				TextReal.TextColor3 = Color3.fromRGB(155,155, 155)
				TextReal.TextSize = 12.000
				TextReal.BackgroundTransparency = 1
				TextReal.Position = UDim2.new(0.05, 0, 0., 0)
				TextReal.TextXAlignment = Enum.TextXAlignment.Left

				local BoxColor = Instance.new("Frame")

				BoxColor.Name = "BoxColor"
				BoxColor.Parent = TextFrameColor
				BoxColor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				BoxColor.Position = UDim2.new(0.85, 0, 0.5, 0)
				BoxColor.Size = UDim2.new(0, 35, 0, 19)
				BoxColor.AnchorPoint = Vector2.new(0.5, 0.5)

				local BoxColorCorner = Instance.new("UICorner")

				BoxColorCorner.CornerRadius = UDim.new(0, 4)
				BoxColorCorner.Name = "BoxColorCorner"
				BoxColorCorner.Parent = BoxColor

				local TextButton_Dropdown = Instance.new("TextButton")


				TextButton_Dropdown.Parent = TextFrameColor
				TextButton_Dropdown.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				TextButton_Dropdown.BorderSizePixel = 0
				TextButton_Dropdown.Position = UDim2.new(0., 0, 0.14705883, 0)
				TextButton_Dropdown.Size = UDim2.new(0, 200, 0, 33)
				TextButton_Dropdown.Font = Enum.Font.SourceSans
				TextButton_Dropdown.Text = "  "
				TextButton_Dropdown.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_Dropdown.TextSize = 14.000
				TextButton_Dropdown.AutoButtonColor = false
				--TextButton_Dropdown.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_Dropdown.Position = UDim2.new(0, 0, 0, 0)
				TextButton_Dropdown.BackgroundTransparency = 1



				Pixker.MouseEnter:Connect(function()
					TweenService:Create(
						MheeFrameStroke,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Transparency = 0.}
					):Play()
					TweenService:Create(
						TextReal,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255,255, 255)}
					):Play()

				end)
				Pixker.MouseLeave:Connect(function()
					TweenService:Create(
						MheeFrameStroke,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Transparency = 0.7}
					):Play()
					TweenService:Create(
						TextReal,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(155,155, 155)}
					):Play()
				end)
				-- Rainbow Toggle


				local TextButton_2_Toggle = Instance.new("TextButton")

				TextButton_2_Toggle.Parent = TextFrameColor
				TextButton_2_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155, 155)
				--        TextButton_2_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_2_Toggle.BorderSizePixel = 0
				TextButton_2_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_2_Toggle.Position = UDim2.new(0.2, 0, 1.87, 0)
				TextButton_2_Toggle.Size = UDim2.new(0, 30, 0, 13)
				TextButton_2_Toggle.Font = Enum.Font.SourceSans
				TextButton_2_Toggle.Text = " "
				TextButton_2_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_2_Toggle.TextSize = 12.000
				TextButton_2_Toggle.AutoButtonColor = false

				local TextButton_Pageframe_Uiconner = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner.Name = ""
				TextButton_Pageframe_Uiconner.Parent = TextButton_2_Toggle

				local TextButton_3_Toggle = Instance.new("TextButton")

				TextButton_3_Toggle.Parent = TextButton_2_Toggle
				TextButton_3_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255,255)
				--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_3_Toggle.BorderSizePixel = 0
				TextButton_3_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_3_Toggle.Position = UDim2.new(0.1, 0, 0.5, 0)
				TextButton_3_Toggle.Size = UDim2.new(0, 19, 0, 19)
				TextButton_3_Toggle.Font = Enum.Font.SourceSans
				TextButton_3_Toggle.Text = " "
				TextButton_3_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_3_Toggle.TextSize = 12.000
				TextButton_3_Toggle.AutoButtonColor = false

				local TextButton_Pageframe_Uiconner2 = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner2.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner2.Name = ""
				TextButton_Pageframe_Uiconner2.Parent = TextButton_3_Toggle

				local TextButton_4_Toggle = Instance.new("TextButton")

				TextButton_4_Toggle.Parent = TextButton_3_Toggle
				TextButton_4_Toggle.BackgroundColor3 = Color3.fromRGB(155, 155,155)
				--        TextButton_3_Toggle.BorderColor3 = _G.ColorMethod
				TextButton_4_Toggle.BorderSizePixel = 0
				TextButton_4_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_4_Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
				TextButton_4_Toggle.Size = UDim2.new(0, 27, 0, 27-2)
				TextButton_4_Toggle.Font = Enum.Font.SourceSans
				TextButton_4_Toggle.Text = " "
				TextButton_4_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_4_Toggle.TextSize = 12.000
				TextButton_4_Toggle.AutoButtonColor = false
				TextButton_4_Toggle.BackgroundTransparency = 1
				TextButton_4_Toggle.Visible = true

				local TextButton_Pageframe_Uiconner4 = Instance.new("UICorner")

				TextButton_Pageframe_Uiconner4.CornerRadius = UDim.new(0, 30)
				TextButton_Pageframe_Uiconner4.Name = ""
				TextButton_Pageframe_Uiconner4.Parent = TextButton_4_Toggle


				local TextButton_Toggle = Instance.new("TextButton")

				TextButton_Toggle.Parent = ValueFrame
				TextButton_Toggle.BackgroundTransparency =1
				TextButton_Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextButton_Toggle.BorderSizePixel = 0
				TextButton_Toggle.Size = UDim2.new(0, 50, 0, 20)
				TextButton_Toggle.AutoButtonColor = false
				TextButton_Toggle.Font = Enum.Font.SourceSans
				TextButton_Toggle.Text = " "
				TextButton_Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				TextButton_Toggle.TextSize = 12.000
				TextButton_Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_Toggle.Position = UDim2.new(1.25, 0, 0.4, 0)

				local TextButton_3_Toggle2 = Instance.new("TextLabel")

				TextButton_3_Toggle2.Parent = TextButton_2_Toggle
				TextButton_3_Toggle2.BackgroundColor3 = Color3.fromRGB(32, 32,32)
				TextButton_3_Toggle2.BorderColor3 = _G.ColorMethod
				TextButton_3_Toggle2.BorderSizePixel = 0
				TextButton_3_Toggle2.AnchorPoint = Vector2.new(0.5, 0.5)
				TextButton_3_Toggle2.Position = UDim2.new(1.9, 0, 0.5, 0)
				TextButton_3_Toggle2.Size = UDim2.new(0, 500, 0, 21)
				TextButton_3_Toggle2.Font = Enum.Font.SourceSansBold
				TextButton_3_Toggle2.Text = "Rainbow"
				TextButton_3_Toggle2.TextColor3 = Color3.fromRGB(255, 255, 255)
				TextButton_3_Toggle2.TextSize = 13.000
				TextButton_3_Toggle2.BackgroundTransparency = 1

				local OMF = Instance.new("TextButton")

				OMF.Parent = TextButton_2_Toggle
				OMF.BackgroundTransparency =1
				OMF.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				OMF.BorderSizePixel = 0
				OMF.Size = UDim2.new(0, 100, 0, 20)
				OMF.AutoButtonColor = false
				OMF.Font = Enum.Font.SourceSans
				OMF.Text = " "
				OMF.TextColor3 = Color3.fromRGB(0, 0, 0)
				OMF.TextSize = 12.000
				OMF.AnchorPoint = Vector2.new(0.5, 0.5)
				OMF.Position = UDim2.new(1.3, 0, 0.5, 0)

				local Color =  Instance.new("ImageLabel")

				Color.Name = "Color"
				Color.Parent = TextFrameColor
				Color.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
				Color.Position = UDim2.new(0.05,0,4,0)
				Color.Size = UDim2.new(0, 195, 0, 40)
				Color.ZIndex = 0
				Color.BorderSizePixel = 0
				Color.Image = "rbxassetid://4155801252"

				local ColorFucj = Instance.new("UICorner")

				ColorFucj.CornerRadius = UDim.new(0, 4)
				ColorFucj.Name = ""
				ColorFucj.Parent = Color

				local ColorSelection =  Instance.new("ImageLabel")

				ColorSelection.Name = "ColorSelection"
				ColorSelection.Parent = Color
				ColorSelection.AnchorPoint = Vector2.new(0.5, 0.5)
				ColorSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ColorSelection.BackgroundTransparency = 1.000
				ColorSelection.Position = UDim2.new(preset and select(3, Color3.toHSV(preset)))
				ColorSelection.Size = UDim2.new(0, 18, 0, 18)
				ColorSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
				ColorSelection.ScaleType = Enum.ScaleType.Fit
				ColorSelection.Visible = true

				local Hue =  Instance.new("ImageLabel")

				Hue.Name = "Hue2"
				Hue.Parent = TextFrameColor
				Hue.Position = UDim2.new(0.14,0,3,0)
				Hue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Hue.Size = UDim2.new(0, 160, 0, 25)
				Hue.ZIndex = 0
				Hue.BorderSizePixel = 0

				local ColorFucj2 = Instance.new("UICorner")

				ColorFucj2.CornerRadius = UDim.new(0, 4)
				ColorFucj2.Name = ""
				ColorFucj2.Parent = Hue

				local HueGradient = Instance.new("UIGradient")

				HueGradient.Color = ColorSequence.new {
					ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)),
					ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)),
					ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)),
					ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)),
					ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)),
					ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)),
					ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))
				}
				HueGradient.Rotation = 0
				HueGradient.Name = "HueGradient"
				HueGradient.Parent = Hue

				local HueSelection =  Instance.new("ImageLabel")

				HueSelection.Name = "HueSelection"
				HueSelection.Parent = Hue
				HueSelection.AnchorPoint = Vector2.new(0.5, 0.5)
				HueSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				HueSelection.BackgroundTransparency = 1.000
				HueSelection.Position = UDim2.new(preset and select(3, Color3.toHSV(preset)))
				HueSelection.Size = UDim2.new(0, 18, 0, 18)
				HueSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
				HueSelection.ScaleType = Enum.ScaleType.Fit
				HueSelection.Visible = true


				local BTN_XD = Instance.new("TextButton")

				BTN_XD.Parent = TextFrameColor
				BTN_XD.BackgroundColor3 = _G.ColorMethod
				BTN_XD.BorderColor3 = _G.ColorMethod
				BTN_XD.BorderSizePixel = 0
				BTN_XD.AnchorPoint = Vector2.new(0.5, 0.5)
				BTN_XD.Position = UDim2.new(0.8, 0, 1.9, 0)
				BTN_XD.Size = UDim2.new(0, 50, 0, 25)
				BTN_XD.Font = Enum.Font.GothamSemibold
				BTN_XD.Text = "Confirm"
				BTN_XD.TextColor3 = Color3.fromRGB(255, 255, 255)
				BTN_XD.TextSize = 11.000
				BTN_XD.AutoButtonColor = false

				local BTN_XD_COnner = Instance.new("UICorner")

				BTN_XD_COnner.CornerRadius = UDim.new(0, 4)
				BTN_XD_COnner.Name = ""
				BTN_XD_COnner.Parent = BTN_XD



				local MheeFrameStroke = Instance.new("UIStroke")

				MheeFrameStroke.Thickness = 1
				MheeFrameStroke.Name = ""
				MheeFrameStroke.Parent = BTN_XD
				MheeFrameStroke.LineJoinMode = Enum.LineJoinMode.Round
				MheeFrameStroke.Color = _G.ColorMethod
				MheeFrameStroke.Transparency = 0.7


				local UwU = false


				OMF.MouseButton1Click:Connect(function()
					if       UwU == false  then
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  _G.ColorMethod} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(153, 0, 102)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
					else
						TweenService:Create(
							TextButton_4_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(155, 155, 155)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 19, 0, 19), UDim2.new(0.1, 0, 0.5, 0), "Out", "Quad", 0.3, true)
					end
					UwU = not UwU
				end
				)


				OMF.MouseEnter:Connect(function()
					TweenService:Create(
						TextButton_4_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.6} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				OMF.MouseLeave:Connect(function()
					TweenService:Create(
						TextButton_4_Toggle,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1} -- UDim2.new(0, 128, 0, 25)
					):Play()
				end
				)

				OMF.MouseButton1Down:Connect(
					function()
						RainbowColorPicker = not RainbowColorPicker

						if ColorInput then
							ColorInput:Disconnect()
						end

						if HueInput then
							HueInput:Disconnect()
						end

						if RainbowColorPicker then


							OldToggleColor = BoxColor.BackgroundColor3
							OldColor = Color.BackgroundColor3
							OldColorSelectionPosition = ColorSelection.Position
							OldHueSelectionPosition = HueSelection.Position

							while RainbowColorPicker do
								BoxColor.BackgroundColor3 = Color3.fromHSV(Red.RainbowColorValue, 1, 1)
								Color.BackgroundColor3 = Color3.fromHSV(Red.RainbowColorValue, 1, 1)

								ColorSelection.Position = UDim2.new(1, 0, 0, 0)
								HueSelection.Position = UDim2.new(0,  Red.HueSelectionPosition, 0.5,0)

								pcall(callback, BoxColor.BackgroundColor3)
								wait()
							end
						elseif not RainbowColorPicker then

							BoxColor.BackgroundColor3 = OldToggleColor
							Color.BackgroundColor3 = OldColor

							ColorSelection.Position = OldColorSelectionPosition
							HueSelection.Position = OldHueSelectionPosition

							pcall(callback, BoxColor.BackgroundColor3)
						end
					end
				)
				TextButton_3_Toggle.MouseButton1Down:Connect(
					function()
						RainbowColorPicker = not RainbowColorPicker

						if ColorInput then
							ColorInput:Disconnect()
						end

						if HueInput then
							HueInput:Disconnect()
						end

						if RainbowColorPicker then


							OldToggleColor = BoxColor.BackgroundColor3
							OldColor = Color.BackgroundColor3
							OldColorSelectionPosition = ColorSelection.Position
							OldHueSelectionPosition = HueSelection.Position

							while RainbowColorPicker do
								BoxColor.BackgroundColor3 = Color3.fromHSV(Red.RainbowColorValue, 1, 1)
								Color.BackgroundColor3 = Color3.fromHSV(Red.RainbowColorValue, 1, 1)

								ColorSelection.Position = UDim2.new(1, 0, 0, 0)
								HueSelection.Position = UDim2.new(0,  Red.HueSelectionPosition, 0.5,0)

								pcall(callback, BoxColor.BackgroundColor3)
								wait()
							end
						elseif not RainbowColorPicker then

							BoxColor.BackgroundColor3 = OldToggleColor
							Color.BackgroundColor3 = OldColor

							ColorSelection.Position = OldColorSelectionPosition
							HueSelection.Position = OldHueSelectionPosition

							pcall(callback, BoxColor.BackgroundColor3)
						end
					end
				)


				local function UpdateColorPicker(nope)
					BoxColor.BackgroundColor3 = Color3.fromHSV(ColorH, ColorS, ColorV)
					Color.BackgroundColor3 = Color3.fromHSV(ColorH, 1, 1)

					pcall(callback, BoxColor.BackgroundColor3)
				end
				ColorH =
					1 -
					(math.clamp(HueSelection.AbsolutePosition.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
						Hue.AbsoluteSize.Y)
				ColorS =
					(math.clamp(ColorSelection.AbsolutePosition.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
						Color.AbsoluteSize.X)
				ColorV =
					1 -
					(math.clamp(ColorSelection.AbsolutePosition.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
						Color.AbsoluteSize.Y)

				BoxColor.BackgroundColor3 = preset
				Color.BackgroundColor3 = preset
				pcall(callback, BoxColor.BackgroundColor3)

				local RainbowColorPicker = false

				Color.InputBegan:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							if RainbowColorPicker then
								return
							end

							if ColorInput then
								ColorInput:Disconnect()
							end

							ColorInput =
								RunService.RenderStepped:Connect(
									function()
										local ColorX =
										(math.clamp(Mouse.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
											Color.AbsoluteSize.X)
										local ColorY =
										(math.clamp(Mouse.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
											Color.AbsoluteSize.Y)

										ColorSelection.Position = UDim2.new(ColorX, 0, ColorY, 0)
										ColorS = ColorX
										ColorV = 1 - ColorY

										UpdateColorPicker(true)
									end
								)
						end
					end
				)


				Color.InputEnded:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							if ColorInput then
								ColorInput:Disconnect()
							end
						end
					end
				)

				Hue.InputBegan:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							if RainbowColorPicker then
								return
							end

							if HueInput then
								HueInput:Disconnect()
							end

							HueInput =
								RunService.RenderStepped:Connect(
									function()
										local HueY =
										(math.clamp(Mouse.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
											Hue.AbsoluteSize.Y)
										local HueX =
										(math.clamp(Mouse.X- Hue.AbsolutePosition.X, 0, Hue.AbsoluteSize.X) /
											Hue.AbsoluteSize.X)

										HueSelection.Position = UDim2.new(HueX, 0, HueY, 0)
										ColorH = 1 - HueY

										UpdateColorPicker(true)
									end
								)
						end
					end
				)

				Hue.InputEnded:Connect(
					function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							if HueInput then
								HueInput:Disconnect()
							end
						end
					end
				)
				local sk = false
				TextButton_Dropdown.MouseButton1Click:Connect(function()
					if sk == false then
						TweenService:Create(
							Pixker,
							TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 213, 0, 180)}
						):Play()
					else
						TweenService:Create(
							Pixker,
							TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 213, 0, 33)}
						):Play()
					end
					sk = not sk
				end
				)
				BTN_XD.MouseButton1Click:Connect(
					function()
						TweenService:Create(
							Pixker,
							TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, 213, 0, 33)}
						):Play()
						sk = not sk
					end
				)


			end
			function items:Label(text)
				local labaelchange = {}
				local LabelFrame = Instance.new("Frame")

				LabelFrame.Name = "Mainframenoti"
				LabelFrame.Parent = ScrollingFrame_Pageframe
				LabelFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				LabelFrame.BackgroundTransparency = 0
				LabelFrame.BorderSizePixel = 0
				LabelFrame.ClipsDescendants = false
				LabelFrame.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelFrame.Position = UDim2.new(0.498, 0, 0.5, 0)
				LabelFrame.Size = UDim2.new(0, 213, 0, 28)
				LabelFrame.BackgroundTransparency = 1

				local LabelFarm2 = Instance.new("TextLabel")

				LabelFarm2.Parent = LabelFrame
				LabelFarm2.Name = "TextLabel_Tap"
				LabelFarm2.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
				LabelFarm2.Size =UDim2.new(0, 130, 0,24 )
				LabelFarm2.Font = Enum.Font.GothamSemibold
				LabelFarm2.Text = " \\\\ "..text.." // "
				LabelFarm2.TextColor3 = Color3.fromRGB(255, 255, 255)
				LabelFarm2.TextSize = 14.000
				LabelFarm2.AnchorPoint = Vector2.new(0.5, 0.5)
				LabelFarm2.Position = UDim2.new(0.5, 0, 0.5, 0)
				LabelFarm2.TextXAlignment = Enum.TextXAlignment.Center
				LabelFarm2.BackgroundTransparency = 1
				LabelFarm2.TextWrapped = true
				function labaelchange:Change(text2)
					LabelFarm2.Text = text2
				end
				return  labaelchange
			end
			return  items
		end
		return  page
	end
	return top
end

-- Script

if game.PlaceId == 2753915549 then
	World1 = true
elseif game.PlaceId == 4442272183 then
	World2 = true
elseif game.PlaceId == 7449423635 then
	World3 = true
end
function CheckQuest() 
	local MyLevel = game.Players.LocalPlayer.Data.Level.Value
	if World1 then
		if MyLevel == 1 or MyLevel <= 9 or _G.Select_Mob_Farm == "Bandit [Lv. 5]" then -- Bandit
			Ms = "Bandit [Lv. 5]"
			NameQuest = "BanditQuest1"
			LevelQuest = 1
			NameMon = "Bandit"
			CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905, -0.942978859, -3.33851502e-09, 0.332852632, 7.04340497e-09, 1, 2.99841325e-08, -0.332852632, 3.06188177e-08, -0.942978859)
			CFrameMon = CFrame.new(1199.31287, 52.2717781, 1536.91516, -0.929782331, 6.60215846e-08, -0.368109822, 3.9077392e-08, 1, 8.06501603e-08, 0.368109822, 6.06023249e-08, -0.929782331)
			SPAWNPOINT = "Default"
		elseif MyLevel == 10 or MyLevel <= 14 or _G.Select_Mob_Farm == "Monkey [Lv. 14]" then -- Monkey
			Ms = "Monkey [Lv. 14]"
			NameQuest = "JungleQuest"
			LevelQuest = 1
			NameMon = "Monkey"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1502.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
			SPAWNPOINT = "Jungle"
		elseif MyLevel == 15 or MyLevel <= 29 or _G.Select_Mob_Farm == "Gorilla [Lv. 20]" then -- Gorilla
			Ms = "Gorilla [Lv. 20]"
			NameQuest = "JungleQuest"
			LevelQuest = 2
			NameMon = "Gorilla"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
			SPAWNPOINT = "Jungle"
		elseif MyLevel == 30 or MyLevel <= 39 or _G.Select_Mob_Farm == "Pirate [Lv. 35]" then -- Pirate
			Ms = "Pirate [Lv. 35]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 1
			NameMon = "Pirate"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1219.32324, 4.75205183, 3915.63452, -0.966492832, -6.91238853e-08, 0.25669381, -5.21195496e-08, 1, 7.3047012e-08, -0.25669381, 5.72206496e-08, -0.966492832)
			SPAWNPOINT = "Pirate"
		elseif MyLevel == 40 or MyLevel <= 59 or _G.Select_Mob_Farm == "Brute [Lv. 45]" then -- Brute
			Ms = "Brute [Lv. 45]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 2
			NameMon = "Brute"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1146.49646, 96.0936813, 4312.1333, -0.978175163, -1.53222057e-08, 0.207781896, -3.33316912e-08, 1, -8.31738873e-08, -0.207781896, -8.82843523e-08, -0.978175163)
			SPAWNPOINT = "Pirate"
		elseif MyLevel == 60 or MyLevel <= 74 or _G.Select_Mob_Farm == "Desert Bandit [Lv. 60]" then -- Desert Bandit
			Ms = "Desert Bandit [Lv. 60]"
			NameQuest = "DesertQuest"
			LevelQuest = 1
			NameMon = "Desert Bandit"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(932.788818, 6.4503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
			SPAWNPOINT = "Desert"
		elseif MyLevel == 75 or MyLevel <= 89 or _G.Select_Mob_Farm == "Desert Officer [Lv. 70]" then -- Desert Officre
			Ms = "Desert Officer [Lv. 70]"
			NameQuest = "DesertQuest"
			LevelQuest = 2
			NameMon = "Desert Officer"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(1580.03198, 4.61375761, 4366.86426, 0.135744005, -6.44280718e-08, -0.990743816, 4.35738308e-08, 1, -5.90598574e-08, 0.990743816, -3.51534837e-08, 0.135744005)
			SPAWNPOINT = "Desert"
		elseif MyLevel == 90 or MyLevel <= 99 or _G.Select_Mob_Farm == "Snow Bandit [Lv. 90]" then -- Snow Bandits
			Ms = "Snow Bandit [Lv. 90]"
			NameQuest = "SnowQuest"
			LevelQuest = 1
			NameMon = "Snow Bandits"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
			SPAWNPOINT = "Ice"
		elseif MyLevel == 100 or MyLevel <= 119 or _G.Select_Mob_Farm == "Snowman [Lv. 100]"  then -- Snowman
			Ms = "Snowman [Lv. 100]"
			NameQuest = "SnowQuest"
			LevelQuest = 2
			NameMon = "Snowman"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
			SPAWNPOINT = "Ice"
		elseif MyLevel == 120 or MyLevel <= 149 or _G.Select_Mob_Farm == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
			Ms = "Chief Petty Officer [Lv. 120]"
			NameQuest = "MarineQuest2"
			LevelQuest = 1
			NameMon = "Chief Petty Officer"
			CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443, 0.0243340395, -7.08064647e-08, 0.999703884, -6.36926814e-08, 1, 7.23777944e-08, -0.999703884, -6.54350671e-08, 0.0243340395)
			CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
			SPAWNPOINT = "MarineBase"
		elseif MyLevel == 150 or MyLevel <= 174 or _G.Select_Mob_Farm == "Sky Bandit [Lv. 150]" then -- Sky Bandit
			Ms = "Sky Bandit [Lv. 150]"
			NameQuest = "SkyQuest"
			LevelQuest = 1
			NameMon = "Sky Bandit"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-4970.74219, 294.544342, -2890.11353, -0.994874597, -8.61311236e-08, -0.101116329, -9.10836206e-08, 1, 4.43614923e-08, 0.101116329, 5.33441664e-08, -0.994874597)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 175 or MyLevel <= 189 or _G.Select_Mob_Farm == "Dark Master [Lv. 175]" then -- Dark Master
			Ms = "Dark Master [Lv. 175]"
			NameQuest = "SkyQuest"
			LevelQuest = 2
			NameMon = "Dark Master"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-5220.58594, 430.693298, -2278.17456, -0.925375521, 1.12086873e-08, 0.379051805, -1.05115507e-08, 1, -5.52320891e-08, -0.379051805, -5.50948407e-08, -0.925375521)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 190 or MyLevel <= 209 or _G.Select_Mob_Farm == "Prisoner [Lv. 190]" then
			Ms = "Prisoner [Lv. 190]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 1
			NameMon = "Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
			SPAWNPOINT = "Prison"
		elseif MyLevel == 210 or MyLevel <= 249 or _G.Select_Mob_Farm == "Dangerous Prisoner [Lv. 210]" then
			Ms = "Dangerous Prisoner [Lv. 210]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 2
			NameMon = "Dangerous Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
			SPAWNPOINT = "Prison"
		elseif MyLevel == 250 or MyLevel <= 274 or _G.Select_Mob_Farm == "Toga Warrior [Lv. 225]" then -- Toga Warrior
			Ms = "Toga Warrior [Lv. 250]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 1
			NameMon = "Toga Warrior"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
			SPAWNPOINT = "Colosseum"
		elseif MyLevel == 275 or MyLevel <= 299 or _G.Select_Mob_Farm == "Gladiator [Lv. 275]" then -- Gladiato
			Ms = "Gladiator [Lv. 275]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 2
			NameMon = "Gladiato"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
			SPAWNPOINT = "Colosseum"
		elseif MyLevel == 300 or MyLevel <= 324 or _G.Select_Mob_Farm == "Military Soldier [Lv. 300]" then -- Military Soldier
			Ms = "Military Soldier [Lv. 300]"
			NameQuest = "MagmaQuest"
			LevelQuest = 1
			NameMon = "Military Soldier"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
			SPAWNPOINT = "Magma"
		elseif MyLevel == 325 or MyLevel <= 374 or _G.Select_Mob_Farm == "Military Spy [Lv. 330]" then -- Military Spy
			Ms = "Military Spy [Lv. 325]"
			NameQuest = "MagmaQuest"
			LevelQuest = 2
			NameMon = "Military Spy"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
			SPAWNPOINT = "Magma"
		elseif MyLevel == 375 or MyLevel <= 399 or _G.Select_Mob_Farm == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior
			Ms = "Fishman Warrior [Lv. 375]"
			NameQuest = "FishmanQuest"
			LevelQuest = 1
			NameMon = "Fishman Warrior"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
			SPAWNPOINT = "Fountain"
			if _G.Auto_Farm_Level and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			end
		elseif MyLevel == 400 or MyLevel <= 449 or _G.Select_Mob_Farm == "Fishman Commando [Lv. 400]" then -- Fishman Commando
			Ms = "Fishman Commando [Lv. 400]"
			NameQuest = "FishmanQuest"
			LevelQuest = 2
			NameMon = "Fishman Commando"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(61885.5039, 18.4828243, 1504.17896, 0.577502489, 0, -0.816389024, -0, 1.00000012, -0, 0.816389024, 0, 0.577502489)
			SPAWNPOINT = "Fountain"
			if _G.Auto_Farm_Level and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			end
		elseif MyLevel == 450 or MyLevel <= 474 or _G.Select_Mob_Farm == "God's Guard [Lv. 450]" then -- God's Guards
			Ms = "God's Guard [Lv. 450]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 1
			NameMon = "God's Guards"
			CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105, -0.999277651, -5.56969759e-09, 0.0380011722, -4.14751478e-09, 1, 3.75035256e-08, -0.0380011722, 3.73188307e-08, -0.999277651)
			CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
			SPAWNPOINT = "Sky"
			if _G.Auto_Farm_Level and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			end
		elseif MyLevel == 475 or MyLevel <= 524 or _G.Select_Mob_Farm == "Shanda [Lv. 475]" then -- Shandas
			sky = false
			Ms = "Shanda [Lv. 475]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 2
			NameMon = "Shandas"
			CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324, 0.362120807, -1.98046344e-08, -0.93213129, 4.05822291e-08, 1, -5.48095125e-09, 0.93213129, -3.58431969e-08, 0.362120807)
			CFrameMon = CFrame.new(-7685.12354, 5601.05127, -443.171509, 0.150056243, 1.79768236e-08, -0.988677442, 6.67798661e-09, 1, 1.91962481e-08, 0.988677442, -9.48289181e-09, 0.150056243)
			SPAWNPOINT = "Sky"
			if _G.Auto_Farm_Level and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			end
		elseif MyLevel == 525 or MyLevel <= 549 or _G.Select_Mob_Farm == "Royal Squad [Lv. 525]" then -- Royal Squad
			sky = true
			Ms = "Royal Squad [Lv. 525]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 1
			NameMon = "Royal Squad"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7685.02051, 5606.87842, -1442.729, 0.561947823, 7.69527464e-09, -0.827172697, -4.24974544e-09, 1, 6.41599973e-09, 0.827172697, -9.01838604e-11, 0.561947823)
			SPAWNPOINT = "Sky2"
		elseif MyLevel == 550 or MyLevel <= 624 or _G.Select_Mob_Farm == "Royal Soldier [Lv. 550]" then -- Royal Soldier
			Dis = 240
			sky = true
			Ms = "Royal Soldier [Lv. 550]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 2
			NameMon = "Royal Soldier"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7864.44775, 5661.94092, -1708.22351, 0.998389959, 2.28686137e-09, -0.0567218624, 1.99431383e-09, 1, 7.54200258e-08, 0.0567218624, -7.54117195e-08, 0.998389959)
			SPAWNPOINT = "Sky2"
		elseif MyLevel == 625 or MyLevel <= 649 or _G.Select_Mob_Farm == "Galley Pirate [Lv. 625]" then -- Galley Pirate
			Dis = 240
			sky = false
			Ms = "Galley Pirate [Lv. 625]"
			NameQuest = "FountainQuest"
			LevelQuest = 1
			NameMon = "Galley Pirate"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5595.06982, 41.5013695, 3961.47095, -0.992138803, -2.11610267e-08, -0.125142589, -1.34249509e-08, 1, -6.26613996e-08, 0.125142589, -6.04887518e-08, -0.992138803)
			SPAWNPOINT = "Fountain"
		elseif MyLevel >= 650 or _G.Select_Mob_Farm == "Galley Captain [Lv. 650]" then -- Galley Captain
			Dis = 240
			Ms = "Galley Captain [Lv. 650]"
			NameQuest = "FountainQuest"
			LevelQuest = 2
			NameMon = "Galley Captain"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5658.5752, 38.5361786, 4928.93506, -0.996873081, 2.12391046e-06, -0.0790185928, 2.16989656e-06, 1, -4.96097414e-07, 0.0790185928, -6.66008248e-07, -0.996873081)
			SPAWNPOINT = "Fountain"
		end
	elseif World2 then
		if MyLevel == 700 or MyLevel <= 724 or _G.Select_Mob_Farm == "Raider [Lv. 700]" then -- Raider [Lv. 700]
			Ms = "Raider [Lv. 700]"
			NameQuest = "Area1Quest"
			LevelQuest = 1
			NameMon = "Raider"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 725 or MyLevel <= 774 or _G.Select_Mob_Farm == "Mercenary [Lv. 725]" then -- Mercenary [Lv. 725]
			Ms = "Mercenary [Lv. 725]"
			NameQuest = "Area1Quest"
			LevelQuest = 2
			NameMon = "Mercenary"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 775 or MyLevel <= 799 or _G.Select_Mob_Farm == "Swan Pirate [Lv. 775]" then -- Swan Pirate [Lv. 775]
			Ms = "Swan Pirate [Lv. 775]"
			NameQuest = "Area2Quest"
			LevelQuest = 1
			NameMon = "Swan Pirate"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667, 0.162079468, -4.85452638e-08, -0.986777723, 1.03357589e-08, 1, -4.74980872e-08, 0.986777723, -2.50063148e-09, 0.162079468)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 800 or MyLevel <= 874 or _G.Select_Mob_Farm == "Factory Staff [Lv. 800]" then -- Factory Staff [Lv. 800]
			Ms = "Factory Staff [Lv. 800]"
			NameQuest = "Area2Quest"
			LevelQuest = 2
			NameMon = "Factory Staff"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(296.786499, 72.9948196, -57.1298141, -0.876037002, -5.32364979e-08, 0.482243896, -3.87658332e-08, 1, 3.99718729e-08, -0.482243896, 1.63222538e-08, -0.876037002)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 875 or MyLevel <= 899 or _G.Select_Mob_Farm == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant [Lv. 875]
			Ms = "Marine Lieutenant [Lv. 875]"
			NameQuest = "MarineQuest3"
			LevelQuest = 1
			NameMon = "Marine Lieutenant"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-2913.26367, 73.0011826, -2971.64282, 0.910507619, 0, 0.413492233, 0, 1.00000012, 0, -0.413492233, 0, 0.910507619)
			SPAWNPOINT = "Greenb"
		elseif MyLevel == 900 or MyLevel <= 949 or _G.Select_Mob_Farm == "Marine Captain [Lv. 900]" then -- Marine Captain [Lv. 900]
			Ms = "Marine Captain [Lv. 900]"
			NameQuest = "MarineQuest3"
			LevelQuest = 2
			NameMon = "Marine Captain"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-1868.67688, 73.0011826, -3321.66333, -0.971402287, 1.06502087e-08, 0.237439692, 3.68856199e-08, 1, 1.06050372e-07, -0.237439692, 1.11775684e-07, -0.971402287)
			SPAWNPOINT = "Greenb"
		elseif MyLevel == 950 or MyLevel <= 974 or _G.Select_Mob_Farm == "Zombie [Lv. 950]" then -- Zombie [Lv. 950]
			Ms = "Zombie [Lv. 950]"
			NameQuest = "ZombieQuest"
			LevelQuest = 1
			NameMon = "Zombie"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039, -0.992770672, 6.77618939e-09, 0.120025545, 1.65461245e-08, 1, 8.04023372e-08, -0.120025545, 8.18070234e-08, -0.992770672)
			SPAWNPOINT = "Graveyard"
		elseif MyLevel == 975 or MyLevel <= 999 or _G.Select_Mob_Farm == "Vampire [Lv. 975]" then -- Vampire [Lv. 975]
			Ms = "Vampire [Lv. 975]"
			NameQuest = "ZombieQuest"
			LevelQuest = 2
			NameMon = "Vampire"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
			SPAWNPOINT = "Graveyard"
		elseif MyLevel == 1000 or MyLevel <= 1049 or _G.Select_Mob_Farm == "Snow Trooper [Lv. 1000]" then -- Snow Trooper [Lv. 1000] **
			Ms = "Snow Trooper [Lv. 1000]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 1
			NameMon = "Snow Trooper"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958, -0.999524176, 0, 0.0308452044, 0, 1, -0, -0.0308452044, 0, -0.999524176)
			SPAWNPOINT = "Snowy"
		elseif MyLevel == 1050 or MyLevel <= 1099 or _G.Select_Mob_Farm == "Winter Warrior [Lv. 1050]" then -- Winter Warrior [Lv. 1050]
			Ms = "Winter Warrior [Lv. 1050]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 2
			NameMon = "Winter Warrior"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148, 0.473996818, 2.56845354e-08, 0.880526543, -5.62456428e-08, 1, 1.10811016e-09, -0.880526543, -5.00510211e-08, 0.473996818)
			SPAWNPOINT = "Snowy"
		elseif MyLevel == 1100 or MyLevel <= 1124 or _G.Select_Mob_Farm == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate [Lv. 1100]
			Ms = "Lab Subordinate [Lv. 1100]"
			NameQuest = "IceSideQuest"
			LevelQuest = 1
			NameMon = "Lab Subordinate"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
			SPAWNPOINT = "CircleIslandIce"
		elseif MyLevel == 1125 or MyLevel <= 1174 or _G.Select_Mob_Farm == "Horned Warrior [Lv. 1125]" then -- Horned Warrior [Lv. 1125]
			Ms = "Horned Warrior [Lv. 1125]"
			NameQuest = "IceSideQuest"
			LevelQuest = 2
			NameMon = "Horned Warrior"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574, -0.964845479, 8.65926566e-08, -0.262817472, 3.98261392e-07, 1, -1.13260398e-06, 0.262817472, -1.19745812e-06, -0.964845479)
			SPAWNPOINT = "CircleIslandIce"
		elseif MyLevel == 1175 or MyLevel <= 1199 or _G.Select_Mob_Farm == "Magma Ninja [Lv. 1175]" then -- Magma Ninja [Lv. 1175]
			Ms = "Magma Ninja [Lv. 1175]"
			NameQuest = "FireSideQuest"
			LevelQuest = 1
			NameMon = "Magma Ninja"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855, -0.885073781, 0, -0.465450764, 0, 1.00000012, -0, 0.465450764, 0, -0.885073781)
			SPAWNPOINT = "CircleIslandFire"
		elseif MyLevel == 1200 or MyLevel <= 1249 or _G.Select_Mob_Farm == "Lava Pirate [Lv. 1200]" then -- Lava Pirate [Lv. 1200]
			Ms = "Lava Pirate [Lv. 1200]"
			NameQuest = "FireSideQuest"
			LevelQuest = 2
			NameMon = "Lava Pirate"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
			SPAWNPOINT = "CircleIslandFire"
		elseif MyLevel == 1250 or MyLevel <= 1274 or _G.Select_Mob_Farm == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand [Lv. 1250]
			Ms = "Ship Deckhand [Lv. 1250]"
			NameQuest = "ShipQuest1"
			LevelQuest = 1
			NameMon = "Ship Deckhand"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1275 or MyLevel <= 1299 or _G.Select_Mob_Farm == "Ship Engineer [Lv. 1275]"  then -- Ship Engineer [Lv. 1275]
			Ms = "Ship Engineer [Lv. 1275]"
			NameQuest = "ShipQuest1"
			LevelQuest = 2
			NameMon = "Ship Engineer"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(916.666504, 44.0920448, 32917.207, -0.99746871, -4.85034697e-08, -0.0711069331, -4.8925461e-08, 1, 4.19294288e-09, 0.0711069331, 7.66126895e-09, -0.99746871)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1300 or MyLevel <= 1324 or _G.Select_Mob_Farm == "Ship Steward [Lv. 1300]" then -- Ship Steward [Lv. 1300]
			Ms = "Ship Steward [Lv. 1300]"
			NameQuest = "ShipQuest2"
			LevelQuest = 1
			NameMon = "Ship Steward"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(918.743286, 129.591064, 33443.4609, -0.999792814, -1.7070947e-07, -0.020350717, -1.72559169e-07, 1, 8.91351277e-08, 0.020350717, 9.2628369e-08, -0.999792814)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1325 or MyLevel <= 1349 or _G.Select_Mob_Farm == "Ship Officer [Lv. 1325]" then -- Ship Officer [Lv. 1325]
			Ms = "Ship Officer [Lv. 1325]"
			NameQuest = "ShipQuest2"
			LevelQuest = 2
			NameMon = "Ship Officer"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(786.051941, 181.474106, 33303.2969, 0.999285698, -5.32193063e-08, 0.0377905183, 5.68968588e-08, 1, -9.62386864e-08, -0.0377905183, 9.83201005e-08, 0.999285698)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1350 or MyLevel <= 1374 or _G.Select_Mob_Farm == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior [Lv. 1350]
			Ms = "Arctic Warrior [Lv. 1350]"
			NameQuest = "FrostQuest"
			LevelQuest = 1
			NameMon = "Arctic Warrior"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314, 0.702747107, -1.53454167e-07, -0.711440146, -1.08168464e-07, 1, -3.22542007e-07, 0.711440146, 3.03620908e-07, 0.702747107)
			SPAWNPOINT = "IceCastle"
		elseif MyLevel == 1375 or MyLevel <= 1424 or _G.Select_Mob_Farm == "Snow Lurker [Lv. 1375]" then -- Snow Lurker [Lv. 1375]
			Ms = "Snow Lurker [Lv. 1375]"
			NameQuest = "FrostQuest"
			LevelQuest = 2
			NameMon = "Snow Lurker"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
			SPAWNPOINT = "IceCastle"
		elseif MyLevel == 1425 or MyLevel <= 1449 or _G.Select_Mob_Farm == "Sea Soldier [Lv. 1425]" then -- Sea Soldier [Lv. 1425]
			Ms = "Sea Soldier [Lv. 1425]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 1
			NameMon = "Sea Soldier"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3029.78467, 66.944252, -9777.38184, -0.998552859, 1.09555076e-08, 0.0537791774, 7.79564235e-09, 1, -5.89660658e-08, -0.0537791774, -5.84614881e-08, -0.998552859)
			SPAWNPOINT = "ForgottenIsland"
		elseif MyLevel >= 1450 or _G.Select_Mob_Farm == "Water Fighter [Lv. 1450]" then -- Water Fighter [Lv. 1450]
			Ms = "Water Fighter [Lv. 1450]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 2
			NameMon = "Water Fighter"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869, -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
			SPAWNPOINT = "ForgottenIsland"
		end
	elseif World3 then
		if MyLevel == 1500 or MyLevel <= 1524 or _G.Select_Mob_Farm == "Pirate Millionaire [Lv. 1500]" then
			Ms = "Pirate Millionaire [Lv. 1500]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 1
			NameMon = "Pirate Millionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
			SPAWNPOINT = "Default"
		elseif MyLevel == 1525 or MyLevel <= 1574 or _G.Select_Mob_Farm == "Pistol Billionaire [Lv. 1525]" then
			Ms = "Pistol Billionaire [Lv. 1525]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 2
			NameMon = "Pistol Billionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
			SPAWNPOINT = "Default"
		elseif MyLevel == 1575 or MyLevel <= 1599 or _G.Select_Mob_Farm == "Dragon Crew Warrior [Lv. 1575]" then
			Ms = "Dragon Crew Warrior [Lv. 1575]"
			NameQuest = "AmazonQuest"
			LevelQuest = 1
			NameMon = "Dragon Crew Warrior"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
			SPAWNPOINT = "Hydra3"
		elseif MyLevel == 1600 or MyLevel <= 1624 or _G.Select_Mob_Farm == "Dragon Crew Archer [Lv. 1600]" then
			Ms = "Dragon Crew Archer [Lv. 1600]"
			NameQuest = "AmazonQuest"
			LevelQuest = 2
			NameMon = "Dragon Crew Archer"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
			SPAWNPOINT = "Hydra3"
		elseif MyLevel == 1625 or MyLevel <= 1649 or _G.Select_Mob_Farm == "Female Islander [Lv. 1625]" then
			Ms = "Female Islander [Lv. 1625]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 1
			NameMon = "Female Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
			SPAWNPOINT = "Hydra1"
		elseif MyLevel == 1650 or MyLevel <= 1699 or _G.Select_Mob_Farm == "Giant Islander [Lv. 1650]" then
			Ms = "Giant Islander [Lv. 1650]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 2
			NameMon = "Giant Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
			SPAWNPOINT = "Hydra1"
		elseif MyLevel == 1700 or MyLevel <= 1724 or _G.Select_Mob_Farm == "Marine Commodore [Lv. 1700]" then
			Ms = "Marine Commodore [Lv. 1700]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 1
			NameMon = "Marine Commodore"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
			SPAWNPOINT = "GreatTree"
		elseif MyLevel == 1725 or MyLevel <= 1774 or _G.Select_Mob_Farm == "Marine Rear Admiral [Lv. 1725]" then
			Ms = "Marine Rear Admiral [Lv. 1725]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 2
			NameMon = "Marine Rear Admiral"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
			SPAWNPOINT = "GreatTree"
		elseif MyLevel == 1775 or MyLevel <= 1799 or _G.Select_Mob_Farm == "Fishman Raider [Lv. 1775]" then
			Ms = "Fishman Raider [Lv. 1775]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 1
			NameMon = "Fishman Raider"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1800 or MyLevel <= 1824 or _G.Select_Mob_Farm == "Fishman Captain [Lv. 1800]" then
			Ms = "Fishman Captain [Lv. 1800]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 2
			NameMon = "Fishman Captain"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1825 or MyLevel <= 1849 or _G.Select_Mob_Farm == "Forest Pirate [Lv. 1825]" then
			Ms = "Forest Pirate [Lv. 1825]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 1
			NameMon = "Forest Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
			SPAWNPOINT = "BigMansion"
		elseif MyLevel == 1850 or MyLevel <= 1899 or _G.Select_Mob_Farm == "Mythological Pirate [Lv. 1850]" then
			Ms = "Mythological Pirate [Lv. 1850]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 2
			NameMon = "Mythological Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
			SPAWNPOINT = "BigMansion"
		elseif MyLevel == 1900 or MyLevel <= 1924 or _G.Select_Mob_Farm == "Jungle Pirate [Lv. 1900]" then
			Ms = "Jungle Pirate [Lv. 1900]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 1
			NameMon = "Jungle Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1925 or MyLevel <= 1974 or _G.Select_Mob_Farm == "Musketeer Pirate [Lv. 1925]" then
			Ms = "Musketeer Pirate [Lv. 1925]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 2
			NameMon = "Musketeer Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1975 or MyLevel <= 1999 or _G.Select_Mob_Farm == "Reborn Skeleton [Lv. 1975]" then
			Ms = "Reborn Skeleton [Lv. 1975]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 1
			NameMon = "Reborn Skeleton"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-8761.3154296875, 164.85829162598, 6161.1567382813)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2000 or MyLevel <= 2024 or _G.Select_Mob_Farm == "Living Zombie [Lv. 2000]" then
			Ms = "Living Zombie [Lv. 2000]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 2
			NameMon = "Living Zombie"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-10093.930664063, 237.38233947754, 6180.5654296875)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2025 or MyLevel <= 2049 or _G.Select_Mob_Farm == "Demonic Soul [Lv. 2025]" then
			Ms = "Demonic Soul [Lv. 2025]"
			NameQuest = "HauntedQuest2"
			LevelQuest = 1
			NameMon = "Demonic Soul"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9466.72949, 171.162918, 6132.01514)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2050 or MyLevel <= 2074 or _G.Select_Mob_Farm == "Posessed Mummy [Lv. 2050]" then
			Ms = "Posessed Mummy [Lv. 2050]" 
			NameQuest = "HauntedQuest2"
			LevelQuest = 2
			NameMon = "Posessed Mummy"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9589.93848, 4.85058546, 6190.27197)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2075 or MyLevel <= 2099 or _G.Select_Mob_Farm == "Peanut Scout [Lv. 2075]" then
			Ms = "Peanut Scout [Lv. 2075]"
			NameQuest = "NutsIslandQuest"
			LevelQuest = 1
			NameMon = "Peanut Scout"
			CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
			CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
			SPAWNPOINT = "Peanut"
		elseif MyLevel == 2100 or MyLevel <= 2124 or _G.Select_Mob_Farm == "Peanut President [Lv. 2100]" then
			Ms = "Peanut President [Lv. 2100]"
			NameQuest = "NutsIslandQuest"
			LevelQuest = 2
			NameMon = "Peanut President"
			CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
			CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
			SPAWNPOINT = "Peanut"
		elseif MyLevel == 2125 or MyLevel <= 2149 or _G.Select_Mob_Farm == "Ice Cream Chef [Lv. 2125]" then
			Ms = "Ice Cream Chef [Lv. 2125]"
			NameQuest = "IceCreamIslandQuest"
			LevelQuest = 1
			NameMon = "Ice Cream Chef"
			CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
			CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
			SPAWNPOINT = "IceCream"
		elseif MyLevel == 2150 or MyLevel <= 2199 or _G.Select_Mob_Farm == "Ice Cream Commander [Lv. 2150]" then
			Ms = "Ice Cream Commander [Lv. 2150]"
			NameQuest = "IceCreamIslandQuest"
			LevelQuest = 2
			NameMon = "Ice Cream Commander"
			CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
			CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
			SPAWNPOINT = "IceCream"
		elseif MyLevel == 2200 or MyLevel <= 2224 or _G.Select_Mob_Farm == "Cookie Crafter [Lv. 2200]" then
			Ms = "Cookie Crafter [Lv. 2200]"
			NameQuest = "CakeQuest1"
			LevelQuest = 1
			NameMon = "Cookie Crafter"
			CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
			CFrameMon = CFrame.new(-2273.00244140625, 90.22590637207031, -12151.62109375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2225 or MyLevel <= 2249 or _G.Select_Mob_Farm == "Cake Guard [Lv. 2225]" then
			Ms = "Cake Guard [Lv. 2225]"
			NameQuest = "CakeQuest1"
			LevelQuest = 2
			NameMon = "Cake Guard"
			CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
			CFrameMon = CFrame.new(-1442.373046875, 158.14111328125, -12277.37109375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2250 or MyLevel <= 2274 or _G.Select_Mob_Farm == "Baking Staff [Lv. 2250]" then
			Ms = "Baking Staff [Lv. 2250]"
			NameQuest = "CakeQuest2"
			LevelQuest = 1
			NameMon = "Baking Staff"
			CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
			CFrameMon = CFrame.new(-1837.2803955078125, 129.0594482421875, -12934.5498046875)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2275 or MyLevel <= 2299 or _G.Select_Mob_Farm == "Head Baker [Lv. 2275]" then
			Ms = "Head Baker [Lv. 2275]"
			NameQuest = "CakeQuest2"
			LevelQuest = 2
			NameMon = "Head Baker"
			CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
			CFrameMon = CFrame.new(-2203.302490234375, 109.90937042236328, -12788.7333984375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2300 or MyLevel <= 2324 or _G.Select_Mob_Farm == "Cocoa Warrior [Lv. 2300]" then
			Ms = "Cocoa Warrior [Lv. 2300]"
			NameQuest = "ChocQuest1"
			LevelQuest = 1
			NameMon = "Cocoa Warrior"
			CFrameQuest = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			CFrameMon = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2325 or MyLevel <= 2349 or _G.Select_Mob_Farm == "Chocolate Bar Battler [Lv. 2325]" then
			Ms = "Chocolate Bar Battler [Lv. 2325]"
			NameQuest = "ChocQuest1"
			LevelQuest = 2
			NameMon = "Chocolate Bar Battler"
			CFrameQuest = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			CFrameMon = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2350 or MyLevel <= 2374 or _G.Select_Mob_Farm == "Sweet Thief [Lv. 2350]" then
			Ms = "Sweet Thief [Lv. 2350]"
			NameQuest = "ChocQuest2"
			LevelQuest = 1
			NameMon = "Sweet Thief"
			CFrameQuest = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			CFrameMon = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2375 or _G.Select_Mob_Farm == "Candy Rebel [Lv. 2375]" then
			Ms = "Candy Rebel [Lv. 2375]"
			NameQuest = "ChocQuest2"
			LevelQuest = 2
			NameMon = "Candy Rebel"
			CFrameQuest = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			CFrameMon = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2400 or _G.Select_Mob_Farm == "Candy Pirate [Lv. 2400]" then
			Ms = "Candy Pirate [Lv. 2400]"
			NameQuest = "CandyQuest1"
			LevelQuest = 1
			NameMon = "Candy Pirates"
			CFrameQuest = CFrame.new(-1150.92224, 16.1330528, -14446.7168, -0.216739461, -1.54126809e-08, -0.976229489, -1.16627412e-07, 1, 1.0105289e-08, 0.976229489, 1.16045328e-07, -0.216739461)
			CFrameMon = CFrame.new(-1422.448, 116.137802, -14605.1836, -0.131237909, -8.23204829e-08, -0.991350889, -8.33612646e-08, 1, -7.20030826e-08, 0.991350889, 7.31907335e-08, -0.131237909)
			SPAWNPOINT = "Snow"
		elseif MyLevel >= 2425 or _G.Select_Mob_Farm == "Snow Demon [Lv. 2425]" then
			Ms = "Snow Demon [Lv. 2425]"
			NameQuest = "CandyQuest1"
			LevelQuest = 2
			NameMon = "Snow Demons"
			CFrameQuest = CFrame.new(-1150.92224, 16.1330528, -14446.7168, -0.216739461, -1.54126809e-08, -0.976229489, -1.16627412e-07, 1, 1.0105289e-08, 0.976229489, 1.16045328e-07, -0.216739461)
			CFrameMon = CFrame.new(-969.235474, 114.227829, -14634.1367, 0.78648001, -6.67341311e-08, -0.617615759, 2.38086972e-08, 1, -7.77329063e-08, 0.617615759, 4.6430749e-08, 0.78648001)
			SPAWNPOINT = "Snow"
		end
	end
end

function AutoHaki()
	if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
	end
end

function EquipWeapon(ToolSe)
	if not _G.NotAutoEquip then
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
			wait(.1)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
		end
	end
end

function Com(com,...)
	local Remote = game:GetService('ReplicatedStorage').Remotes:FindFirstChild("Comm"..com)
	if Remote:IsA("RemoteEvent") then
		Remote:FireServer(...)
	elseif Remote:IsA("RemoteFunction") then
		Remote:InvokeServer(...)
	end
end

-- [Tween Functions]

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


-- [Tween Functions (toTarget)]
getgenv().ToTarget = function (...)
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
	if _G.FastTween then
		if Distance < 400 then
			Speed = 575
		else 
			Speed = 350
		end
	else 
		Speed = 350
	end

	if _G.BypassTp then
		if Distance > 2000 then
			pcall(function()
				tween:Cancel()
				fkwarp = false
				if game:GetService("Players")["LocalPlayer"].Data:FindFirstChild("LastSpawnPoint").Value == tostring(GetIsLand(RealTarget)) then
					game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid"):ChangeState(15)
					wait(0.1)
					repeat wait() until game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0
				else
					if game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0 then
						if fkwarp == false then
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = RealTarget
							tween:cancel()
						end
						fkwarp = true
					end
					wait(.08)
					game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid"):ChangeState(15)
					repeat wait() until game:GetService("Players").LocalPlayer.Character:WaitForChild("Humanoid").Health > 0
					tween:cancel()
					wait(.1)
					Com("F_","SetSpawnPoint")
					wait(0.2)
					tween:cancel()
				end
				return
			end)
		end
	end

	local tween_s = game:service"TweenService"
	local info = TweenInfo.new((RealTarget.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/Speed, Enum.EasingStyle.Linear)
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

---------------------------------------------------------------

function TP(Pos)
	Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
	if game.Players.LocalPlayer.Character.Humanoid.Sit == true then game.Players.LocalPlayer.Character.Humanoid.Sit = false end
	pcall(function() tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/210, Enum.EasingStyle.Linear),{CFrame = Pos}) end)
	tween:Play()
	if Distance <= 110 then
		tween:Cancel()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
	end
	if _G.StopTween == true then
		tween:Cancel()
		_G.Clip = false
	end
end

spawn(function()
	while wait() do
		repeat wait() until game.CoreGui:FindFirstChild('RobloxPromptGui')
		local lp,po,ts = game:GetService('Players').LocalPlayer,game.CoreGui.RobloxPromptGui.promptOverlay,game:GetService('TeleportService')							
		po.ChildAdded:connect(function(a)
			if a.Name == 'ErrorPrompt' then
				repeat
					ts:Teleport(game.PlaceId)
					wait(2)
				until false
			end
		end)
	end
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.Auto_Farm_Level or _G.Auto_New_World or _G.Auto_Third_World or _G.Auto_Farm_Chest or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.Auto_Saber or _G.Auto_Pole or _G.Auto_Farm_Scrap_and_Leather or _G.Auto_Farm_Angel_Wing or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Farm_Radioactive or _G.Auto_Farm_Vampire_Fang or _G.Auto_Farm_Mystic_Droplet or _G.Auto_Farm_GunPowder or _G.Auto_Farm_Dragon_Scales or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Soul_Reaper or _G.Auto_Farm_Fish_Tail or _G.Auto_Farm_Mini_Tusk or _G.Auto_Farm_Magma_Ore or _G.Auto_Farm_Bone or _G.Auto_Farm_Conjured_Cocoa or _G.Auto_Open_Dough_Dungeon or _G.Auto_Rainbow_Haki or _G.Auto_Musketeer_Hat or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Start_Tween_Island or _G.Auto_Next_Island or _G.Auto_Kill_Law then
				if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					local Noclip = Instance.new("BodyVelocity")
					Noclip.Name = "BodyClip"
					Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
					Noclip.MaxForce = Vector3.new(100000,100000,100000)
					Noclip.Velocity = Vector3.new(0,0,0)
				end
			else	
				if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
				end
			end
		end)
	end)
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.Auto_Farm_Level or _G.Auto_New_World or _G.Auto_Third_World or _G.Auto_Farm_Chest or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.Auto_Saber or _G.Auto_Pole or _G.Auto_Farm_Scrap_and_Leather or _G.Auto_Farm_Angel_Wing or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Farm_Radioactive or _G.Auto_Farm_Vampire_Fang or _G.Auto_Farm_Mystic_Droplet or _G.Auto_Farm_GunPowder or _G.Auto_Farm_Dragon_Scales or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Soul_Reaper or _G.Auto_Farm_Fish_Tail or _G.Auto_Farm_Mini_Tusk or _G.Auto_Farm_Magma_Ore or _G.Auto_Farm_Bone or _G.Auto_Farm_Conjured_Cocoa or _G.Auto_Open_Dough_Dungeon or _G.Auto_Rainbow_Haki or _G.Auto_Musketeer_Hat or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Start_Tween_Island or _G.Auto_Next_Island or _G.Auto_Kill_Law then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			end
		end)
	end)
end)

------------------------------------------------------------------------------------------------------------------------

local Window = Windows()
local Main = Window:AddTab("Main")
local page1 = Main:newpage()
local page2 = Main:newpage()
local items = Window:AddTab("items")
local items1 = items:newpage()
local items2 = items:newpage()
local Stats = Window:AddTab("Stats")
local Stats1 = Stats:newpage()
local Stats2 = Stats:newpage()
local pvp = Window:AddTab("PvP")
local pvp1 = pvp:newpage()
local pvp2 = pvp:newpage()
local Teleport = Window:AddTab("Teleport")
local Teleport1 = Teleport:newpage()
local Teleport2 = Teleport:newpage()
local Misc = Window:AddTab("Misc")
local Misc1 = Misc:newpage()
local Misc2 = Misc:newpage()

page1:Label("Auto Farm")

page1:AddToggle("Auto Farm Level",false,function(value)
	_G.Auto_Farm_Level = value
	StopTween(_G.Auto_Farm_Level)
end)


spawn(function()
	while wait() do
		if _G.Auto_Farm_Level then
			pcall(function()
				if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
					StartMagnet = false
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
				end
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					StartMagnet = false
					CheckQuest()
					repeat wait() getgenv().ToTarget(CFrameQuest) until (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Level
					if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
						wait(1.2)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
						wait(0.5)
					end
				elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					CheckQuest()
					if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								if v.Name == Ms then
									repeat wait()
										if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											EquipWeapon(_G.Select_Weapon)
											AutoHaki()
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											StartMagnet = true
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
											game:GetService("VirtualUser"):CaptureController()
											game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
										else
											StartMagnet = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									until not _G.Auto_Farm_Level or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
								end
							end
						end
					else
						StartMagnet = false
						if game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
							getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame * CFrame.new(0,20,0))
						else	
							getgenv().ToTarget(CFrameMon)
						end
					end
				end
			end)
		end
	end
end)


page1:AddToggle("Auto Farm Level",false,function(value)
	_G.Auto_Farm_Level = value
	StopTween(_G.Auto_Farm_Level)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Farm_Level or _G.Auto_Farm_Chest or _G.Auto_Farm_Bone or _G.Auto_Cake_Prince or _G.Auto_Raid or _G.Auto_Next or _G.TeleportIsland or _G.AutoDarkDagger or _G.AutoFarmBossHallow or _G.AutoBudySword or _G.AutoFarmSwanGlasses or _G.AutoElitehunter or _G.Auto_Third_World or _G.Auto_New_World then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

----------------------------------------------------------------------------------------------

page2:Label("Settings")

local SelectWeapon = "Melee";
local Weapon = {
	"Melee",
	"Sword",
	"Fruit"
}

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

page2:Drop("Select Weapon",false,Weapon,function(value)
	SelectWeapon = value
end)

------------ // Fast Attack \\ ------------

page2:AddToggle("Fast Attack", true,function(abc)
	_G.FastAttack = abc
end)

page2:AddToggle("Bring Mob",true,function(value)
	_G.Brimob = value
end)

page2:AddToggle("Fast Tween",false,function(value)
	_G.FastTween = value
end)

page2:AddToggle("Bypass Tp",false,function(value)
	_G.BypassTp = value
end)

-------------------------------------------------------------------------------------------------------------------------------------------------------
spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function() CheckQuest()
		pcall(function()
			if _G.Brimob then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Level and StartMagnet and v.Name == Ms and (v.HumanoidRootPart.Position - PosMon.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMon
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end
		end)
	end)
end)

-------------------------------------------------------------------------------------------------------------------------------------------------------
require(game.ReplicatedStorage.Util.CameraShaker):Stop()
xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
task.spawn(function()
	while true do task.wait()
		if _G.FastAttack then
			if typeof(xShadowx) == "table" then
				pcall(function()
					xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
					xShadowx.activeController.timeToNextAttack = 0
					xShadowx.activeController.hitboxMagnitude = 200
					xShadowx.activeController.active = false
					xShadowx.activeController.timeToNextBlock = 0
					xShadowx.activeController.focusStart = 0
					xShadowx.activeController.increment = 4
					xShadowx.activeController.blocking = false
					xShadowx.activeController.attacking = false
					xShadowx.activeController.humanoid.AutoRotate = true
				end)
			end
		end
	end
end)

local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
local CombatFramework = debug.getupvalues(Module)[2]
local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)

task.spawn(function()
	while true do task.wait()
		if _G.FastAttack then
			pcall(function()
				CameraShakerR:Stop()
				CombatFramework.activeController.attacking = false
				CombatFramework.activeController.timeToNextAttack = 0
				CombatFramework.activeController.increment = 4
				CombatFramework.activeController.hitboxMagnitude = 100
				CombatFramework.activeController.blocking = false
				CombatFramework.activeController.timeToNextBlock = 0
				CombatFramework.activeController.focusStart = 0
				CombatFramework.activeController.humanoid.AutoRotate = true
			end)
		end
	end
end)

local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
local VirtualUser = game:GetService('VirtualUser')
local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
local Client = game:GetService("Players").LocalPlayer
local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)

function SeraphFuckWeapon() 
	local p13 = SeraphFrame.activeController
	local wea = p13.blades[1]
	if not wea then return end
	while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
	return wea
end

function getHits(Size)
	local Hits = {}
	local Enemies = workspace.Enemies:GetChildren()
	local Characters = workspace.Characters:GetChildren()
	for i=1,#Enemies do local v = Enemies[i]
		local Human = v:FindFirstChildOfClass("Humanoid")
		if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
			table.insert(Hits,Human.RootPart)
		end
	end
	for i=1,#Characters do local v = Characters[i]
		if v ~= game.Players.LocalPlayer.Character then
			local Human = v:FindFirstChildOfClass("Humanoid")
			if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
				table.insert(Hits,Human.RootPart)
			end
		end
	end
	return Hits
end

task.spawn(
	function()
		while true do task.wait()
			if  _G.FastAttack then
				if SeraphFrame.activeController then
					--if v.Humanoid.Health > 0 then
						SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
						SeraphFrame.activeController.timeToNextAttack = 0
						SeraphFrame.activeController.focusStart = 0
						SeraphFrame.activeController.hitboxMagnitude = 110
						SeraphFrame.activeController.humanoid.AutoRotate = true
						SeraphFrame.activeController.increment = 4
					--end
				end
			end
		end
	end)

function Boost()
	spawn(function()
		if SeraphFrame.activeController then
			game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
		end
	end)
end

function Unboost()
	spawn(function()
		game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
	end)
end

local cdnormal = 0
local Animation = Instance.new("Animation")
local CooldownFastAttack = 0.000000
Attack = function()
	local ac = SeraphFrame.activeController
	if ac and ac.equipped then
		task.spawn(
			function()
				if tick() - cdnormal > 0 then
					ac:attack()
					cdnormal = tick()
				else
					Animation.AnimationId = ac.anims.basic[2]
					ac.humanoid:LoadAnimation(Animation):Play(0, 0) --ท่าไม่ทำงานแก้เป็น (1,1)
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
				end
				wait(0.12)
			end)
	end
end

b = tick()
spawn(function()
	while _G.FastAttack do task.wait()
		if _G.FastAttack then
			if b - tick() > 9e9 then
				b = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
							Attack()
							wait()
							Boost()
						end
					end
				end
			end)
			wait(0.05)
		end
	end
end)

k = tick()
spawn(function()
	while wait() do
		if  _G.FastAttack then
			if k - tick() > 9e9 then
				k = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
							Unboost()
						end
					end
				end
			end)
		end
	end
end)

tjw1 = true
task.spawn(
	function()
		local a = game.Players.LocalPlayer
		local b = require(a.PlayerScripts.CombatFramework.Particle)
		local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
		if not shared.orl then
			shared.orl = c.wrapAttackAnimationAsync
		end
		if not shared.cpc then
			shared.cpc = b.play
		end
		if tjw1 then
			pcall(
				function()
					c.wrapAttackAnimationAsync = function(d, e, f, g, h)
						local i = c.getBladeHits(e, f, g)
						if i then
							b.play = function()
							end
							d:Play(0.01,0.01,0.01)
							h(i)
							b.play = shared.cpc
							wait(0.1)
							d:Stop()
						end
					end
				end
			)
		end
	end
)

local Client = game.Players.LocalPlayer
local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
task.spawn(function()
	pcall(function()
		if not shared.orl then
			shared.orl = STOPRL.wrapAttackAnimationAsync
		end
		if not shared.cpc then
			shared.cpc = STOP.play 
		end
		spawn(function()
			require(game.ReplicatedStorage.Util.CameraShaker):Stop()
			game:GetService("RunService").Stepped:Connect(function()
				STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
					local Hits = STOPRL.getBladeHits(b,c,d)
					if Hits then
						if  _G.FastAttack then
							STOP.play = function() end
							a:Play(21,29,30)
							func(Hits)
							STOP.play = shared.cpc
							wait(a.length * 9e9)
							a:Stop()
						else
							func(Hits)
							STOP.play = shared.cpc
							wait(a.length * 9e9)
							a:Stop()
						end
					end
				end
			end)
		end)
	end)
end)



--------------------------------------------------------------------------------------------------------------------------------------------------
if World1 then

	page1:AddToggle("Auto New World",false,function(value)
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
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
											game:GetService("VirtualUser"):CaptureController()
											game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 870),workspace.CurrentCamera.CFrame)
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
end
-----------------------------------------------------------------------------------------------------

if World2 then

	page1:AddToggle("Auto Third World",false,function(value)
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
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
											game:GetService("VirtualUser"):CaptureController()
											game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
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
end

----------------------------------------------------------------------------------------------------

page1:Label("Chest")

page1:AddToggle("Auto Farm Chest",false,function(value)
	_G.Auto_Farm_Chest = value
	StopTween(_G.Auto_Farm_Chest)
end)

spawn(function()
	while wait() do
		if _G.Auto_Farm_Chest then
			pcall(function()
				if game:GetService("Workspace"):FindFirstChild("Chest1") or game:GetService("Workspace"):FindFirstChild("Chest2") or game:GetService("Workspace"):FindFirstChild("Chest3") then
					for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
						if v.Name == "Chest1" or v.Name == "Chest2" or v.Name == "Chest3" then
							repeat wait()
								getgenv().ToTarget(v.CFrame)
							until not v.Parent or _G.Auto_Farm_Chest == false
						end
					end
				else
					if _G.Auto_Farm_Chest_Hop then
						Hop()
					end
				end
			end)
		end
	end
end)

page1:AddToggle("Auto Farm Chest Hop",false,function(value)
	_G.Auto_Farm_Chest_Hop = value
end)

-----------------------------------------------------------------------------------------------------------------------

if World1 then
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items1:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
	items2:Label("Go to World 2 - 3")
else
	if World3 then
		items1:Label("EliteHunter")

		local EliteProgress = items1:Label("")

		spawn(function()
			pcall(function()
				while wait() do
					EliteProgress:Set("Elite Progress : "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress"))
				end
			end)
		end)

		items1:AddToggle("Auto Elite Hunter",_G.AutoElitehunter,function(value)
			_G.AutoElitehunter = value
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
			StopTween(_G.AutoElitehunter)
		end)

		spawn(function()
			while wait() do
				if _G.AutoElitehunter and World3 then
					pcall(function()
						local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							repeat  wait()
								getgenv().ToTarget(CFrame.new(-5418.892578125, 313.74130249023, -2826.2260742188)) 
							until not _G.AutoElitehunter or (Vector3.new(-5418.892578125, 313.74130249023, -2826.2260742188)-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3
							if (Vector3.new(-5418.892578125, 313.74130249023, -2826.2260742188)-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
								wait(1.1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
								wait(0.5)
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if string.find(QuestTitle,"Diablo") or string.find(QuestTitle,"Deandre") or string.find(QuestTitle,"Urban") then
								if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Diablo [Lv. 1750]" or v.Name == "Deandre [Lv. 1750]" or v.Name == "Urban [Lv. 1750]" then
											if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat task.wait()
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
													game:GetService("VirtualUser"):CaptureController()
													game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
												until _G.AutoElitehunter == false or v.Humanoid.Health <= 0 or not v.Parent
											end
										end
									end
								else
									if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,35,0))
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,35,0))
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,35,0))
									else
										if _G.AutoEliteHunterHop then
											Hop()
										else
											getgenv().ToTarget(CFrame.new(-5418.892578125, 313.74130249023, -2826.2260742188))
										end
									end
								end                    
							end
						end
					end)
				end
			end
		end)

		items1:AddToggle("Auto Elite Hunter Hop",_G.AutoElitehunterHop,function(value)
			_G.AutoElitehunterHop = value
		end)
	end

	--------------------------------------------------------------------------------------------------------------------

	items1:Label("Buddy Sword")

	items1:AddToggle("Auto Buddy Sword",false,function(value)
		_G.AutoBudySword = value
		StopTween(_G.AutoBudySword)
	end)

	items1:AddToggle("Auto Buddy Sword Hop",false,function(value)
		_G.AutoBudySwordHop = value
	end)

	spawn(function()
		while wait() do
			if _G.AutoBudySword then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Cake Queen [Lv. 2175] [Boss]" then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat task.wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid.WalkSpeed = 0
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
										sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
									until not _G.AutoBudySword or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
							getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]").HumanoidRootPart.CFrame * Method)
						else
							if _G.AutoBudySwordHop then
								Hop()
							end
						end
					end
				end)
			end
		end
	end)

	--------------------------------------------------------------------------------------------------------------------

	items1:Label("Hallow Scythe")

	items1:AddToggle("Auto Hallow Scythe",_G.AutoFarmBossHallow,function(value)
		_G.AutoFarmBossHallow = value
		StopTween(_G.AutoFarmBossHallow)
	end)

	items1:AddToggle("Auto Hallow Scythe Hop",_G.AutoFarmBossHallowHop,function(value)
		_G.AutoFarmBossHallowHop = value
	end)

	spawn(function()
		while wait() do
			if _G.AutoFarmBossHallow then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if string.find(v.Name , "Soul Reaper") then
								repeat task.wait()
									EquipWeapon(_G.Select_Weapon)
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
									game:GetService("VirtualUser"):CaptureController()
									game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
									v.HumanoidRootPart.Transparency = 1
									sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
								until v.Humanoid.Health <= 0 or _G.AutoFarmBossHallow == false
							end
						end
					elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hallow Essence") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hallow Essence") then
						repeat getgenv().ToTarget(CFrame.new(-8932.322265625, 146.83154296875, 6062.55078125)) wait() until (CFrame.new(-8932.322265625, 146.83154296875, 6062.55078125).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 8                        
						EquipWeapon("Hallow Essence")
					else
						if game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
							getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]").HumanoidRootPart.CFrame * Method)
						else
							if _G.AutoFarmBossHallowHop then
								Hop()
							end
						end
					end
				end)
			end
		end
	end)

	--------------------------------------------------------------------------------------------------------------------

	items1:Label("Dark Dagger")

	items1:AddToggle("Auto Dark Dagger",_G.AutoDarkDagger,function(value)
		_G.AutoDarkDagger = value
		StopTween(_G.AutoDarkDagger)
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if _G.AutoDarkDagger then
					if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 5000] [Raid Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == ("rip_indra True Form [Lv. 5000] [Raid Boss]" or v.Name == "rip_indra [Lv. 5000] [Raid Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat task.wait()
									pcall(function()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CanCollide = false
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670),workspace.CurrentCamera.CFrame)
									end)
								until _G.AutoDarkDagger == false or v.Humanoid.Health <= 0
							end
						end
					else
						getgenv().ToTarget(CFrame.new(-5344.822265625, 423.98541259766, -2725.0930175781))
					end
				end
			end
		end)
	end)

	items1:AddToggle("Auto Dark Dagger Hop",_G.AutoDarkDagger_Hop,function(value)
		_G.AutoDarkDagger_Hop = value
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if (_G.AutoDarkDagger_Hop and _G.AutoDarkDagger) and World3 and not game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
					Hop()
				end
			end
		end)
	end)


	items2:Label("Melee")

	items2:AddToggle("Auto Electric Claw",_G.Auto_Electric_Claw,function(value)
		_G.Auto_Electric_Claw = value
		StopTween(_G.Auto_Electric_Claw)
	end)

	spawn(function()
		while wait() do 
			if _G.Auto_Electric_Claw then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						_G.Select_Weapon = "Electric Claw"
					end  
					if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						_G.Select_Weapon = "Electric Claw"
					end  
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 399 then
						_G.Select_Weapon = "Electro"
					end 
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
				end
			end
		end
	end)

	items2:AddToggle("Auto Dragon Talon",_G.Auto_Dragon_Talon,function(value)
		_G.Auto_Dragon_Talon = value
		StopTween(_G.Auto_Dragon_Talon)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Dragon_Talon then
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Talon") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Talon") then
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
						_G.Select_Weapon = "Dragon Talon"
					end  
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
						_G.Select_Weapon = "Dragon Talon"
					end  
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 then
						_G.Select_Weapon = "Dragon Claw"
					end 
				else 
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
				end
			end
		end
	end)

	items2:AddToggle("Auto_God_Human",_G.Auto_God_Human,function(value)
		_G.Auto_God_Human = value
		StopTween(_G.Auto_God_Human)
	end)
end

spawn(function()
	while task.wait() do
		if _G.Auto_God_Human then
			pcall(function()
				if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Death Step") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Death Step") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sharkman Karate") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Talon") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Talon") or game.Players.LocalPlayer.Character:FindFirstChild("Godhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Godhuman") then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true) == 1 then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Character:FindFirstChild("Superhuman").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
						end
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = "Notification", 
							Text = "Not Have Superhuman" ,
							Icon = "http://www.roblox.com/asset/?id=",
							Duration = 2.5
						})
					end
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true) == 1 then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Death Step") and game.Players.LocalPlayer.Character:FindFirstChild("Death Step").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
						end
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = "Notification", 
							Text = "Not Have Death Step" ,
							Icon = "http://www.roblox.com/asset/?id=",
							Duration = 2.5
						})
					end
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						end
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = "Notification", 
							Text = "Not Have SharkMan Karate" ,
							Icon = "http://www.roblox.com/asset/?id=",
							Duration = 2.5
						})
					end
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true) == 1 then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
						end
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = "Notification", 
							Text = "Not Have Electric Claw" ,
							Icon = "http://www.roblox.com/asset/?id=",
							Duration = 2.5
						})
					end
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true) == 1 then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon").Level.Value >= 400 then
							if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true), "Bring") then
								game.StarterGui:SetCore("SendNotification", {
									Title = "Notification", 
									Text = "Not Have Enough Material" ,
									Icon = "http://www.roblox.com/asset/?id=",
									Duration = 2.5
								})
							else
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
							end
						end
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = "Notification", 
							Text = "Not Have Dragon Talon" ,
							Icon = "http://www.roblox.com/asset/?id=",
							Duration = 2.5
						})
					end
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
				end
			end)
		end
	end
end)


-------------------------------------------------------------------------

if World2 then

	items1:Label("Swan Glasses")

	items1:AddToggle("Auto Swan Glasses",false,function(value)
		_G.AutoFarmSwanGlasses = value
		StopTween(_G.AutoFarmSwanGlasses)
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if _G.AutoFarmSwanGlasses then
					if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Don Swan [Lv. 1000] [Boss]" and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat task.wait()
									pcall(function()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CanCollide = false
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
										sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
									end)
								until _G.AutoFarmSwanGlasses == false or v.Humanoid.Health <= 0
							end
						end
					else 
						repeat task.wait()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(2284.912109375, 15.537666320801, 905.48291015625)) 
						until (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 or _G.AutoFarmSwanGlasses == false
					end
				end
			end
		end)
	end)

	items1:AddToggle("Auto Swan Glasses Hop",false,function(value)
		_G.AutoFarmSwanGlasses_Hop = value
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if (_G.AutoFarmSwanGlasses and _G.AutoFarmSwanGlasses_Hop) and World2 and not game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
					Hop()
				end
			end
		end)
	end)
end

--------------------------------------------------------------------------------------------------------------------------------------------------

if World3 then

	page1:Label("Bone")

	local BoneFarm = page1:AddToggle("Auto Farm Bone",_G.Auto_Farm_Bone,function(value)
		_G.Auto_Farm_Bone = value
		StopTween(_G.Auto_Farm_Bone)
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Bone and StartMagnetBoneMon and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and (v.HumanoidRootPart.Position - PosMonBone.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonBone
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
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
									until _G.Auto_Farm_Bone == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetBoneMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Reborn Skeleton [Lv. 1975]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
							elseif v.Name == "Living Zombie [Lv. 2000]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
							elseif v.Name == "Demonic Soul [Lv. 2025]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
							elseif v.Name == "Posessed Mummy [Lv. 2050]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
							end
						end
						getgenv().ToTarget(CFrame.new(-9466.72949, 171.162918, 6132.01514))
					end
				end)
			end
		end
	end)

	page1:AddToggle("Auto Random Surprise",_G.Auto_Random_Bone,function(value)
		_G.Auto_Random_Bone = value
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if _G.Auto_Random_Bone then    
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
				end
			end
		end)
	end)
end
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

if World3 then

	page1:Label("Cake Prince")

	local CakePrince = page1:Label("")

	spawn(function()
		while wait() do
			pcall(function()
				if string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 88 then
					CakePrince:Set("Kill : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,41).." : More!!!")
				elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 87 then
					CakePrince:Set("Kill : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,40).." : More!!!")
				elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 86 then
					CakePrince:Set("Kill : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,39).." : More!!!")
				else
					CakePrince:Set("Boss Is Spawned!!!")
				end
			end)
		end
	end)

	local SpawnCake = page1:AddToggle("Auto Spawn Cake Prince",true,function(value)
		_G.Auto_Spawn_Cake_Prince = value    
		StopTween(_G.Auto_Cake_Prince)
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

	local AutoFarmCake = page1:AddToggle("Auto Cake Prince",false,function(value)
		_G.Auto_Cake_Prince = value
		StopTween(_G.Auto_Cake_Prince)
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Cake_Prince and StartCakeMagnet and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and (v.HumanoidRootPart.Position - POSCAKE.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = POSCAKE
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
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0, -40, 10))
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))									
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
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
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
end

-------------------------------------------------------------------------------------------------------------------


Stats1:Label("Fake")

Stats1:AddToggle("Enabled Fake",false,function(value)
	_G.EnabledStat = value
end)

Stats1:AddTextbox("Level","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Level.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Exp ","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Exp.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Beli","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Beli.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Fragments","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["Localplayer"].Data.Fragments.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Melee","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Defense","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Defense.Level.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Sword","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Sword.Level.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Gun","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Gun.Level.Value = tonumber(value)
	end
end)
Stats1:AddTextbox("Fruit","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats["Demon Fruit"].Level.Value = tonumber(value)
	end
end)

Stats1:AddTextbox("Bounty","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].leaderstats["Bounty/Honor"].Value = tonumber(value)
	end
end)

-------------------------------------------------------------------------------------------------------------

local Pointstat = Stats2:Label("Stat Points")

spawn(function()
	while wait() do
		pcall(function()
			Pointstat:Set("Stat Points : "..tostring(game:GetService("Players")["LocalPlayer"].Data.Points.Value))
		end)
	end
end)

Stats2:AddToggle("Auto Melee",_G.Auto_Melee,function(value)
	_G.Auto_Melee = value
end)

Stats2:AddToggle("Auto Defense",_G.Auto_Defense,function(value)
	_G.Auto_Defense = value
end)

Stats2:AddToggle("Auto Sword",_G.Auto_Sword,function(value)
	_G.Auto_Sword = value
end)

Stats2:AddToggle("Auto Gun",_G.Auto_Gun,function(value)
	_G.Auto_Gun = value
end)

Stats2:AddToggle("Auto Devil Fruits",_G.Auto_DevilFruit,function(value)
	_G.Auto_DevilFruit = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Melee then
				if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
				end
			end
		end)
	end
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Defense then
				if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense",_G.PointStats)
				end
			end
		end)
	end
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Sword then
				if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Sword",_G.PointStats)
				end
			end
		end)
	end
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Gun then
				if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Gun",_G.PointStats)
				end
			end
		end)
	end
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_DevilFruit then
				if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Demon Fruit",_G.PointStats)
				end
			end
		end)
	end
end)

Points = {
	"5", 
	"10",
	"20",
	"30",
	"40",
	"50",
	"60",
	"70",
	"80",
	"90",
	"100",
}

Stats2:Drop("Points Island",false,Points,function(value)
	_G.PointStats = value
end)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
pvp1:Label("Kill Player")

Playerslist = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do
	table.insert(Playerslist,v.Name)
end

local SelectedPly = pvp1:Drop("Select Players",false,Playerslist,function(value)
	_G.Select_Player = value
end)

pvp1:Button("Refresh Player",function()
	Playerslist = {}
	SelectedPly:Clear()
	for i,v in pairs(game:GetService("Players"):GetChildren()) do  
		SelectedPly:Add(v.Name)
	end
end)

pvp1:AddToggle("Spectate Player",_G.Spectate_Player,function(value)
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

pvp1:AddToggle("Teleport to Player",_G.Teleport_to_Player,function(value)
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

pvp1:AddToggle("Auto Kill Player [Melee]",_G.Auto_Kill_Player_Melee,function(value)
	_G.Auto_Kill_Player_Melee = value
	StopTween(_G.Auto_Kill_Player_Melee)
end)


spawn(function()
	while wait() do 
		pcall(function()
			if _G.Auto_Kill_Player_Melee then
				if game.Players:FindFirstChild(_G.Select_Player) then
					for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if v.Name == _G.Select_Player and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0))
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									AutoHaki()
									EquipWeapon(_G.Select_Weapon_Kill_Player_Melee)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,-20))
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								end
							until game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid.Health <= 0 or not _G.Auto_Kill_Player_Melee or not game.Players:FindFirstChild(_G.Select_Player)
						end
					end
				end
			end
		end)
	end
end)



pvp1:Label("PvP")

pvp1:AddToggle("Enabled PvP ",false,function(value)
	_G.EnabledPvP = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.EnabledPvP then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
				end
			end
		end
	end)
end)

pvp1:AddToggle("Safe Mode ",false,function(value)
	_G.Safe_Mode = value
	StopTween(_G.Safe_Mode)
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Safe_Mode then
				game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame
			end
		end
	end)
end)

pvp1:Button("Respawn",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","") 
	wait()
end)

pvp1:Label("Bounty")

local Bounty = pvp1:AddToggle("Auto Farm Bounty",_G.AutoFarmBounty,function(value)
	_G.AutoFarmBounty = value
	StopTween(_G.AutoFarmBounty)
end)

Bounty:lock()

local Bounty1 = pvp1:AddToggle("Auto Farm Bounty Hop ",_G.AutoFarmBounty_Hop,function(value)
	_G.AutoFarmBounty_Hop = value
end)

Bounty1:lock()

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Teleport1:Label("World - Monster")

Teleport1:Button("Teleport To Old World",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end)

Teleport1:Button("Teleport To Second Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
end)

Teleport1:Button("Teleport To Third Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end)


Teleport1:Label("Island")

SelectIsland = {
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

if World1 then
	Teleport1:Drop("Select Island",false,SelectIsland,function(value)
		_G.SelectIsland = value
	end)
end

SelectIsland1 = {
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

if World2 then
	Teleport1:Drop("Select Island",false,SelectIsland1,function(value)
		_G.SelectIsland = value
	end)
end

SelectIsland2 = {
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
	"Cake Island",
	"Noname Island(New)"
}

if World3 then
	Teleport1:Drop("Select Island",false,SelectIsland2,function(value)
		_G.SelectIsland = value
	end)
end

Teleport1:AddToggle("Teleport",false,function(value)
	_G.TeleportIsland = value
	if _G.TeleportIsland == true then
		repeat wait()
			if _G.SelectIsland == "WindMill" then
				getgenv().ToTarget(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
			elseif _G.SelectIsland == "Marine" then
				getgenv().ToTarget(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
			elseif _G.SelectIsland == "Middle Town" then
				getgenv().ToTarget(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
			elseif _G.SelectIsland == "Jungle" then
				getgenv().ToTarget(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
			elseif _G.SelectIsland == "Pirate Village" then
				getgenv().ToTarget(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
			elseif _G.SelectIsland == "Desert" then
				getgenv().ToTarget(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
			elseif _G.SelectIsland == "Snow Island" then
				getgenv().ToTarget(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
			elseif _G.SelectIsland == "MarineFord" then
				getgenv().ToTarget(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
			elseif _G.SelectIsland == "Colosseum" then
				getgenv().ToTarget( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
			elseif _G.SelectIsland == "Sky Island 1" then
				getgenv().ToTarget(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
			elseif _G.SelectIsland == "Sky Island 2" then  
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			elseif _G.SelectIsland == "Sky Island 3" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			elseif _G.SelectIsland == "Prison" then
				getgenv().ToTarget( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
			elseif _G.SelectIsland == "Magma Village" then
				getgenv().ToTarget(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
			elseif _G.SelectIsland == "Under Water Island" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			elseif _G.SelectIsland == "Fountain City" then
				getgenv().ToTarget(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
			elseif _G.SelectIsland == "Shank Room" then
				getgenv().ToTarget(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
			elseif _G.SelectIsland == "Mob Island" then
				getgenv().ToTarget(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
			elseif _G.SelectIsland == "The Cafe" then
				getgenv().ToTarget(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
			elseif _G.SelectIsland == "Frist Spot" then
				getgenv().ToTarget(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
			elseif _G.SelectIsland == "Dark Area" then
				getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
			elseif _G.SelectIsland == "Flamingo Mansion" then
				getgenv().ToTarget(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
			elseif _G.SelectIsland == "Flamingo Room" then
				getgenv().ToTarget(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
			elseif _G.SelectIsland == "Green Zone" then
				getgenv().ToTarget( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
			elseif _G.SelectIsland == "Factory" then
				getgenv().ToTarget(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
			elseif _G.SelectIsland == "Colossuim" then
				getgenv().ToTarget( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
			elseif _G.SelectIsland == "Zombie Island" then
				getgenv().ToTarget(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
			elseif _G.SelectIsland == "Two Snow Mountain" then
				getgenv().ToTarget(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
			elseif _G.SelectIsland == "Punk Hazard" then
				getgenv().ToTarget(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
			elseif _G.SelectIsland == "Cursed Ship" then
				getgenv().ToTarget(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
			elseif _G.SelectIsland == "Ice Castle" then
				getgenv().ToTarget(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
			elseif _G.SelectIsland == "Forgotten Island" then
				getgenv().ToTarget(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
			elseif _G.SelectIsland == "Ussop Island" then
				getgenv().ToTarget(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
			elseif _G.SelectIsland == "Mini Sky Island" then
				getgenv().ToTarget(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
			elseif _G.SelectIsland == "Great Tree" then
				getgenv().ToTarget(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
			elseif _G.SelectIsland == "Castle On The Sea" then
				getgenv().ToTarget(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
			elseif _G.SelectIsland == "MiniSky" then
				getgenv().ToTarget(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
			elseif _G.SelectIsland == "Port Town" then
				getgenv().ToTarget(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
			elseif _G.SelectIsland == "Hydra Island" then
				getgenv().ToTarget(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
			elseif _G.SelectIsland == "Floating Turtle" then
				getgenv().ToTarget(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
			elseif _G.SelectIsland == "Mansion" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
			elseif _G.SelectIsland == "Haunted Castle" then
				getgenv().ToTarget(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
			elseif _G.SelectIsland == "Ice Cream Island" then
				getgenv().ToTarget(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
			elseif _G.SelectIsland == "Peanut Island" then
				getgenv().ToTarget(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
			elseif _G.SelectIsland == "Cake Island" then
				getgenv().ToTarget(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
			elseif _G.SelectIsland == "Noname Island(New)" then
				getgenv().ToTarget(CFrame.new(53.0000267, 58.6640739, -12851.6777, -0.203585744, 0, 0.979057133, 0, 1, 0, -0.979057133, 0, -0.203585744))
			end
		until not _G.TeleportIsland
	end
	StopTween(_G.TeleportIsland)
end)

-----------------------------------------------------------------------------------------------------------------------------------------

Teleport2:Label("Dungeon")

Teleport2:AddToggle("Auto Farm Dungeon ",_G.Auto_Raid,function(value)
	_G.Auto_Raid = value
	StopTween(_G.Auto_Raid)
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Auto_Raid or _G.Auto_Next then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,30,0))
					end
				end
			end
		end
	end)
end)

Teleport2:AddToggle("Kill Aura",_G.Kill,function(value)
	_G.Kill = value
end)

spawn(function()
	pcall(function() 
		while wait() do
			if _G.Auto_Raid or _G.Kill then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
						if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
							pcall(function()
								repeat task.wait()                                    
									v.Humanoid.Health = 0
									v.HumanoidRootPart.CanCollide = false
									sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
								until not _G.Auto_Dungeon and _G.kill or not v.Parent or v.Humanoid.Health <= 0
							end)
						end
					end
				end
			end
		end
	end)
end)

Teleport2:AddToggle("Auto Next Island ",_G.Auto_Next,function(value)
	_G.Auto_Next = value
	StopTween(_G.Auto_Next)
end)

SelectChips = {
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
	"Bird: Phoenix",
	"Dough"
}

Teleport2:Drop("Select Chips",false,SelectChips,function(value)
	_G.SelectChip = value
end)

Teleport2:AddToggle("Auto Select Dungeon",_G.AutoSelectDungeon,function(value)
	_G.AutoSelectDungeon = value
end)

spawn(function()
	while wait() do
		if _G.AutoSelectDungeon then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame-Flame") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame-Flame") then
					_G.SelectChip = "Flame"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice-Ice") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice-Ice") then
					_G.SelectChip = "Ice"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake-Quake") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake-Quake") then
					_G.SelectChip = "Quake"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light-Light") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light-Light") then
					_G.SelectChip = "Light"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark-Dark") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark-Dark") then
					_G.SelectChip = "Dark"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("String-String") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String-String") then
					_G.SelectChip = "String"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble-Rumble") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble-Rumble") then
					_G.SelectChip = "Rumble"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma-Magma") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma-Magma") then
					_G.SelectChip = "Magma"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
					_G.SelectChip = "Human: Buddha"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand-Sand") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand-Sand") then
					_G.SelectChip = "Sand"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird-Bird: Phoenix") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird-Bird: Phoenix") then
					_G.SelectChip = "Bird: Phoenix"
				elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough-Dough") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough-Dough") then
					_G.SelectChip = "Dough"
				else
					_G.SelectChip = "Flame"
				end
			end)
		end
	end
end)

Teleport2:AddToggle("Auto Buy Chip ",_G.AutoBuyChip,function(value)
	_G.AutoBuyChip = value
end)

Teleport2:AddToggle("Auto Start Raid ",_G.Auto_StartRaid,function(value)
	_G.Auto_StartRaid = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
				if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					if _G.Auto_StartRaid then
						if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
							if World2 then
								fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
							elseif World3 then
								fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
							end
						end
					end
				end
			else
				if _G.AutoBuyChip then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", _G.SelectChip)
				end
			end
		end
	end)
end)

Teleport2:Label("DevilFruit")

_G.SelectFruit = "Bomb-Bomb";
FruitList = {
	"Bomb-Bomb",
	"Spike-Spike",
	"Chop-Chop",
	"Spring-Spring",
	"Kilo-Kilo",
	"Spin-Spin",
	"Bird: Falcon",
	"Smoke-Smoke",
	"Flame-Flame",
	"Ice-Ice",
	"Sand-Sand",
	"Dark-Dark",
	"Revive-Revive",
	"Diamond-Diamond",
	"Light-Light",
	"Love-Love",
	"Rubber-Rubber",
	"Barrier-Barrier",
	"Magma-Magma",
	"Door-Door",
	"Quake-Quake",
	"Human-Human: Buddha",
	"String-String",
	"Bird-Bird: Phoenix",
	"Rumble-Rumble",
	"Paw-Paw",
	"Gravity-Gravity",
	"Dough-Dough",
	"Venom-Venom",
	"Shadow-Shadow",
	"Control-Control",
	"Soul-Soul",
	"Dragon-Dragon"
}


Teleport2:Drop("Select Fruits Sniper",false,FruitList,function(value)
	_G.SelectFruit = value
end)

Teleport2:AddToggle("Auto Buy Fruit Sniper",_G.AutoBuyDevilFruitSniper,function(value)
	_G.AutoBuyFruitSniper = value
end)

Teleport2:Drop("Select Fruits Eat",false,FruitList,function(value)
	_G.SelectFruitEat = value
end)

Teleport2:AddToggle("Auto Eat Fruit",_G.AutoEatFruit,function(value)
	_G.AutoEatFruit = value
end)

spawn(function()
	pcall(function()
		while wait(.1) do
			if _G.AutoEatFruit then
				game:GetService("Players").LocalPlayer.Character:FindFirstChild(_G.SelectFruitEat).EatRemote:InvokeServer()
			end
		end
	end)
end)

Teleport2:AddToggle("Auto Eat Fruit Hop",_G.AutoEatFruitHop,function(value)
	_G.AutoEatFruitHop = value
end)

spawn(function()
	pcall(function()
		while wait(.1) do wait(10)
			if _G.AutoEatFruitHop and _G.SelectFruitEat ~= nil then
				if not game:GetService("Players").LocalPlayer.Character:FindFirstChild(_G.SelectFruitEat) or not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(_G.SelectFruitEat) then
					Hop()
				else
					game:GetService("Players").LocalPlayer.Character:FindFirstChild(_G.SelectFruitEat).EatRemote:InvokeServer()
				end
			end
		end
	end)
end)

spawn(function()
	pcall(function()
		while wait(.1) do
			if _G.AutoBuyFruitSniper then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",_G.SelectFruit)
			end 
		end
	end)
end)

Teleport2:AddToggle("Auto Random Fruit",_G.Random_Auto,function(value)
	_G.Random_Auto = value
end)

spawn(function()
	pcall(function()
		while wait(.1) do
			if _G.Random_Auto then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
			end 
		end
	end)
end)

Teleport2:Button("Random Fruit",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
end)


Teleport2:AddToggle("Auto Drop Fruit",_G.DropFruit,function(value)
	_G.DropFruit = value
end)

spawn(function()
	while wait() do
		if _G.DropFruit then
			pcall(function()
				for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
					if string.find(v.Name, "Fruit") then
						EquipWeapon(v.Name)
						wait(.1)
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible == true then
							game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible = false
						end
						EquipWeapon(v.Name)
						game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectFruit).EatRemote:InvokeServer("Drop")
					end
				end
				for i,v in pairs(game:GetService("Players").LocalPlayer.Character:GetChildren()) do
					if string.find(v.Name, "Fruit") then
						EquipWeapon(v.Name)
						wait(.1)
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible == true then
							game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible = false
						end
						EquipWeapon(v.Name)
						game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectFruit).EatRemote:InvokeServer("Drop")
					end
				end
			end)
		end
	end
end)

Teleport2:AddToggle("Auto Store Fruit",_G.AutoStoreFruit,function(value)
	_G.AutoStoreFruit = value
end)

spawn(function()
	pcall(function()
		while wait(.1) do
			if _G.AutoStoreFruit then
				for i,v in pairs(FruitList) do
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit",v)
				end
			end
		end
	end)
end)


Teleport2:AddToggle("Grab Fruit",_G.BringFruit,function(value)
	_G.BringFruit = value
	pcall(function()
		while _G.BringFruit do wait(.1)
			for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
				if v:IsA("Tool") then
					local OldCFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame				
					game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.Handle.CFrame * CFrame.new(0,0,8)
					v.Handle.CFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame
					wait(.1)
					game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = OldCFrame
				end
			end
		end
	end)
end)

-----------------------------------------------------------------------------------------------------------------------------------------

Misc1:Label("Abilities")

Misc1:Button("Buy Geppo [ $10,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
end)

Misc1:Button("Buy Buso Haki [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
end)

Misc1:Button("Buy Soru [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
end)

Misc1:Button("Buy Observation Haki [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
end)

Misc1:AddToggle("Auto Buy Abilities", false, function(t)
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

Misc1:Label("Boats")

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

Misc1:Drop("Select Boats",false,BoatList,function(value)
	SelectBoat = value
end)

Misc1:Button("Buy Boat",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat",_G.SelectBoat)
end)

Misc1:Label("Fighting Style")

Misc1:Button("Buy Black Leg [ $150,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
end)

Misc1:Button("Buy Electro [ $550,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
end)

Misc1:Button("Buy Fishman Karate [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
end)

Misc1:Button("Buy Dragon Claw [ $1,500 Fragments ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
end)

Misc1:Button("Buy Superhuman [ $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
end)

Misc1:Button("Buy Death Step [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
end)

Misc1:Button("Buy Sharkman Karate [ $5,000 Fragments $2,500,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
end)

Misc1:Button("Buy Electric Claw [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
end)

Misc1:Button("Buy Dragon Talon [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
end)

Misc1:Button("Buy God Human [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
end)
-----Shop----------------

Misc1:Label("Sword")

Misc1:Button("Cutlass [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end)

Misc1:Button("Katana [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end)

Misc1:Button("Iron Mace [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end)

Misc1:Button("Dual Katana [ $12,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end)

Misc1:Button("Triple Katana [ $60,000 Beli ]", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end)

Misc1:Button("Pipe [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end)

Misc1:Button("Dual-Headed Blade [ $400,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end)

Misc1:Button("Bisento [ $1,200,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end)

Misc1:Button("Soul Cane [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end)

Misc1:Button("Pole v.2 [ 5,000 Fragments ]",function()
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ThunderGodTalk")
end)

Misc1:AddToggle("Yama Sword [ Elite Hunter 30 ]",_G.AutoYama,function(value)
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

Misc1:Label("Gun")

Misc1:Button("Slingshot [ $5,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end)

Misc1:Button("Musket [ $8,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end)

Misc1:Button("Flintlock [ $10,500 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end)

Misc1:Button("Refined Slingshot [ $30,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
end)

Misc1:Button("Refined Flintlock [ $65,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Refined Flintlock"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Misc1:Button("Cannon [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
end)

Misc1:Button("Kabucha [ 1,500 Fragments]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end)

Misc1:Button("Bizarre Rifle [ 250 Ectoplasm ]", function()
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

Misc1:Label("Bones")

Misc1:Button("Buy Surprise [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
end)

Misc1:Button("Stat Refund [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,2)
end)

Misc1:Button("Race Reroll [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,3)
end)

------------Stat------------------

Misc1:Label("Stat")

Misc1:Button("Reset Stats (Use 2.5K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end)

Misc1:Button("Random Race (Use 3K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","2")
end)
--------------Accessories-----------------
Misc1:Label("Accessories")
Misc1:Button("Black Cape [ $50,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Black Cape"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Misc1:Button("Swordsman Hat [ 150k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Swordsman Hat"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Misc1:Button("Tomoe Ring [ $500k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Tomoe Ring"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

----------------------------------------------------------------

Misc2:Label("WhiteScreen")

Misc2:AddToggle(" WhiteScreen",_G.WhiteScreen,function(value)

	_G.WhiteScreen = value

	if _G.WhiteScreen == true then
		game:GetService("RunService"):Set3dRenderingEnabled(false)
	elseif _G.WhiteScreen == false then
		game:GetService("RunService"):Set3dRenderingEnabled(true)
	end
end)

Misc2:Button("FPS Booster",function()
	FPSBOOT()
end)

function FPSBOOT()
	pcall(function()
		game:GetService("Lighting").FantasySky:Destroy()
		local decalsyeeted = true
		local g = game
		local w = g.Workspace
		local l = g.Lighting
		local t = w.Terrain
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
				--v.CanCollide = false
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
		for i, v in pairs(game:GetService("Workspace").Camera:GetDescendants()) do
			if v.Name == ("Water;") then
				v.Transparency = 1
				v.Material = "Plastic"
			end
		end
	end)
end

Method = CFrame.new(0, 15, 0)

Misc2:Button("All Redeem Code",function()
	for i,v in pairs(Code) do
		UseCode(v) 
	end
end)

Code = {
	"EXP_5B",
	"CONTROL",
	"UPDATE11",
	"XMASEXP",
	"1BILLION",
	"ShutDownFix2",
	"UPD14",
	"STRAWHATMAINE",
	"TantaiGaming",
	"Colosseum",
	"Axiore",
	"Sub2Daigrock",
	"Sky Island 3",
	"Sub2OfficialNoobie",
	"SUB2NOOBMASTER123",
	"THEGREATACE",
	"Fountain City",
	"BIGNEWS",
	"FUDD10",
	"SUB2GAMERROBOT_EXP1",
	"UPD15",
	"2BILLION",
	"UPD16",
	"3BVISITS",
	"fudd10_v2",
	"Starcodeheo",
	"Magicbus",
	"JCWK",
	"Bluxxy",
	"Sub2Fer999",
	"Enyu_is_Pro"
}

--------------------------------------------------------------------

Misc2:Label("Server")

Misc2:Button("Rejoin Server",function()
	game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end)

Misc2:Button("Server Hop",function()
	Hop()
end)

Misc2:Button("Hop To Lower Player",function()
	getgenv().AutoTeleport = true
	getgenv().DontTeleportTheSameNumber = true 
	getgenv().CopytoClipboard = false
	if not game:IsLoaded() then
		print("Game is loading waiting...")
	end
	local maxplayers = math.huge
	local serversmaxplayer;
	local goodserver;
	local gamelink = "https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100" 
	function serversearch()
		for _, v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink)).data) do
			if type(v) == "table" and v.playing ~= nil and maxplayers > v.playing then
				serversmaxplayer = v.maxPlayers
				maxplayers = v.playing
				goodserver = v.id
			end
		end       
	end
	function getservers()
		serversearch()	
		for i,v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink))) do
			if i == "nextPageCursor" then
				if gamelink:find("&cursor=") then
					local a = gamelink:find("&cursor=")
					local b = gamelink:sub(a)
					gamelink = gamelink:gsub(b, "")
				end
				gamelink = gamelink .. "&cursor=" ..v
				getservers()
			end
		end
	end 
	getservers()
	if AutoTeleport then
		if DontTeleportTheSameNumber then 
			if #game:GetService("Players"):GetPlayers() - 4  == maxplayers then
				return warn("It has same number of players (except you)")
			elseif goodserver == game.JobId then
				return warn("Your current server is the most empty server atm") 
			end
		end
		game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, goodserver)
	end
end)

Misc2:Label("Gui")

Misc2:Button("Delete Ui",function()
	game:GetService("CoreGui")["ScreenGui"]:destroy()
	game:GetService("CoreGui")["ExaXGUI"]:destroy()
end)

pvp2:Label("Main")

pvp2:AddToggle("Infinits Energy",_G.WhiteScreen,function(value)
	_G.InfinitsEnergy = value
end)


local LocalPlayer = game:GetService'Players'.LocalPlayer
local originalstam = LocalPlayer.Character.Energy.Value
function infinitestam()
	LocalPlayer.Character.Energy.Changed:connect(function()
		if _G.InfinitsEnergy then
			LocalPlayer.Character.Energy.Value = originalstam
		end 
	end)
end
spawn(function()
	while wait(.1) do
		if _G.InfinitsEnergy then
			wait(0.3)
			originalstam = LocalPlayer.Character.Energy.Value
			infinitestam()
		end
	end
end)

pvp2:AddToggle("Infinit Ability",false,function(value)
	if value then
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		local Agility = game:GetService("ReplicatedStorage").FX["Agility"]:Clone()
		Agility.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
	else
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
		game:GetService("Players").LocalPlayer.Character.HumanoidRootPart["Agility"]:Destroy()
	end
end)

pvp2:AddToggle("Infinite Obversation Range",false,function(value)
	_G.InfiniteObRange = value
	local VS = game:GetService("Players").LocalPlayer.VisionRadius.Value
	while _G.InfiniteObRange do
		wait()
		local player = game:GetService("Players").LocalPlayer
		local char = player.Character
		local VisionRadius = player.VisionRadius
		if player then
			if char.Humanoid.Health <= 0 then 
				wait(5) 
			end
			VisionRadius.Value = math.huge
		elseif _G.InfiniteObRange == false and player then
			VisionRadius.Value = VS
		end
	end
end)

pvp2:AddToggle("Infinite Geppo",false,function(value)
	_G.InfGeppo = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.InfGeppo then
				for i,v in next, getgc() do
					if game:GetService("Players").LocalPlayer.Character.Geppo then
						if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.Character.Geppo then
							for i2,v2 in next, getupvalues(v) do
								if tostring(i2) == "9" then
									repeat wait(.1)
										setupvalue(v,i2,0)
									until not _G.InfGeppo or game:GetService("Players").LocalPlayer.Character.Humanoid.Health <= 0 
								end
							end
						end
					end
				end
			end
		end)
	end
end)

pvp2:AddToggle("Infinite Soru",false,function(value)
	_G.InfSoru = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.InfSoru and game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") ~= nil  then
				for i,v in next, getgc() do
					if game:GetService("Players").LocalPlayer.Character.Soru then
						if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.Character.Soru then
							for i2,v2 in next, getupvalues(v) do
								if typeof(v2) == "table" then
									repeat wait(.1)
										v2.LastUse = 0
									until not _G.InfSoru or game:GetService("Players").LocalPlayer.Character.Humanoid.Health <= 0
								end
							end
						end
					end
				end
			end
		end)
	end
end)

pvp2:AddToggle("Infinite Jump",false, function(State)
	_G.Infinite = State
	game:GetService("UserInputService").JumpRequest:connect(function()
		if _G.Infinite then
			game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
		end
	end) 
end)

function Nomob()
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
		game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
	end
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
		game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
	end
end

Nomob()

--------------------------------------------------------------------

function Delete()
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
		game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
	end
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
		game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
	end
end

Delete()



--------------------------------------------------------------------
