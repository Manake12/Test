
if game.CoreGui:FindFirstChild("SOMEXGUI") then
	game.CoreGui:FindFirstChild("SOMEXGUI"):Destroy()
end

if game.CoreGui:FindFirstChild("OpanGui") then
	game.CoreGui:FindFirstChild("OpanGui"):Destroy()
end

local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui.Name = "OpanGui"
ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton.Size = UDim2.new(0, 60, 0, 60)
ImageButton.Draggable = true
ImageButton.Image = ""
ImageButton.MouseButton1Down:connect(function()
	game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
	game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)

UICorner.Parent = ImageButton

repeat wait(1) until game:IsLoaded()

do
	local ui = game.CoreGui:FindFirstChild("SOMEXGUI")
	if ui then
		ui:Destroy()
	end
end


game:GetService("Players").LocalPlayer.Idled:connect(function()
	game:GetService("VirtualUser"):Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
	wait(1)
	game:GetService("VirtualUser"):Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
end)

if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end

repeat wait() until game:GetService("Players")

if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then repeat wait() until game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") end

wait(1)

do
	local ui = game.CoreGui:FindFirstChild("SOMEXGUI")
	if ui then
		ui:Destroy()
	end
end

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

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

local library = {}

function library:AddWindow(text,keybind)
	local bind = keybind or Enum.KeyCode.RightControl
	local ff = false
	local currenttab = ""

	local DoctorShiba = Instance.new("ScreenGui")
	DoctorShiba.Name = "SOMEXGUI"
	DoctorShiba.Parent = game.CoreGui
	DoctorShiba.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	local Main = Instance.new("Frame")
	Main.Name = "Main"
	Main.Parent = DoctorShiba
	Main.AnchorPoint = Vector2.new(0.5, 0.5)
	Main.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
	Main.BackgroundTransparency = 0.100
	Main.BorderSizePixel = 0
	Main.ClipsDescendants = true
	Main.Position = UDim2.new(0.499526083, 0, 0.499241292, 0)
	Main.Size = UDim2.new(0, 600, 0, 350)

	local Top = Instance.new("Frame")
	Top.Name = "Top"
	Top.Parent = Main
	Top.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Top.BackgroundTransparency = 1.000
	Top.BorderSizePixel = 0
	Top.Size = UDim2.new(0, 600, 0, 20)

	local Page = Instance.new("Frame")
	Page.Name = "Page"
	Page.Parent = Main
	Page.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
	Page.BackgroundTransparency = 0.100
	Page.BorderSizePixel = 0
	Page.Size = UDim2.new(0, 125, 0, 350)

	local NameHub = Instance.new("TextLabel")
	NameHub.Name = "NameHub"
	NameHub.Parent = Page
	NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	NameHub.BackgroundTransparency = 1.000
	NameHub.Position = UDim2.new(0.113333493, 0, 0, 0)
	NameHub.Size = UDim2.new(0, 600, 0, 20)
	NameHub.Font = Enum.Font.Gotham
	NameHub.Text = text
	NameHub.TextColor3 = Color3.fromRGB(255, 0, 195)
	NameHub.TextSize = 11.000
	NameHub.TextXAlignment = Enum.TextXAlignment.Left

	local User = Instance.new("Frame")
	User.Name = "User"
	User.Parent = Page
	User.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	User.BackgroundTransparency = 1.000
	User.Position = UDim2.new(0, 0, 0.8, 30)
	User.Size = UDim2.new(0, 125, 0, 40)

	local UserText = Instance.new("TextLabel")
	UserText.Name = "UserText"
	UserText.Parent = User
	UserText.BackgroundColor3 = Color3.fromRGB(255, 2555, 255)
	UserText.BackgroundTransparency = 1.000
	UserText.Position = UDim2.new(0.354999989, 0, 0, 11)
	UserText.Size = UDim2.new(0, 80, 0, 20)
	UserText.Font = Enum.Font.Gotham
	UserText.Text = tostring(game.Players.LocalPlayer.Name) 
	UserText.TextScaled = true
	UserText.TextSize = 11.000
	UserText.TextWrapped = true
	UserText.TextXAlignment = Enum.TextXAlignment.Left

	local UITextSizeConstraint = Instance.new("UITextSizeConstraint")
	UITextSizeConstraint.Parent = UserText
	UITextSizeConstraint.MaxTextSize = 11

	local UserImage = Instance.new("ImageLabel")
	UserImage.Name = "UserImage"
	UserImage.Parent = User
	UserImage.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
	UserImage.Position = UDim2.new(0, 10, 0, 9)
	UserImage.Size = UDim2.new(0, 25, 0, 25)
	UserImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId="..game.Players.LocalPlayer.UserId.."&width=420&height=420&format=png"

	local UserImageCorner = Instance.new("UICorner")
	UserImageCorner.CornerRadius = UDim.new(0, 100)
	UserImageCorner.Name = "UserImageCorner"
	UserImageCorner.Parent = UserImage

	local ScrollPage = Instance.new("ScrollingFrame")
	ScrollPage.Name = "ScrollPage"
	ScrollPage.Parent = Page
	ScrollPage.Active = true
	ScrollPage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScrollPage.BackgroundTransparency = 1.000
	ScrollPage.BorderSizePixel = 0
	ScrollPage.Position = UDim2.new(0, 0, 0.086, 0)
	ScrollPage.Size = UDim2.new(0, 125, 0, 290)
	ScrollPage.CanvasSize = UDim2.new(0, 0, 0, 0)
	ScrollPage.ScrollBarThickness = 0
	local PageList = Instance.new("UIListLayout")
	PageList.Name = "PageList"
	PageList.Parent = ScrollPage
	PageList.SortOrder = Enum.SortOrder.LayoutOrder
	PageList.Padding = UDim.new(0, 7)

	local PagePadding = Instance.new("UIPadding")
	PagePadding.Name = "PagePadding"
	PagePadding.Parent = ScrollPage
	PagePadding.PaddingTop = UDim.new(0, 5)
	PagePadding.PaddingLeft = UDim.new(0, 28)

	local TabFolder = Instance.new("Folder")
	TabFolder.Name = "TabFolder"
	TabFolder.Parent = Main

	MakeDraggable(Top,Main)

	local uihide = false

	UserInputService.InputBegan:Connect(function(input)
		if input.KeyCode == bind then
			if uihide == false then
				uihide = true
				Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
			else
				uihide = false
				Main:TweenSize(UDim2.new(0, 600, 0, 350),"Out","Quad",0.2,true)
			end
		end
	end)

	local uitab = {}

	function uitab:Tab(text,image)
		local Image = image or 6023426915

		local PageButton = Instance.new("TextButton")
		PageButton.Name = "PageButton"
		PageButton.Parent = ScrollPage
		PageButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		PageButton.BackgroundTransparency = 1.000
		PageButton.BorderSizePixel = 0
		PageButton.Position = UDim2.new(0.224000007, 0, 0.029787235, 0)
		PageButton.Size = UDim2.new(0, 97, 0, 20)
		PageButton.AutoButtonColor = false
		PageButton.Font = Enum.Font.Gotham
		PageButton.Text = text
		PageButton.TextColor3 = Color3.fromRGB(225, 225, 225)
		PageButton.TextSize = 11.000
		PageButton.TextXAlignment = Enum.TextXAlignment.Left

		local MainTab = Instance.new("Frame")
		MainTab.Name = "MainTab"
		MainTab.Parent = TabFolder
		MainTab.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
		MainTab.BorderSizePixel = 0
		MainTab.Position = UDim2.new(0.208333328, 0, 0, 0)
		MainTab.Size = UDim2.new(0, 475, 0, 350)
		MainTab.Visible = false

		local PageImage = Instance.new("ImageLabel")
		PageImage.Name = "PageImage"
		PageImage.Parent = PageButton
		PageImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		PageImage.BackgroundTransparency = 1.000
		PageImage.Position = UDim2.new(0, -20, 0, 3)
		PageImage.Size = UDim2.new(0, 15, 0, 15)
		PageImage.Image = "rbxassetid://"..tostring(Image)

		local ScrollTab = Instance.new("ScrollingFrame")
		ScrollTab.Name = "ScrollTab"
		ScrollTab.Parent = MainTab
		ScrollTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ScrollTab.BackgroundTransparency = 1.000
		ScrollTab.BorderSizePixel = 0
		ScrollTab.Position = UDim2.new(0, 0, 0.057, 0)
		ScrollTab.Size = UDim2.new(0, 475, 0, 330)
		ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
		ScrollTab.ScrollBarThickness = 3

		local TabList = Instance.new("UIListLayout")
		TabList.Name = "TabList"
		TabList.Parent = ScrollTab
		TabList.SortOrder = Enum.SortOrder.LayoutOrder
		TabList.Padding = UDim.new(0, 5)

		local TabPadding = Instance.new("UIPadding")
		TabPadding.Name = "TabPadding"
		TabPadding.Parent = ScrollTab
		TabPadding.PaddingLeft = UDim.new(0, 10)
		TabPadding.PaddingTop = UDim.new(0, 10)

		PageButton.MouseButton1Click:Connect(function()
			currenttab = MainTab.Name
			for i,v in next, TabFolder:GetChildren() do 
				if v.Name == "MainTab" then
					v.Visible = false
				end
			end
			MainTab.Visible = true

			for i,v in next, ScrollPage:GetChildren() do 
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(225, 225, 225)}
					):Play()
				end
				TweenService:Create(
					PageButton,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(255, 0, 195)}
				):Play()
			end
		end)

		if ff == false then
			TweenService:Create(
				PageButton,
				TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
				{TextColor3 = Color3.fromRGB(255, 0, 195)}
			):Play()
			for i,v in next, TabFolder:GetChildren() do 
				if v.Name == "MainTab" then
					v.Visible = false
				end
				MainTab.Visible = true
			end
			ff = true
		end

		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				ScrollPage.CanvasSize = UDim2.new(0,0,0,PageList.AbsoluteContentSize.Y + 10)
				ScrollTab.CanvasSize = UDim2.new(0,0,0,TabList.AbsoluteContentSize.Y + 30)
			end)
		end)

		local main = {}

		function main:Button(text,callback)
			local Button = Instance.new("TextButton")

			Button.Name = "Button"
			Button.Parent = ScrollTab
			Button.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Button.BackgroundTransparency = 0.1
			Button.BorderSizePixel = 0
			Button.Size = UDim2.new(0, 455, 0, 30)
			Button.AutoButtonColor = false
			Button.Font = Enum.Font.Gotham
			Button.Text = text
			Button.TextColor3 = Color3.fromRGB(225, 225, 225)
			Button.TextSize = 11.000
			Button.TextWrapped = true

			local ButtonCorner = Instance.new("UICorner")
			ButtonCorner.Name = "ButtonCorner"
			ButtonCorner.CornerRadius = UDim.new(0, 5)
			ButtonCorner.Parent = Button

			Button.MouseEnter:Connect(function()
				TweenService:Create(
					Button,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(255, 0, 195)}
				):Play()
			end)

			Button.MouseLeave:Connect(function()
				TweenService:Create(
					Button,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)

			Button.MouseButton1Click:Connect(function()
				callback()
				Button.TextSize = 0
				TweenService:Create(
					Button,
					TweenInfo.new(0.4,Enum.EasingStyle.Back,Enum.EasingDirection.Out),
					{TextSize = 11}
				):Play()
			end)
		end

		function main:Toggle(text,config,callback)
			local ToggleImage = Instance.new("Frame")

			local Toggle = Instance.new("TextButton")
			Toggle.Name = "Toggle"
			Toggle.Parent = ScrollTab
			Toggle.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Toggle.BackgroundTransparency = 0.1
			Toggle.BorderSizePixel = 0
			Toggle.AutoButtonColor = false
			Toggle.Size = UDim2.new(0, 455, 0, 30)
			Toggle.Font = Enum.Font.SourceSans
			Toggle.Text = ""
			Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
			Toggle.TextSize = 14.000

			local ToggleCorner = Instance.new("UICorner")
			ToggleCorner.Name = "ToggleCorner"
			ToggleCorner.CornerRadius = UDim.new(0, 5)
			ToggleCorner.Parent = Toggle

			local ToggleLabel = Instance.new("TextLabel")
			ToggleLabel.Name = "ToggleLabel"
			ToggleLabel.Parent = Toggle
			ToggleLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			ToggleLabel.BackgroundTransparency = 1.000
			ToggleLabel.Position = UDim2.new(0, 13, 0, 0)
			ToggleLabel.Size = UDim2.new(0, 410, 0, 30)
			ToggleLabel.Font = Enum.Font.Gotham
			ToggleLabel.Text = text
			ToggleLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			ToggleLabel.TextSize = 11.000
			ToggleLabel.TextXAlignment = Enum.TextXAlignment.Left

			ToggleImage.Name = "ToggleImage"
			ToggleImage.Parent = Toggle
			ToggleImage.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			ToggleImage.Position = UDim2.new(0, 425, 0, 5)
			ToggleImage.BorderSizePixel = 0
			ToggleImage.Size = UDim2.new(0, 20, 0, 20)
			local ToggleImageCorner = Instance.new("UICorner")
			ToggleImageCorner.Name = "ToggleImageCorner"
			ToggleImageCorner.CornerRadius = UDim.new(0, 5)
			ToggleImageCorner.Parent = ToggleImage

			local ToggleImage2 = Instance.new("Frame")
			ToggleImage2.Name = "ToggleImage2"
			ToggleImage2.Parent = ToggleImage
			ToggleImage2.AnchorPoint = Vector2.new(0.5, 0.5)
			ToggleImage2.BackgroundColor3 = Color3.fromRGB(255, 0, 195)
			ToggleImage2.Position = UDim2.new(0, 10, 0, 10)
			ToggleImage2.Visible = false

			local ToggleImage2Corner = Instance.new("UICorner")
			ToggleImage2Corner.Name = "ToggleImageCorner"
			ToggleImage2Corner.CornerRadius = UDim.new(0, 5)
			ToggleImage2Corner.Parent = ToggleImage2

			Toggle.MouseEnter:Connect(function()
				TweenService:Create(
					ToggleLabel,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(255, 0, 195)}
				):Play()
			end)

			Toggle.MouseLeave:Connect(function()
				TweenService:Create(
					ToggleLabel,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)
			if config == nil then config = false end
			local toggled = config or false
			Toggle.MouseButton1Click:Connect(function()
				if toggled == false then
					toggled = true
					ToggleImage2.Visible = true
					ToggleImage2:TweenSize(UDim2.new(0, 21, 0, 21),"In","Quad",0.1,true)
				else
					toggled = false
					ToggleImage2:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.1,true)
					wait(0.1)
					ToggleImage2.Visible = false
				end
				callback(toggled)
			end)

			if config == true then
				ToggleImage2.Visible = true
				ToggleImage2:TweenSize(UDim2.new(0, 21, 0, 21),"In","Quad",0.1,true)
				toggled = true
				callback(toggled)
			end
		end

		function main:Textbox(text,holder,disappear,callback)
			local Textboxx = Instance.new("Frame")
			local TextboxxCorner = Instance.new("UICorner")
			local TextboxTitle = Instance.new("TextLabel")
			local Textbox = Instance.new("TextBox")
			local TextboxCorner = Instance.new("UICorner")

			Textboxx.Name = "Textboxx"
			Textboxx.Parent = ScrollTab
			Textboxx.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Textboxx.Size = UDim2.new(0, 455, 0, 30)

			TextboxxCorner.CornerRadius = UDim.new(0, 5)
			TextboxxCorner.Name = "TextboxxCorner"
			TextboxxCorner.Parent = Textboxx

			TextboxTitle.Name = "TextboxTitle"
			TextboxTitle.Parent = Textboxx
			TextboxTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			TextboxTitle.BackgroundTransparency = 1.000
			TextboxTitle.Position = UDim2.new(0, 15, 0, 0)
			TextboxTitle.Size = UDim2.new(0, 300, 0, 30)
			TextboxTitle.Font = Enum.Font.Gotham
			TextboxTitle.Text = text
			TextboxTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextboxTitle.TextSize = 11.000
			TextboxTitle.TextXAlignment = Enum.TextXAlignment.Left

			Textbox.Name = "Textbox"
			Textbox.Parent = Textboxx
			Textbox.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Textbox.Position = UDim2.new(0, 310, 0, 5)
			Textbox.Size = UDim2.new(0, 140, 0, 20)
			Textbox.Font = Enum.Font.Gotham
			Textbox.Text = holder
			Textbox.TextColor3 = Color3.fromRGB(225, 225, 225)
			Textbox.TextSize = 11.000

			Textbox.FocusLost:Connect(function()
				if #Textbox.Text > 0 then
					callback(Textbox.Text)
				end
				if disappear then
					Textbox.Text = ""
				else
					Textbox.Text = holder
				end
			end)

			TextboxCorner.Name = "TextboxCorner"
			TextboxCorner.CornerRadius = UDim.new(0, 5)
			TextboxCorner.Parent = Textbox
		end

		function main:Dropdown(text,table,callback)
			local Dropdown = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local DropButton = Instance.new("TextButton")
			local Droptitle = Instance.new("TextLabel")
			local DropScroll = Instance.new("ScrollingFrame")
			local DropdownList = Instance.new("UIListLayout")
			local DropdownPadding = Instance.new("UIPadding")
			local DropImage = Instance.new("ImageLabel")

			Dropdown.Name = "Dropdown"
			Dropdown.Parent = ScrollTab
			Dropdown.Active = true
			Dropdown.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Dropdown.ClipsDescendants = true
			Dropdown.Size = UDim2.new(0, 455, 0, 30)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Dropdown

			DropButton.Name = "DropButton"
			DropButton.Parent = Dropdown
			DropButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropButton.BackgroundTransparency = 1.000
			DropButton.Size = UDim2.new(0, 455, 0, 30)
			DropButton.Font = Enum.Font.SourceSans
			DropButton.Text = ""
			DropButton.TextColor3 = Color3.fromRGB(0, 0, 0)
			DropButton.TextSize = 14.000

			Droptitle.Name = "Droptitle"
			Droptitle.Parent = Dropdown
			Droptitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Droptitle.BackgroundTransparency = 1.000
			Droptitle.Position = UDim2.new(0.0281690136, 0, 0, 0)
			Droptitle.Size = UDim2.new(0, 410, 0, 30)
			Droptitle.Font = Enum.Font.Gotham
			Droptitle.Text = text.." : "
			Droptitle.TextColor3 = Color3.fromRGB(225, 225, 225)
			Droptitle.TextSize = 11.000
			Droptitle.TextXAlignment = Enum.TextXAlignment.Left

			DropImage.Name = "DropImage"
			DropImage.Parent = Dropdown
			DropImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropImage.BackgroundTransparency = 1.000
			DropImage.Position = UDim2.new(0, 425, 0, 5)
			DropImage.Rotation = 0
			DropImage.Size = UDim2.new(0, 20, 0, 20)
			DropImage.Image = "rbxassetid://5012539403"

			DropScroll.Name = "DropScroll"
			DropScroll.Parent = Droptitle
			DropScroll.Active = true
			DropScroll.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropScroll.BackgroundTransparency = 1.000
			DropScroll.BorderSizePixel = 0
			DropScroll.Position = UDim2.new(-0.0317460336, 0, 1, 0)
			DropScroll.Size = UDim2.new(0, 455, 0, 70)
			DropScroll.CanvasSize = UDim2.new(0, 0, 0, 2)
			DropScroll.ScrollBarThickness = 2

			DropdownList.Name = "DropdownList"
			DropdownList.Parent = DropScroll
			DropdownList.SortOrder = Enum.SortOrder.LayoutOrder
			DropdownList.Padding = UDim.new(0, 5)

			DropdownPadding.Name = "DropdownPadding"
			DropdownPadding.Parent = DropScroll
			DropdownPadding.PaddingTop = UDim.new(0, 5)

			local isdropping = false

			for i,v in next,table do
				local DropButton2 = Instance.new("TextButton")

				DropButton2.Name = "DropButton2"
				DropButton2.Parent = DropScroll
				DropButton2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				DropButton2.BackgroundTransparency = 1.000
				DropButton2.Size = UDim2.new(0, 455, 0, 30)
				DropButton2.AutoButtonColor = false
				DropButton2.Font = Enum.Font.Gotham
				DropButton2.TextColor3 = Color3.fromRGB(225, 225, 225)
				DropButton2.TextSize = 11.000
				DropButton2.Text = tostring(v)

				DropButton2.MouseEnter:Connect(function()
					TweenService:Create(
						DropButton2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(255, 0, 195)}
					):Play()
				end)
				DropButton2.MouseLeave:Connect(function()
					TweenService:Create(
						DropButton2,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{TextColor3 = Color3.fromRGB(225, 225, 225)}
					):Play()
				end)

				DropButton2.MouseButton1Click:Connect(function()
					TweenService:Create(
						Dropdown,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 455, 0, 30)}
					):Play()
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
						{Rotation = 0}
					):Play()
					Droptitle.Text =  text.." : "..tostring(v)
					callback(v)
					isdropping = not isdropping
					DropScroll.CanvasSize = UDim2.new(0,0,0,DropdownList.AbsoluteContentSize.Y + 10)
				end)
			end

			DropButton.MouseButton1Click:Connect(function()
				if isdropping == false then
					isdropping = true
					TweenService:Create(
						Dropdown,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 455, 0, 100)}
					):Play()
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = -180}
					):Play()
					DropScroll.CanvasSize = UDim2.new(0,0,0,DropdownList.AbsoluteContentSize.Y + 10)
				else
					isdropping = false
					TweenService:Create(
						Dropdown,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 455, 0, 30)}
					):Play()
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = 0}
					):Play()
					DropScroll.CanvasSize = UDim2.new(0,0,0,DropdownList.AbsoluteContentSize.Y + 10)
				end
			end)
			DropScroll.CanvasSize = UDim2.new(0,0,0,DropdownList.AbsoluteContentSize.Y + 10)

			local drop = {}

			function drop:Clear()
				Droptitle.Text = tostring(text).." :"
				TweenService:Create(
					Dropdown,
					TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 455, 0, 30)} 
				):Play()
				isdropping = false
				for i, v in next, DropScroll:GetChildren() do
					if v:IsA("TextButton") then
						v:Destroy()
					end
				end
			end
			function drop:Add(t)
				local DropButton2 = Instance.new("TextButton")

				DropButton2.Name = "DropButton2"
				DropButton2.Parent = DropScroll
				DropButton2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				DropButton2.BackgroundTransparency = 1.000
				DropButton2.Size = UDim2.new(0, 455, 0, 30)
				DropButton2.AutoButtonColor = false
				DropButton2.Font = Enum.Font.Gotham
				DropButton2.TextColor3 = Color3.fromRGB(225, 225, 225)
				DropButton2.TextSize = 11.000
				DropButton2.Text = tostring(t)

				DropButton2.MouseButton1Click:Connect(function()
					TweenService:Create(
						Dropdown,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 455, 0, 30)}
					):Play()
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
						{Rotation = 0}
					):Play()
					Droptitle.Text =  text.." : "..tostring(t)
					callback(t)
					isdropping = not isdropping
					DropScroll.CanvasSize = UDim2.new(0,0,0,DropdownList.AbsoluteContentSize.Y + 10)
				end)
			end
			return drop
		end

		function main:Slider(text,min,max,set,callback)
			set = (math.clamp(set,min,max))
			if set > max then set = max end

			local Slider = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local SliderTitle = Instance.new("TextLabel")
			local SliderValue = Instance.new("TextLabel")
			local SliderButton = Instance.new("TextButton")
			local Bar1 = Instance.new("Frame")
			local Bar = Instance.new("Frame")
			local UICorner_2 = Instance.new("UICorner")
			local CircleBar = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			local UICorner_4 = Instance.new("UICorner")

			Slider.Name = "Slider"
			Slider.Parent = ScrollTab
			Slider.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Slider.Size = UDim2.new(0, 455, 0, 40)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Slider

			SliderTitle.Name = "SliderTitle"
			SliderTitle.Parent = Slider
			SliderTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SliderTitle.BackgroundTransparency = 1.000
			SliderTitle.Position = UDim2.new(0.0283286124, 0, 0, 0)
			SliderTitle.Size = UDim2.new(0, 290, 0, 20)
			SliderTitle.Font = Enum.Font.Gotham
			SliderTitle.Text = text
			SliderTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
			SliderTitle.TextSize = 11.000
			SliderTitle.TextXAlignment = Enum.TextXAlignment.Left

			SliderValue.Name = "SliderValue"
			SliderValue.Parent = Slider
			SliderValue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SliderValue.BackgroundTransparency = 1.000
			SliderValue.Position = UDim2.new(0.887778878, 0, 0, 0)
			SliderValue.Size = UDim2.new(0, 40, 0, 20)
			SliderValue.Font = Enum.Font.Gotham
			SliderValue.Text =  tostring(set and math.floor( (set / max) * (max - min) + min) or 0)
			SliderValue.TextColor3 = Color3.fromRGB(225, 225, 225)
			SliderValue.TextSize = 11.000

			SliderButton.Name = "SliderButton"
			SliderButton.Parent = Slider
			SliderButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SliderButton.BackgroundTransparency = 1.000
			SliderButton.Position = UDim2.new(0, 10, 0, 25)
			SliderButton.Size = UDim2.new(0, 435, 0, 5)
			SliderButton.AutoButtonColor = false
			SliderButton.Font = Enum.Font.SourceSans
			SliderButton.Text = ""
			SliderButton.TextColor3 = Color3.fromRGB(0, 0, 0)
			SliderButton.TextSize = 14.000

			Bar1.Name = "Bar1"
			Bar1.Parent = SliderButton
			Bar1.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Bar1.Size = UDim2.new(0, 435, 0, 5)

			Bar.Name = "Bar"
			Bar.Parent = Bar1
			Bar.BackgroundColor3 = Color3.fromRGB(255, 0, 195)
			Bar.Size = UDim2.new(set/max, 0, 0, 5)

			UICorner_2.CornerRadius = UDim.new(0, 100)
			UICorner_2.Parent = Bar

			CircleBar.Name = "CircleBar"
			CircleBar.Parent = Bar
			CircleBar.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			CircleBar.Position = UDim2.new(1, -2, 0, -2)
			CircleBar.AnchorPoint = Vector2.new(0, 0.1)
			CircleBar.Size = UDim2.new(0, 10, 0, 10)

			UICorner_3.CornerRadius = UDim.new(0, 100)
			UICorner_3.Parent = CircleBar

			UICorner_4.CornerRadius = UDim.new(0, 100)
			UICorner_4.Parent = Bar1

			local mouse = game.Players.LocalPlayer:GetMouse()
			local uis = game:GetService("UserInputService")

			if Value == nil then
				Value = set
				pcall(function()
					callback(Value)
				end)
			end

			SliderButton.MouseButton1Down:Connect(function()
				Value = math.floor((((tonumber(max) - tonumber(min)) / 435) * Bar.AbsoluteSize.X) + tonumber(min)) or 0
				pcall(function()
					callback(Value)
				end)
				Bar.Size = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X, 0, 435), 0, 5)
				CircleBar.Position = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X - 2, 0, 425), 0, -2)
				moveconnection = mouse.Move:Connect(function()
					SliderValue.Text = Value
					Value = math.floor((((tonumber(max) - tonumber(min)) / 435) * Bar.AbsoluteSize.X) + tonumber(min))
					pcall(function()
						callback(Value)
					end)
					Bar.Size = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X, 0, 435), 0, 5)
					CircleBar.Position = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X - 2, 0, 425), 0, -2)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 435) * Bar.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						Bar.Size = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X, 0, 435), 0, 5)
						CircleBar.Position = UDim2.new(0, math.clamp(mouse.X - Bar.AbsolutePosition.X - 2, 0, 425), 0, -2)
						moveconnection:Disconnect()
						releaseconnection:Disconnect()
					end
				end)
			end)
			releaseconnection = uis.InputEnded:Connect(function(Mouse)
				if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
					Value = math.floor((((tonumber(max) - tonumber(min)) / 435) * Bar.AbsoluteSize.X) + tonumber(min))
					SliderValue.Text = Value
				end
			end)
		end
		function main:Seperator(text)
			local Seperator = Instance.new("Frame")
			local Sep1 = Instance.new("Frame")
			local SepLabel = Instance.new("TextLabel")
			local Sep2 = Instance.new("Frame")

			Seperator.Name = "Seperator"
			Seperator.Parent = ScrollTab
			Seperator.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Seperator.BackgroundTransparency = 1.000
			Seperator.ClipsDescendants = true
			Seperator.Size = UDim2.new(0, 455, 0, 20)

			Sep1.Name = "Sep1"
			Sep1.Parent = Seperator
			Sep1.BackgroundColor3 = Color3.fromRGB(255, 0, 195)
			Sep1.BorderSizePixel = 0
			Sep1.Position = UDim2.new(0, 0, 0, 10)
			Sep1.Size = UDim2.new(0, 150, 0, 1)

			SepLabel.Name = "SepLabel"
			SepLabel.Parent = Seperator
			SepLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SepLabel.BackgroundTransparency = 1.000
			SepLabel.Position = UDim2.new(0, 95, 0, 0)
			SepLabel.Size = UDim2.new(0, 255, 0, 20)
			SepLabel.Font = Enum.Font.Gotham
			SepLabel.Text = text
			SepLabel.TextColor3 = Color3.fromRGB(225,225,225)
			SepLabel.TextSize = 11.000

			Sep2.Name = "Sep2"
			Sep2.Parent = Seperator
			Sep2.BackgroundColor3 = Color3.fromRGB(255, 0, 195)
			Sep2.BorderSizePixel = 0
			Sep2.Position = UDim2.new(0, 305, 0, 10)
			Sep2.Size = UDim2.new(0, 150, 0, 1)
		end
		function main:Line()
			local Line = Instance.new("Frame")
			local Linee = Instance.new("Frame")

			Line.Name = "Line"
			Line.Parent = ScrollTab
			Line.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Line.BackgroundTransparency = 1.000
			Line.ClipsDescendants = true
			Line.Size = UDim2.new(0, 455, 0, 20)

			Linee.Name = "Linee"
			Linee.Parent = Line
			Linee.BackgroundColor3 = Color3.fromRGB(255, 0, 195)
			Linee.BorderSizePixel = 0
			Linee.Position = UDim2.new(0, 0, 0, 10)
			Linee.Size = UDim2.new(0, 455, 0, 1)
		end
		function main:Label(text)
			local Label = Instance.new("TextLabel")
			local PaddingLabel = Instance.new("UIPadding")
			local labell = {}

			Label.Name = "Label"
			Label.Parent = ScrollTab
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.Size = UDim2.new(0, 455, 0, 20)
			Label.Font = Enum.Font.Gotham
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 11.000
			Label.Text = text
			Label.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabel.PaddingLeft = UDim.new(0,10)
			PaddingLabel.Parent = Label
			PaddingLabel.Name = "PaddingLabel"

			function labell:Set(newtext)
				Label.Text = newtext
			end

			return labell
		end

		return main
	end
	return uitab
end

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
		elseif MyLevel == 250 or MyLevel <= 300 or _G.Select_Mob_Farm == "Toga Warrior [Lv. 225]" then -- Toga Warrior
			Ms = "Toga Warrior [Lv. 250]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 1
			NameMon = "Toga Warrior"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
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

function topos(Pos)
	Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
	if game.Players.LocalPlayer.Character.Humanoid.Sit == true then game.Players.LocalPlayer.Character.Humanoid.Sit = false end
	pcall(function() tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/210, Enum.EasingStyle.Linear),{CFrame = Pos}) end)
	tween:Play()
	if Distance <= 250 then
		tween:Cancel()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
	end
	if _G.StopTween == true then
		tween:Cancel()
		_G.Clip = false
	end
end

function StopTween(target)
	if not target then
		_G.StopTween = true
		wait()
		topos(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		wait()
		if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
			game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
		end
		_G.StopTween = false
		_G.Clip = false
	end
end


function GetDistance(target)
	return math.floor((target.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude)
end

function UseCode(Text)
	game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
end

function hop()
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
								-- delfile("NotSameServers.json")
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
						-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
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

------------------------------------------------------------------------------------------------------------------------------

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.Auto_Farm_Level or _G.Auto_New_World or _G.TeleportIsland or _G.Auto_Third_World or _G.Auto_Farm_Chest or _G.Auto_Farm_Boss or _G.GunMastery or _G.Mastery or _G.AutoFarmFruitMastery or _G.AutoFarmGunMastery or _G.Auto_Elite_Hunter or _G.AutoFarmKenHaki or _G.AutoFactory or _G.AutoFarmSelectMonster or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.Auto_Saber or _G.Auto_Pole or _G.Auto_Farm_Scrap_and_Leather or _G.Auto_Farm_Angel_Wing or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.d or _G.Auto_Rengoku or _G.Autotushita or _G.Auto_Farm_Radioactive or _G.Auto_Farm_Vampire_Fang or _G.Auto_Farm_Mystic_Droplet or _G.Auto_Farm_GunPowder or _G.Auto_Farm_Dragon_Scales or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Soul_Reaper or _G.Auto_Farm_Fish_Tail or _G.Mirage or _G.Auto_Farm_Magma_Ore or _G.Auto_Farm_Bone or _G.Auto_Farm_Conjured_Cocoa or _G.Auto_Open_Dough_Dungeon or _G.Auto_Rainbow_Haki or _G.Auto_Musketeer_Hat or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.AutoFarmMaterial or _G.autoraid or _G.Auto_Twin_Hook or AutoNextIsland or _G.Auto_Serpent_Bow or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Start_Tween_Island or _G.AutoObservationHakiV2 or _G.d or _G.Auto_Next_Island or _G.Auto_Farm_Sword or _G.MeleeFarm or _G.Auto_Kill_Law or _G.Auto_Raid then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			end
		end)
	end)
end)

------------------------------------------------------------------------------------------------------------------------------
local SOMEXHUB = library:AddWindow("Maruko Hub",Enum.KeyCode.RightControl)
local Main = SOMEXHUB:Tab("Main",6026568198)
local Stats = SOMEXHUB:Tab("Stats",7040410130)
local Combat = SOMEXHUB:Tab("Combat",7251993295)
local Teleport = SOMEXHUB:Tab("Teleport",6035190846)
local Dungeon = SOMEXHUB:Tab("Dungeon",7044284832)
local Shop = SOMEXHUB:Tab("Shop",6031265976)
local DevilFruit = SOMEXHUB:Tab("Devil Fruit",7044233235)
local Misc = SOMEXHUB:Tab("Misc Game",6034509993)

------------------------------------------------------------------------------------------------------------------------------
--\\ ระบบ script //--

--Webhook Script



Main:Seperator("Chack All")

Time = Main:Label("Server Time")

function UpdateTime()
	local GameTime = math.floor(workspace.DistributedGameTime+0.5)
	local Hour = math.floor(GameTime/(60^2))%24
	local Minute = math.floor(GameTime/(60^1))%60
	local Second = math.floor(GameTime/(60^0))%60
	Time:Set("Hr(s) : "..Hour.." Min(s) : "..Minute.." Sec(s) : "..Second)
end

spawn(function()
	while task.wait() do
		pcall(function()
			UpdateTime()
		end)
	end
end)

------------------------------------------------------------------------------------------------------------------------------
Main:Seperator(" \\\\ Auto Farm Level // ")

Main:Toggle("Auto Farm Level",false,function(value)
	_G.Auto_Farm_Level = value
	StopTween(_G.Auto_Farm_Level)
end)

if World1 then
	Main:Toggle("Auto Farm Fast",true,function(value)
		_G.AutoFarmFast = value
		StopTween(_G.AutoFarmFast)
	end)
end

function AutoFarmFast()
	pcall(function()
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		CFrameMon = CFrame.new(-4837.64258, 850.10199, -1840.58374, -0.430530697, -4.42848638e-08, -0.90257591, -3.08042516e-08, 1, -3.43712756e-08, 0.90257591, 1.30052875e-08, -0.430530697)
		if MyLevel >= 15 and MyLevel <= 70 then
			for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
				if v.Name == "God's Guard [Lv. 450]" then
					if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						repeat task.wait()
							EquipWeapon(_G.Select_Weapon)
							AutoHaki()
							v.HumanoidRootPart.CanCollide = false
							v.Humanoid.WalkSpeed = 0
							v.Head.CanCollide = false
							PosMonSky = v.HumanoidRootPart.CFrame
							v.HumanoidRootPart.Transparency = 1
							topos(v.HumanoidRootPart.CFrame * MethodFarm)
							game:GetService'VirtualUser':CaptureController()
							game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
						until not v.Parent or not _G.AutoFarmFast or v.Humanoid.Health < 0
					end
				else
					if _G.Auto_Farm_Level and _G.AutoFarmFast and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 500 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
					end
					topos(CFrameMon)
				end
			end
		elseif MyLevel >= 70 and MyLevel <= 80 then
			if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
			end
			if QuestC.Visible == false then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				end
			elseif QuestC.Visible == true then
				local quest = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
				local Player = string.split(quest," ")[2]
				getgenv().SelectPly = string.split(quest," ")[2]
				if string.find(quest,"Defeat") then
					repeat task.wait()
						if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
						end
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
						end
						EquipWeapon(_G.Select_Weapon)
						topos(game:GetService("Players")[getgenv().SelectPly].Character.HumanoidRootPart.CFrame*CFrame.new(1,0,1))
						game.Players:FindFirstChild(Player).Character.HumanoidRootPart.Size = Vector3.new(120,120,120)
						game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
						game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
						game:GetService'VirtualUser':CaptureController()
						game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
					until game.Players:FindFirstChild(Player).Character.Humanoid.Health <= 0 or not game.Players:FindFirstChild(Player) or not AutoFarmFast()
					if not game.Players:FindFirstChild(Player) then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
					end   
				else
					EquipWeapon(_G.Select_Weapon)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
				end
			end
		end
	end)
end

spawn(function()
	while wait() do
		if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
			if _G.Auto_Farm_Level then
				local args = {
					[1] = "StartQuest",
					[2] = NameQuest, 
					[3] = LevelQuest
				}
				game:GetService("ReplicatedStorage").Remotes.CommF:InvokeServer(unpack(args))

			end
		end
	end
end)

task.spawn(function()
	while wait() do
		pcall(function()
			local MyLevel = game.Players.LocalPlayer.Data.Level.Value
			if _G.AutoFarmFast then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if (v.HumanoidRootPart.Position - PosMonSky.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMonSky
						v.Humanoid.JumpPower = 0
						v.Humanoid.WalkSpeed = 0
						v.HumanoidRootPart.CanCollide = false
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						v.Humanoid:ChangeState(11)
					end
				end
			end
		end)
	end
end)

Main:Toggle("Auto Farm Mob Aura",false,function(value)
	_G.Auto_Farm_Mob_Aura = value
	StopTween(_G.Auto_Farm_Mob_Aura)
end)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Farm_Mob_Aura then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if _G.Auto_Farm_Mob_Aura and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 1000 then
						repeat wait()
							StartMagnet = true
							EquipWeapon(_G.Select_Weapon)
							AutoHaki()
							PosMonAura = v.HumanoidRootPart.CFrame
							v.HumanoidRootPart.Size = Vector3.new(60,60,60)
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.Humanoid:ChangeState(11)
							topos(v.HumanoidRootPart.CFrame * MethodFarm)
							game:GetService'VirtualUser':CaptureController()
							game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
						until not _G.Auto_Farm_Mob_Aura or not v.Parent or v.Humanoid.Health <= 0
					end
				end
			end
		end)
	end
end)

task.spawn(function()
	while wait() do
		pcall(function()
			local MyLevel = game.Players.LocalPlayer.Data.Level.Value
			if _G.Auto_Farm_Mob_Aura then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if (v.HumanoidRootPart.Position - PosMonAura.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMonAura
						v.Humanoid.JumpPower = 0
						v.Humanoid.WalkSpeed = 0
						v.HumanoidRootPart.CanCollide = false
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						v.Humanoid:ChangeState(11)
					end
				end
			end
		end)
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Farm_Mob_Aura then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)


------------------------------------------------------------------------------------------------------------------------------

spawn(function()
	while wait() do
		if _G.Auto_Farm_Level then
			pcall(function()
				local MyLevel = game.Players.LocalPlayer.Data.Level.Value
				if _G.AutoFarmFast and (MyLevel >= 15 and MyLevel <= 300) then
					if MyLevel >= 15 and MyLevel <= 300 then
						AutoFarmFast()
					end
				else
					if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
						StartMagnet = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
					end
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						StartMagnet = false
						CheckQuest()
						repeat wait() topos(CFrameQuest) until (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Level
						if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
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
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
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
								topos(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame * MethodFarm)
							else	
								topos(CFrameMon)
							end
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Farm_Level then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)


if World1 then

	Main:Seperator(" \\\\ World //")

	Main:Toggle("Auto New World",false,function(value)
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
							repeat wait() topos(CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563)) until (CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
							wait(1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
							EquipWeapon("Key")
							local pos2 = CFrame.new(1347.7124, 37.3751602, -1325.6488)
							repeat wait() topos(pos2) until (pos2.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
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
											topos(v.HumanoidRootPart.CFrame * MethodFarm)
										until v.Humanoid.Health <= 0 or not v.Parent or not _G.Auto_New_World
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
									end
								end
							else
								topos(CFrame.new(1347.7124, 37.3751602, -1325.6488))
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

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_New_World then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)


------------------------------------------------------------------------------------------------------------------------------

if World2 then

	Main:Seperator(" \\\\ World //")	

	Main:Toggle("Auto Third World",false,function(value)
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
							topos(CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016))
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
											topos(v.HumanoidRootPart.CFrame * MethodFarm)
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Third_World == false or v.Humanoid.Health <= 0 or not v.Parent
									end
								end
							elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") and (CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
								topos(CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016))
							end
						end
					end
				end)
			end
		end
	end)
end

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Third_World then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Fighting Style // ")

Main:Toggle("Auto Superhuman",_G.AutoSuperhuman,function(value)
	_G.AutoSuperhuman = value
end)

spawn(function()
	pcall(function()
		while wait() do 
			if _G.AutoSuperhuman then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 150000 then
					EquipWeapon("Combat")
					wait(.1)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
				end   
				if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") then
					_G.Select_Weapon = "Superhuman"
				end  
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 then
						_G.Select_Weapon = "Black Leg"
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299 then
						_G.Select_Weapon = "Electro"
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 then
						_G.Select_Weapon = "Fishman Karate"
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299 then
						_G.Select_Weapon = "Dragon Claw"
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 300000 then
						EquipWeapon("Black Leg")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 300000 then
						EquipWeapon("Black Leg")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 750000 then
						EquipWeapon("Electro")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 750000 then
						EquipWeapon("Electro")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game:GetService("Players")["Localplayer"].Data.Fragments.Value >= 1500 then
						EquipWeapon("Fishman Karate")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2") 
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game:GetService("Players")["Localplayer"].Data.Fragments.Value >= 1500 then
						EquipWeapon("Fishman Karate")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2") 
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 3000000 then
						EquipWeapon("Dragon Claw")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 3000000 then
						EquipWeapon("Dragon Claw")
						wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
					end 
				end
			end
		end
	end)
end)

Main:Toggle("Auto DeathStep",_G.AutoDeathStep,function(value)
	_G.AutoDeathStep = value
end)

spawn(function()
	while wait() do wait()
		if _G.AutoDeathStep then
			if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Death Step") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Death Step") then
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
					_G.Select_Weapon = "Death Step"
				end  
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
					_G.Select_Weapon = "Death Step"
				end  
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 449 then
					_G.Select_Weapon = "Black Leg"
				end 
			else 
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
			end
		end
	end
end)

Main:Toggle("Auto Sharkman Karate",_G.AutoSharkman,function(value)
	_G.AutoSharkman = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.AutoSharkman then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
				if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key") then
						topos(CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365))
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
					else 
						Ms = "Tide Keeper [Lv. 1475] [Boss]"
						if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then   
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == Ms then    
									OldCFrameShark = v.HumanoidRootPart.CFrame
									repeat task.wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.Head.CanCollide = false
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										v.HumanoidRootPart.CFrame = OldCFrameShark
										topos(v.HumanoidRootPart.CFrame * MethodFarm)
										game:GetService("VirtualUser"):CaptureController()
										game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
										sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
									until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoSharkman == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key")
								end
							end
						else
							topos(CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202))
							wait(3)
						end
					end
				else 
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
				end
			end
		end
	end)
end)

Main:Toggle("Auto Electric Claw",_G.AutoElectricClaw,function(value)
	_G.AutoElectricClaw = value
	StopTween(_G.AutoElectricClaw)
end)

spawn(function()
	pcall(function()
		while wait() do 
			if _G.AutoElectricClaw then
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electric Claw") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electric Claw") then
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						_G.Select_Weapon = "Electric Claw"
					end  
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						_G.Select_Weapon = "Electric Claw"
					end  
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 399 then
						_G.Select_Weapon = "Electro"
					end 
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
				end
			end
			if _G.AutoElectricClaw then
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") then
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
						if _G.Auto_Farm_Level == false then
							repeat task.wait()
								topos(CFrame.new(-10371.4717, 330.764496, -10131.4199))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
							wait(2)
							repeat task.wait()
								topos(CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438).Position).Magnitude <= 10
							wait(1)
							repeat task.wait()
								topos(CFrame.new(-10371.4717, 330.764496, -10131.4199))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
							wait(1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
						elseif _G.Auto_Farm_Level == true then
							_G.Auto_Farm_Level = false
							wait(1)
							repeat task.wait()
								topos(CFrame.new(-10371.4717, 330.764496, -10131.4199))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
							wait(2)
							repeat task.wait()
								topos(CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438).Position).Magnitude <= 10
							wait(1)
							repeat task.wait()
								topos(CFrame.new(-10371.4717, 330.764496, -10131.4199))
							until not _G.AutoElectricClaw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
							wait(1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
							_G.Select_Weapon = "Electric Claw"
							wait(.1)
							_G.Auto_Farm_Level = true
						end
					end
				end
			end
		end
	end)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoDragonTalon or _G.AutoElectricClaw or _G.AutoSharkman or _G.AutoDeathStep or _G.AutoSuperhuman then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Dragon Talon",_G.AutoDragonTalon,function(value)
	_G.AutoDragonTalon = value
end)

spawn(function()
	while wait() do
		if _G.AutoDragonTalon then
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

------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Settings // ")

_G.Method = "Upper"
Main:Dropdown("Select Farm Method", {
	"Behind","Below","Upper"
},function(value)
	_G.Method = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Method == "Behind" then
				MethodFarm = CFrame.new(0,0,_G.DistanceMob)
			elseif _G.Method == "Below" then
				MethodFarm = CFrame.new(0,-_G.DistanceMob,0)
			elseif _G.Method == "Upper" then
				MethodFarm = CFrame.new(0,_G.DistanceMob,0)
			else
				MethodFarm = CFrame.new(0,_G.DistanceMob,0)
			end
		end)
	end
end)

------------------------------------------------------------------------------------------------------------------------------

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

local SelectWeapona = Main:Dropdown("Select Weapon",Weapon,function(value)
	SelectWeapon = value
end)

Main:Seperator(" \\\\ Settings // ")

Main:Toggle("WhiteScreen",_G.WhiteScreen,function(value)
	_G.WhiteScreen = value

	if _G.WhiteScreen == true then
		game:GetService("RunService"):Set3dRenderingEnabled(false)
	elseif _G.WhiteScreen == false then
		game:GetService("RunService"):Set3dRenderingEnabled(true)
	end
end)

_G.DistanceMob = 25
Main:Slider("Farm Distance",1,100,_G.DistanceMob,function(value)
	_G.DistanceMob = value
end)

Main:Toggle("Bring Mob",true,function(value)
	_G.BringNormal = value
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function() CheckQuest()
		pcall(function()
			if _G.BringNormal then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Level and StartMagnet and v.Name == Ms and (v.HumanoidRootPart.Position - PosMon.Position).magnitude <= 225 then
						v.HumanoidRootPart.CFrame = PosMon
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

if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
	game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
end
if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
	game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
end

Main:Toggle('Super Attack (New!!) ',false, function(value)
	_G.FastAttack = value
end)

Main:Toggle('Fast Attack (New!!) ',true, function(value)
	_G.FastAttack1 = value
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
		if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+5 then
			table.insert(Hits,Human.RootPart)
		end
	end
	for i=1,#Characters do local v = Characters[i]
		if v ~= game.Players.LocalPlayer.Character then
			local Human = v:FindFirstChildOfClass("Humanoid")
			if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+5 then
				table.insert(Hits,Human.RootPart)
			end
		end
	end
	return Hits
end

task.spawn(
	function()
		while wait(0) do
			if  _G.FastAttack then
				if SeraphFrame.activeController then
					-- if v.Humanoid.Health > 0 then
					SeraphFrame.activeController.timeToNextAttack = 0
					SeraphFrame.activeController.focusStart = 0
					SeraphFrame.activeController.hitboxMagnitude = 40
					SeraphFrame.activeController.humanoid.AutoRotate = true
					SeraphFrame.activeController.increment = 1 + 1 / 1
					-- end
				end
			end
		end
	end)

function Boost()
	spawn(function()
		game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
	end)
end

function Unboost()
	spawn(function()
		game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
	end)
end

local cdnormal = 2.0
local Animation = Instance.new("Animation")
local CooldownFastAttack = 0
Attack = function()
	local ac = SeraphFrame.activeController
	if ac and ac.equipped then
		task.spawn(
			function()
				if tick() - cdnormal > 5.0 then
					ac:attack()
					cdnormal = tick()
				else
					Animation.AnimationId = ac.anims.basic[2]
					ac.humanoid:LoadAnimation(Animation):Play(2, 2) --ท่าไม่ทำงานแก้เป็น (1,1)
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(120), 2, "")
				end
			end)
	end
end

b = tick()
spawn(function()
	while wait(0) do
		if  _G.FastAttack then
			if b - tick() > 0.75 then
				wait(.2)
				b = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
							Attack()
							wait(0)
							Boost()
						end
					end
				end
			end)
		end
	end
end)

k = tick()
spawn(function()
	while wait(0) do
		if  _G.FastAttack then
			if k - tick() > 0.75 then
				wait(0)
				k = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
							wait(0)
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
							d:Play(15.25, 15.25, 15.25)
							h(i)
							b.play = shared.cpc
							wait(0)
							d:Stop()
						end
					end
				end
			)
		end
	end
)

function GetBladeHit()
	local CombatFrameworkLib = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
	local CmrFwLib = CombatFrameworkLib[2]
	local p13 = CmrFwLib.activeController
	local weapon = p13.blades[1]
	if not weapon then 
		return weapon
	end
	while weapon.Parent ~= game.Players.LocalPlayer.Character do
		weapon = weapon.Parent 
	end
	return weapon
end

function AttackHit()
	local CombatFrameworkLib = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
	local CmrFwLib = CombatFrameworkLib[2]
	local plr = game.Players.LocalPlayer
	local DMG = require(plr.PlayerScripts.CombatFramework.Particle.Damage)
	for i = 1, 1 do
		local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(plr.Character,{plr.Character.HumanoidRootPart},60)
		local cac = {}
		local hash = {}
		for k, v in pairs(bladehit) do
			if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
				table.insert(cac, v.Parent.HumanoidRootPart)
				hash[v.Parent] = true
			end
		end
		bladehit = cac
		if #bladehit > 0 then
			pcall(function()
				CmrFwLib.activeController.timeToNextAttack = 1
				CmrFwLib.activeController.attacking = false
				CmrFwLib.activeController.blocking = false
				CmrFwLib.activeController.timeToNextBlock = 0
				CmrFwLib.activeController.increment = 3
				CmrFwLib.activeController.hitboxMagnitude = 50
				CmrFwLib.activeController.focusStart = 0
				game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetBladeHit()))
				game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "")
			end)
		end
	end
end
spawn(function()
	while wait(.1) do
		if _G.FastAttack1 then
			pcall(function()
				repeat task.wait(0.1)
					AttackHit()
				until not _G.FastAttack1
			end)
		end
	end
end)

local CamShake = require(game.ReplicatedStorage.Util.CameraShaker)
CamShake:Stop()

Main:Toggle("Disable Damage",false,function(value)
	_G.DisableDamage = value
end)

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.DisableDamage then
				game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = false
			else
				game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = true
			end
		end)
	end
end)

Main:Toggle("Invisble Mob",false,function(value)
	_G.inv = value
	while _G.inv do wait()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
				if v.ClassName == "MeshPart" then
					v.Transparency = 1
				end
			end
			for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
				if v.Name == "Head" then
					v.Transparency = 1
				end
			end
			for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
				if v.ClassName == "Accessory" then
					v.Handle.Transparency = 1
				end
			end
			for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
				if v.ClassName == "Decal" then
					v.Transparency = 1
				end
			end
		end)
	end
end)

------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\  Auto Farm Chest // ")

Main:Toggle("Auto Chest Fast",false,function(vu)
	_G.ChestBypass = vu
end)

spawn(function()
	while wait() do
		if _G.ChestBypass then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
					if string.find(v.Name, "Chest") then
						print(v.Name)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
						wait(.15)
					end
				end
				game.Players.LocalPlayer.Character.Head:Destroy()
				for _,v in pairs(game:GetService("Workspace"):GetDescendants()) do
					if string.find(v.Name, "Chest") and v:IsA("TouchTransmitter") then
						firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
						wait()
						firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
					end
				end
			end)
		end
	end
end)

spawn(function()
	while task.wait() do
		if _G.ChestBypass then
			local ohString1 = "SetTeam"
			local ohString2 = "Pirates"
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(ohString1, ohString2)
		end
	end
end)

------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Bosses // ")

local Boss = {}

for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
	if string.find(v.Name, "Boss") then
		if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
		else
			table.insert(Boss, v.Name)
		end
	end
end

local BossName = Main:Dropdown("Select Boss",Boss,function(value)
	_G.Select_Boss = value
end)

Main:Button("Refresh Boss",function()
	BossName:Clear()
	for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
		if string.find(v.Name, "Boss") then
			BossName:Add(v.Name) 
		end
	end
end)

Main:Toggle("Auto Farm Boss",_G.Auto_Farm_Boss,function(value)
	_G.Auto_Farm_Boss = value
	StopTween(_G.Auto_Farm_Boss)
end)

Main:Toggle("Auto Quest Boss",true,function(value)
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
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					else
						topos(CFrameBoss)
					end
				else
					if _G.Auto_Quest_Boss then
						CheckBossQuest()
						if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
						end
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							repeat wait() topos(CFrameQuestBoss) until (CFrameQuestBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Boss
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
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
												game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))									
											else
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
											end
										until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
									end
								end
							else
								topos(CFrameBoss)
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == MsBoss then
									repeat wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										topos(v.HumanoidRootPart.CFrame * MethodFarm)
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))										
									until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						else
							topos(CFrameBoss)
						end
					end
				end
			end)
		end
	end
end)

Main:Toggle("Auto Farm All Boss",_G.Auto_Farm_All_Boss,function(value)
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
								topos(v.HumanoidRootPart.CFrame)
							elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(80,80,80)
								topos(v.HumanoidRootPart.CFrame * MethodFarm)
								game:GetService'VirtualUser':CaptureController()
								game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
							end
						until v.Humanoid.Health <= 0 or _G.Auto_Farm_All_Boss == false or not v.Parent
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Farm_All_Boss or _G.Auto_Farm_Boss then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)


------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Mastery // ")

Main:Toggle("Auto BF Mastery",_G.AutoFarmFruitMastery,function(value)
	_G.AutoFarmFruitMastery = value
	StopTween(_G.AutoFarmFruitMastery)
	if _G.AutoFarmFruitMastery == false then
		UseSkill = false
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoFarmFruitMastery or _G.AutoFarmGunMastery then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

spawn(function()
	while wait() do
		if _G.AutoFarmFruitMastery then
			pcall(function()
				local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
				if not string.find(QuestTitle, NameMon) then
					StartMagnet = false
					UseSkill = false
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
				end
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					StartMasteryFruitStartMagnet = false
					UseSkill = false
					CheckQuest()
					repeat wait()
						topos(CFrameQuest)
					until (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.AutoFarmFruitMastery
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
									if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
										HealthMs = v.Humanoid.MaxHealth * _G.Kill_At/100
										repeat task.wait()
											if v.Humanoid.Health <= HealthMs then
												AutoHaki()
												EquipWeapon(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value)
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												PosMonMasteryFruit = v.HumanoidRootPart.CFrame
												v.Humanoid.WalkSpeed = 0
												v.Head.CanCollide = false
												UseSkill = true
											else
												UseSkill = false
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												PosMonMasteryFruit = v.HumanoidRootPart.CFrame
												v.Humanoid.WalkSpeed = 0
												v.Head.CanCollide = false
											end
											StartMasteryFruitStartMagnet = true
											game:GetService'VirtualUser':CaptureController()
											game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
										until not _G.AutoFarmFruitMastery or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									else
										UseSkill = false
										StartMasteryFruitStartMagnet = false
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
									end
								end
							end
						end
					else
						StartMasteryFruitStartMagnet = false
						UseSkill = false
						local Mob = game:GetService("ReplicatedStorage"):FindFirstChild(Ms)
						if Mob then
							topos(Mob.HumanoidRootPart.CFrame * MethodFarm)
						else
							if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame.Y <= 1 then
								game:GetService("Players").LocalPlayer.Character.Humanoid.Jump = true
								task.wait()
								game:GetService("Players").LocalPlayer.Character.Humanoid.Jump = false
							end
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.AutoFarmFruitMastery and StartMasteryFruitStartMagnet and (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).magnitude <= 225 then
					v.HumanoidRootPart.CFrame = PosMonMasteryFruit
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
		if UseSkill then
			pcall(function()
				CheckQuest()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Backpack[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					end
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then
						if _G.SkillZ then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.SkillX then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.SkillC then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom-Venom") then
						if _G.SkillZ then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.SkillX then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.SkillC then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
						if _G.SkillZ and game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(2, 2.0199999809265, 1) then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.SkillX then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.SkillC then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.SkillV then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						if _G.SkillZ then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.SkillX then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.SkillC then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.SkillV then
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

Main:Toggle("Auto Gun Mastery",_G.AutoFarmGunMastery,function(value)
	_G.AutoFarmGunMastery = value
	StopTween(_G.AutoFarmGunMastery)
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.AutoFarmGunMastery then
				local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
				if not string.find(QuestTitle, NameMon) then
					StartMagnet = false
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
				end
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					StartMasteryGunStartMagnet = false
					CheckQuest()
					topos(CFrameQuest)
					if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						wait(1.2)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, LevelQuest)
					end
				elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					CheckQuest()
					if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
						pcall(function()
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == Ms then
									repeat task.wait()
										if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											HealthMs = v.Humanoid.MaxHealth * _G.Kill_At/100
											if v.Humanoid.Health <= HealthMs then
												EquipWeapon(SelectWeaponGun)
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
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
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
											end
											StartMasteryGunStartMagnet = true
											PosMonMasteryGun = v.HumanoidRootPart.CFrame
										else
											StartMasteryGunStartMagnet = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									until v.Humanoid.Health <= 0 or _G.AutoFarmGunMastery == false or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMasteryGunStartMagnet = false
								end
							end
						end)
					else
						StartMasteryGunStartMagnet = false
						local Mob = game:GetService("ReplicatedStorage"):FindFirstChild(Ms)
						if Mob then
							topos(Mob.HumanoidRootPart.CFrame * MethodFarm)
						else
							if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame.Y <= 1 then
								game:GetService("Players").LocalPlayer.Character.Humanoid.Jump = true
								task.wait()
								game:GetService("Players").LocalPlayer.Character.Humanoid.Jump = false
							end
						end
					end
				end
			end
		end
	end)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.AutoFarmGunMastery and StartMasteryGunStartMagnet and (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).magnitude <= 225 then
					v.HumanoidRootPart.CFrame = PosMonMasteryGun
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

Main:Seperator(" \\\\ Settings Mastery // ")

if not game:GetService("UserInputService").TouchEnabled and not game:GetService("UserInputService").KeyboardEnabled == false then
	_G.Kill_At = 25
	Main:Slider("Kill Health [For Mastery]",1,100,25,function(value)
		_G.Kill_At = value
	end)
else

	_G.Kill_At = 25
	Main:Slider("Kill Health [For Mastery]",1,100,25,function(value)
		_G.Kill_At = value
	end)
end

Main:Toggle("Skill Z",true,function(a)
	_G.SkillZ = a
end)
Main:Toggle("Skill X",true,function(a)
	_G.SkillX = a
end)
Main:Toggle("Skill C",true,function(a)
	_G.SkillC = a
end)
Main:Toggle("Skill V",true,function(a)
	_G.SkillV = a
end)


------------------------------------------------------------------------------------------------------------------------------


Main:Seperator(" \\\\ Elite Hunter // ")

Main:Toggle("Auto Elite Hunter",_G.Auto_Elite_Hunter,function(value)
	_G.Auto_Elite_Hunter = value
	StopTween(_G.Auto_Elite_Hunter)
end)

Main:Toggle("Auto Elite Hunter Hop",_G.Auto_Elite_Hunter_Hop,function(value)
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
											topos(v.HumanoidRootPart.CFrame * MethodFarm)
											game:GetService("VirtualUser"):CaptureController()
											game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
											sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
										until _G.Auto_Elite_Hunter == false or v.Humanoid.Health <= 0 or not v.Parent
									end
								end
							end
						else
							if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
								topos(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
							elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
								topos(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
							elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
								topos(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
							end
						end                    
					end
				else
					if _G.Auto_Elite_Hunter_Hop and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
						hop()
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Elite_Hunter then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

-----------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Auto Farm Cake // ")

local MobKilled = Main:Label("Killed")

spawn(function()
	while wait() do
		pcall(function()
			if string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 88 then
				MobKilled:Set("Defeat : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,41))
			elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 87 then
				MobKilled:Set("Defeat : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,40))
			elseif string.len(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")) == 86 then
				MobKilled:Set("Defeat : "..string.sub(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner"),39,39))
			else
				MobKilled:Set("Boss Is Spawning 🟢")
			end
		end)
	end
end)

Main:Toggle("Auto Spawn Cake Prince",_G.Auto_Spawn_Cake_Prince,function(value)
	_G.Auto_Spawn_Cake_Prince = value
	StopTween(_G.Auto_Spawn_Cake_Prince)
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

Main:Toggle("Auto Farm Cake Prince",_G.Auto_Cake_Prince,function(value)
	_G.Auto_Cake_Prince = value
	StopTween(_G.Auto_Cake_Prince)
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.Auto_Cake_Prince and StartCakeStartMagnet and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and (v.HumanoidRootPart.Position - POSCAKE.Position).magnitude <= 225 then
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
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until _G.Auto_Cake_Prince == false or not v.Parent or v.Humanoid.Health <= 0
							end    
						end    
					else
						topos(CFrame.new(-2009.2802734375, 4532.97216796875, -14937.3076171875)) 
					end
				else
					if game.Workspace.Enemies:FindFirstChild("Baking Staff [Lv. 2250]") or game.Workspace.Enemies:FindFirstChild("Head Baker [Lv. 2275]") or game.Workspace.Enemies:FindFirstChild("Cake Guard [Lv. 2225]") or game.Workspace.Enemies:FindFirstChild("Cookie Crafter [Lv. 2200]")  then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do  
							if (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") and v.Humanoid.Health > 0 then
								repeat wait()
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									StartCakeStartMagnet = true
									v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
									POSCAKE = v.HumanoidRootPart.CFrame
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until _G.Auto_Cake_Prince == false or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					else
						StartCakeStartMagnet = false
						topos(CFrame.new(-1820.0634765625, 210.74781799316406, -12297.49609375))
					end
				end
			end)
		end
	end
end)	


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Cake_Prince then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Auto Farm Bone // ")

Main:Toggle("Auto Farm Bone",_G.Auto_Farm_Bone,function(value)
	_G.Auto_Farm_Bone = value
	StopTween(_G.Auto_Farm_Bone)
end)

spawn(function()
	while wait() do 
		if _G.Auto_Farm_Bone and World3 then
			pcall(function()
				if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Domenic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
							if v.Humanoid.Health > 0 then
								repeat task.wait()
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									v.HumanoidRootPart.CanCollide = false
									v.Head.CanCollide = false 
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService("VirtualUser"):CaptureController()
									game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
									PosMonBone = v.HumanoidRootPart.CFrame
									StartMagnetBoneMon = true
								until not _G.Auto_Farm_Bone or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					end
				else
					StartMagnetBoneMon = false
					topos(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))                    
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.Auto_Farm_Bone and StartMagnetBoneMon and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" or v.Name == "Head Baker [Lv. 2275]") and (v.HumanoidRootPart.Position - PosMonBone.Position).magnitude <= 350 then
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

Main:Toggle("Auto Random Surprise",_G.Auto_Random_Bone,function(value)
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

------------------------------------------------------------------------------------------------------------------------------

if World3 then
	Main:Seperator(" \\\\ Mirage Island // ")

	local Mirragecheck = Main:Label('...')

	spawn(function()
		pcall(function()
			while wait() do
				if game.Workspace._WorldOrigin.Locations:FindFirstChild('Mirage Island') then
					Mirragecheck:Set('  Mirage Island is Spawning 🟢')
				else
					Mirragecheck:Set('  Mirage Island Not Found ❌')
				end
			end
		end)
	end)

	Main:Toggle("Auto Mirage Island",false,function(value)
		_G.Mirage = value
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if _G.Mirage then
					if game:GetService("Workspace").Map:FindFirstChild("MysticIsland") then
						topos(workspace.Map.MysticIsland.PrimaryPart.CFrame * CFrame.new(0,250,0))
					else
						game.StarterGui:SetCore("SendNotification", {
							Title = ""; -- the title (ofc)
							Text = "Mirage not Found!"; -- what the text says (ofc)
							Icon = "rbxassetid://"; -- the image if u want. 
							Duration = 3; -- how long the notification should in secounds
						})
						if _G.MirageHop then
							wait(6)
							Hop()
						end          
					end
				end
			end
		end)
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			if _G.Mirage then
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
					setfflag("HumanoidParallelRemoveNoPhysics", "False")
					setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
					game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
				end
			end
		end)
	end)

	Main:Toggle("Auto Mirage Island Hop",false,function(value)
		_G.Mystichop = value
	end)

	Main:Seperator(" \\\\ Race V4 // ")

	Main:Button("Teleport To Timple Of Time",function()
		Game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(28286.35546875, 14895.3017578125, 102.62469482421875)
	end)

	Main:Button("Teleport To Lever Pull",function()
		topos(CFrame.new(28575.181640625, 14936.6279296875, 72.31636810302734))
	end)

	Main:Button("Teleport To Acient One (Must Be in Temple Of Time!)",function()
		topos(CFrame.new(28981.552734375, 14888.4267578125, -120.245849609375))
	end)

	Main:Toggle("Teleport To Gear ",function(value)
		topos(game:GetService("Workspace").Map.MysticIsland:FindFirstChildOfClass("MeshPart").CFrame)
	end)

	Main:Seperator(" \\\\ Misc // ")

	Main:Toggle("Auto Bartilo Quest",_G.Auto_Bartilo_Quest,function(value)
		_G.Auto_Bartilo_Quest = value
		StopTween(_G.Auto_Bartilo_Quest)
	end)
end


------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Swan Glasses // ")

Main:Toggle("Auto Swan Glasses",_G.Auto_Swan_Glasses,function(value)
	_G.Auto_Swan_Glasses = value
	StopTween(_G.Auto_Swan_Glasses)
end)


Main:Toggle("Auto Swan Glasses Hop",_G.Auto_Swan_Glasses_Hop,function(value)
	_G.Auto_Swan_Glasses_Hop = value
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Swan_Glasses then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
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
								topos(v.HumanoidRootPart.CFrame * MethodFarm)
								game:GetService'VirtualUser':CaptureController()
								game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
							until not _G.Auto_Swan_Glasses or v.Humanoid.Health <= 0 or not v.Parent
						end
					end
				else
					topos(CFrame.new(2289.47900390625, 15.152046203613281, 739.512939453125))
				end
			else
				if _G.Auto_Swan_Glasses_Hop then
					hop()
				end
			end
		end)
	end
end)


------------------------------------------------------------------------------------------------------------------------------


Main:Seperator(" \\\\ Serpent Bow // ")

Main:Toggle("Auto Serpent Bow",_G.Auto_Serpent_Bow,function(value)
	_G.Auto_Serpent_Bow = value
	StopTween(_G.Auto_Serpent_Bow)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Serpent_Bow then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Serpent Bow Hop",_G.Auto_Serpent_Bow_Hop,function(value)
	_G.Auto_Serpent_Bow_Hop = value
	StopTween(_G.Auto_Serpent_Bow_Hop)
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
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until _G.Auto_Serpent_Bow or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					else
						topos(CFrame.new(5764.1826171875, 700.425537109375, 141.11996459960938))
					end
				else
					if _G.Auto_Serpent_Bow_Hop then
						hop()
					end
				end
			end)
		end
	end
end)


------------------------------------------------------------------------------------------------------------------------------


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

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoFarmMaterial then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Seperator(" \\\\ Materials //")

local SelectMaterial = Main:Dropdown("Select Material",MaterialMethod,function(value)
	_G.SelectMaterial = value
end)

Main:Toggle("Auto Farm Selected Material",_G.AutoFarmMaterial,function(t)
	_G.AutoFarmMaterial = t
	StopTween(_G.AutoFarmMaterial)
end)

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
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									MatMon = v.Name
									MatPos = v.HumanoidRootPart.CFrame
								until not _G.AutoFarmMaterial or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					end
				else
					topos(MPos)
				end
			end
		end)
	end
end)

spawn(function()
	while task.wait() do
		if _G.BringNormal and _G.AutoFarmMaterial then
			pcall(function()
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Name == MatMon and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 225 then
						v.Humanoid.WalkSpeed = 0
						v.HumanoidRootPart.Size = Vector3.new(60,60,60)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						v.HumanoidRootPart.CFrame = MatPos
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						v.Humanoid:ChangeState(11)
						v.Humanoid:ChangeState(14)
						sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
					end
				end
			end)
		end
	end
end)

------------------------------------------------------------------------------------------------------------------------------


Main:Seperator(" \\\\ AutoLaw // ")

Main:Toggle("AutoLaw",_G.Auto_Kill_Law,function(value)
	_G.Auto_Kill_Law = value
	StopTween(_G.Auto_Kill_Law)
end)

Main:Toggle("AutoLawd Hop", _G.Auto_Kill_LawHop,function(value)
	_G.Auto_Kill_LawHop = value
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Kill_Law then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

spawn(function()
	while wait() do
		if _G.Auto_Kill_Law then
			pcall(function()
				if not game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") then
						fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
					else
						if _G.AutoBuyBossLawChip then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Microchip","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Microchip","2")
						end
					end
				else
					if game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Order [Lv. 1250] [Raid Boss]" then
									repeat task.wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										topos(v.HumanoidRootPart.CFrame * CFrame.new(0,35,0))
										v.HumanoidRootPart.CanCollide = false
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									until v.Humanoid.Health <= 0 or not _G.AutoBossLaw or not v.Parent
								end
							end
						else 
							if game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
								topos(game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]").HumanoidRootPart.CFrame * CFrame.new(0,35,0))
							end
						end
					end
				end
			end)
		end
	end
end)

Main:Button("Buy Microchip Law",function()
	local args = {
		[1] = "BlackbeardReward",
		[2] = "Microchip",
		[3] = "2"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Main:Button("Start Raid Law",function()
	fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
end)


Main:Seperator(" \\\\  Observation // ")

local ObservationLevel = Main:Label("")

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

Main:Toggle("Auto Farm Observation",_G.AutoObservation,function(value)
	_G.AutoObservation = value
	StopTween(_G.AutoObservation)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoObservation then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
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

Main:Toggle("Auto Farm Observation Hop",_G.AutoObservation_Hop,function(value)
	_G.AutoObservation_Hop = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.AutoObservation then
				if game:GetService("Players").LocalPlayer.VisionRadius.Value >= 3000 then
					local NotificationHolder = loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Module.Lua"))()
					local Notification = loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Client.Lua"))()
					wait(1)
					Notification:Notify(
						{Title = "", Description = "You Have Max Observation"},
						{OutlineColor = Color3.fromRGB(80, 80, 80),Time = 5, Type = "option"},
						{Image = "http://www.roblox.com/asset/?id=", ImageColor = Color3.fromRGB(255, 84, 84), Callback = function(State) print(tostring(State)) end}
					)
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
							topos(CFrame.new(-3184.662353515625, 58.35300064086914, -9662.85546875))
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
							topos(CFrame.new(5533.29785, 88.1079102, 4852.3916))
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
							topos(CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789))
						end
					end
				end
			end
		end
	end)
end)
------------------------------------------------------------------------------------------------------------------------------


Main:Seperator(" \\\\ Legendary Sword // ")

Main:Toggle("Auto Buy Legendary Sword",_G.AutoBuyLegendarySword,function(Value)
	_G.AutoBuyLegendarySword = Value
end)
spawn(function()
	while wait() do
		if _G.AutoBuyLegendarySword then
			pcall(function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","1")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","2")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","3")
				if _G.AutoBuyLegendarySword_Hop and _G.AutoBuyLegendarySword and World2 then
					wait(10)
					Hop()
				end
			end)
		end 
	end
end)
Main:Toggle("Auto Buy Legendary Sword Hop",_G.AutoBuyLegendarySword_Hop,function(Value)
	_G.AutoBuyLegendarySword_Hop = Value
end)




Main:Seperator(" \\\\ Auto Saber // ")

Main:Toggle("Auto Saber",_G.AutoSaber,function(value)
	_G.AutoSaber = value
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoSaber then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Saber Hop",_G.AutoSaberHop,function(value)
	_G.AutoSaberHop = value
end)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoSaber and game.Players.LocalPlayer.Data.Level.Value >= 200 and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Saber") and not game.Players.LocalPlayer.Character:FindFirstChild("Saber") then
				if game:GetService("Workspace").Map.Jungle.Final.Part.Transparency == 0 then
					if game:GetService("Workspace").Map.Jungle.QuestPlates.Door.Transparency == 0 then
						if (CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
							topos(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate1.Button.CFrame
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate2.Button.CFrame
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate3.Button.CFrame
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate4.Button.CFrame
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate5.Button.CFrame
							wait(1) 
						else
							topos(CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279))
						end
					else
						if game:GetService("Workspace").Map.Desert.Burn.Part.Transparency == 0 then
							if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Torch") then
								EquipWeapon("Torch")
								topos(CFrame.new(1114.61475, 5.04679728, 4350.22803, -0.648466587, -1.28799094e-09, 0.761243105, -5.70652914e-10, 1, 1.20584542e-09, -0.761243105, 3.47544882e-10, -0.648466587))
							else
								topos(CFrame.new(-1610.00757, 11.5049858, 164.001587, 0.984807551, -0.167722285, -0.0449818149, 0.17364943, 0.951244235, 0.254912198, 3.42372805e-05, -0.258850515, 0.965917408))                 
							end
						else
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
								wait(0.5)
								EquipWeapon("Cup")
								wait(0.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","FillCup",game:GetService("Players").LocalPlayer.Character.Cup)
								wait(0)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") 
							else
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == nil then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
								elseif  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
									if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
										topos(CFrame.new(-2967.59521, -4.91089821, 5328.70703, 0.342208564, -0.0227849055, 0.939347804, 0.0251603816, 0.999569714, 0.0150796166, -0.939287126, 0.0184739735, 0.342634559))
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Mob Leader [Lv. 120] [Boss]" then
												repeat wait()
													StartMagnet = true
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													topos(v.HumanoidRootPart.CFrame * MethodFarm)
													PosMon = v.HumanoidRootPart.CFrame
													game:GetService'VirtualUser':CaptureController()
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
													v.HumanoidRootPart.Size = Vector3.new(60,60,60)
													v.Humanoid.JumpPower = 0
													v.Humanoid.WalkSpeed = 0
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid:ChangeState(11)
												until v.Humanoid.Health <= 0 or _G.AutoSaber == false
											end
										end
									end
								elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
									wait(0.5)
									EquipWeapon("Relic")
									wait(0.5)
									topos(CFrame.new(-1404.91504, 29.9773273, 3.80598116, 0.876514494, 5.66906877e-09, 0.481375456, 2.53851997e-08, 1, -5.79995607e-08, -0.481375456, 6.30572643e-08, 0.876514494))
								end
							end
						end
					end
				else
					if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
						topos(CFrame.new(-1401.85046, 29.9773273, 8.81916237, 0.85820812, 8.76083845e-08, 0.513301849, -8.55007443e-08, 1, -2.77243419e-08, -0.513301849, -2.00944328e-08, 0.85820812))
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Saber Expert [Lv. 200] [Boss]" then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									PosMon = v.HumanoidRootPart.CFrame
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
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



Main:Seperator(" \\\\ Tushita // ")

Main:Toggle("Auto Tushita Sword",_G.Autotushita,function(value)
	_G.Autotushita = value
	StopTween(_G.Autotushita)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Autotushita then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

spawn(function()
	while wait() do
		if _G.Autotushita then
			if game:GetService("Workspace").Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if v.Name == ("Longma [Lv. 2000] [Boss]" or v.Name == "Longma [Lv. 2000] [Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
						repeat wait()
							StartMagnet = true
							AutoHaki()
							if not game.Players.LocalPlayer.Character:FindFirstChild(_G.Select_Weapon) then
								wait()
								EquipWeapon(_G.Select_Weapon)
							end
							PosMon = v.HumanoidRootPart.CFrame
							game:GetService'VirtualUser':CaptureController()
							game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
							v.HumanoidRootPart.Size = Vector3.new(60,60,60)
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.Humanoid:ChangeState(11)
							topos(v.HumanoidRootPart.CFrame * MethodFarm)
						until not _G.Autotushita or not v.Parent or v.Humanoid.Health <= 0
						StartMagnet = false
					end
				end
			else
				topos(CFrame.new(-10238.875976563, 389.7912902832, -9549.7939453125))
			end
		end
	end
end)

Main:Toggle("Auto Holy Torch",_G.AutoHolyTorch,function(value)
	_G.AutoHolyTorch = value
	StopTween(_G.AutoHolyTorch)
end)

spawn(function()
	while wait() do
		if _G.AutoHolyTorch then
			pcall(function()
				wait(1)
				topos(CFrame.new(-10752, 417, -9366))
				wait(1)
				topos(CFrame.new(-11672, 334, -9474))
				wait(1)
				topos(CFrame.new(-12132, 521, -10655))
				wait(1)
				topos(CFrame.new(-13336, 486, -6985))
				wait(1)
				topos(CFrame.new(-13489, 332, -7925))
			end)
		end
	end
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoHolyTorch then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Seperator(" \\\\ Trident // ")

Main:Toggle("Auto Dragon Trident",_G.Auto_Dragon_Trident,function(value)
	_G.Auto_Dragon_Trident = value
	StopTween(_G.Auto_Dragon_Trident)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Dragon_Trident then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Dragon Trident Hop",_G.Auto_Dragon_Trident_Hop,function(value)
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
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until _G.Auto_Dragon_Trident or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					else
						topos(CFrame.new(-3914.830322265625, 123.29389190673828, -11516.8642578125))
					end
				else
					if _G.Auto_Dragon_Trident_Hop then
						hop()
					end
				end
			end)
		end
	end
end)



Main:Seperator(" \\\\ Rengoku // ")

Main:Toggle("Auto Rengoku",_G.Auto_Rengoku,function(value)
	_G.Auto_Rengoku = value
	StopTween(_G.Auto_Rengoku)
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.Auto_Rengoku and StartRengokuStartMagnet and (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and (v.HumanoidRootPart.Position - RengokuMon.Position).magnitude <= 225 then
					v.HumanoidRootPart.CFrame = RengokuMon
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
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Rengoku then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

spawn(function()
	while wait() do
		if _G.Auto_Rengoku then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hidden Key") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hidden Key") then
					EquipWeapon("Hidden Key")
					topos(CFrame.new(6571.1201171875, 299.23028564453, -6967.841796875))
				elseif game:GetService("Workspace").Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") or game:GetService("Workspace").Enemies:FindFirstChild("Arctic Warrior [Lv. 1350]") then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and v.Humanoid.Health > 0 then
							repeat wait()
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								RengokuMon = v.HumanoidRootPart.CFrame
								topos(v.HumanoidRootPart.CFrame * MethodFarm)
								game:GetService'VirtualUser':CaptureController()
								game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								StartRengokuStartMagnet = true
							until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hidden Key") or _G.Auto_Rengoku == false or not v.Parent or v.Humanoid.Health <= 0
							StartRengokuStartMagnet = false
						end
					end
				else
					StartRengokuStartMagnet = false
					topos(CFrame.new(5439.716796875, 84.420944213867, -6715.1635742188))
				end
			end)
		end
	end
end)

if _G.Auto_Rengoku_Hop then
	Hop()
end

Main:Toggle("Auto Rengoku Hop",_G.Auto_Rengoku_Hop,function(value)
	_G.Auto_Rengoku_Hop = value
end)



Main:Seperator(" \\\\ Buddy Sword // ")

local Cake_Queen_Status = Main:Label("Status : N/Q")

spawn(function()
	while wait() do
		pcall(function()
			if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
				Cake_Queen_Status:Set("Status : Spawned")	
			else
				Cake_Queen_Status:Set("Status : Not Spawned")	
			end
		end)
	end
end)

Main:Toggle("Auto Buddy Sword",_G.AutoBudySword,function(value)
	_G.AutoBudySword = value
	StopTween(_G.AutoBudySword)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoBudySword then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Buddy Sword Hop",_G.AutoBudySwordHop,function(value)
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
									v.HumanoidRootPart.Size = Vector3.new(55,55,55)
									topos(v.HumanoidRootPart.CFrame * MethodFarm)                         
									game:GetService("VirtualUser"):CaptureController()
									game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
									sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
								until not _G.AutoBudySword or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					end
				else
					if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						topos(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]").HumanoidRootPart.CFrame * MethodFarm)
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



Main:Seperator(" \\\\ Hallow Scythe // ")

local Hallow_Status = Main:Label("Status : N/Q")

spawn(function()
	while wait() do
		pcall(function()
			if game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
				Hallow_Status:Set("Status : Spawned")	
			else
				Hallow_Status:Set("Status : Not Spawned")	
			end
		end)
	end
end)

Main:Toggle("Auto Hallow Scythe",_G.AutoFarmBossHallow,function(value)
	_G.AutoFarmBossHallow = value
	StopTween(_G.AutoFarmBossHallow)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoFarmBossHallow then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Main:Toggle("Auto Hallow Scythe Hop",_G.AutoFarmBossHallowHop,function(value)
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
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								topos(v.HumanoidRootPart.CFrame * MethodFarm)
								game:GetService("VirtualUser"):CaptureController()
								game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
								v.HumanoidRootPart.Transparency = 1
								sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
							until v.Humanoid.Health <= 0 or _G.AutoFarmBossHallow == false
						end
					end
				elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Hallow Essence") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hallow Essence") then
					repeat topos(CFrame.new(-8932.322265625, 146.83154296875, 6062.55078125)) wait() until (CFrame.new(-8932.322265625, 146.83154296875, 6062.55078125).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 8                        
				else
					if game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						topos(game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]").HumanoidRootPart.CFrame * CFrame.new(5,10,7))
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



Main:Seperator(" \\\\ Dark Dagger // ")

local rip_indra_Status = Main:Label("Status : N/Q")

spawn(function()
	while wait() do
		pcall(function()
			if game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
				rip_indra_Status:Set("Status : Spawned")	
			else
				rip_indra_Status:Set("Status : Not Spawned")	
			end
		end)
	end
end)

Main:Toggle("Auto Dark Dagger",_G.AutoDarkDagger,function(value)
	_G.AutoDarkDagger = value
	StopTween(_G.AutoDarkDagger)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoDarkDagger then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
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
									v.HumanoidRootPart.Size = Vector3.new(50,50,50)
									topos(v.HumanoidRootPart.CFrame * MethodFarm)
									game:GetService("VirtualUser"):CaptureController()
									game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670),workspace.CurrentCamera.CFrame)
								end)
							until _G.AutoDarkDagger == false or v.Humanoid.Health <= 0
						end
					end
				end
			end
		end
	end)
end)

Main:Toggle("Auto Dark Dagger Hop",_G.AutoDarkDagger_Hop,function(value)
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


------------------------------------------------------------------------------------------------------------------------------

Main:Seperator(" \\\\ Other // ")

Main:Toggle("Auto Evo Race [V2]",_G.Auto_Evo_Race_V2,function(value)
	_G.Auto_Evo_Race_V2 = value
	StopTween(_G.Auto_Evo_Race_V2)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Evo_Race_V2 then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
				if _G.Auto_Evo_Race_V2 and StartEvoStartMagnet and v.Name == "Swan Pirate [Lv. 775]" and (v.HumanoidRootPart.Position - PosMonEvo.Position).magnitude <= 225 then
					v.HumanoidRootPart.CFrame = PosMonEvo
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
	pcall(function()
		while wait() do
			if _G.Auto_Evo_Race_V2 then
				if not game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 0 then
						topos(CFrame.new(-2779.83521, 72.9661407, -3574.02002, -0.730484903, 6.39014104e-08, -0.68292886, 3.59963224e-08, 1, 5.50667032e-08, 0.68292886, 1.56424669e-08, -0.730484903))
						if (Vector3.new(-2779.83521, 72.9661407, -3574.02002) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
							wait(1.3)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 1 then
						pcall(function()
							if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 1") then
								topos(game:GetService("Workspace").Flower1.CFrame)
							elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 2") then
								topos(game:GetService("Workspace").Flower2.CFrame)
							elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 3") then
								if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Swan Pirate [Lv. 775]" then
											repeat wait()
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												topos(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
												PosMonEvo = v.HumanoidRootPart.CFrame
												StartEvoStartMagnet = true
											until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") or not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Evo_Race_V2 == false
											StartEvoStartMagnet = false
										end
									end
								else
									StartEvoStartMagnet = false
									topos(CFrame.new(980.0985107421875, 121.331298828125, 1287.2093505859375))
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


Main:Toggle("Auto Buy Enchancement",_G.Auto_Buy_Enchancement,function(value)
	_G.Auto_Buy_Enchancement = value
	StopTween(_G.Auto_Buy_Enchancement)
end)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Enchancement then
			local args = {
				[1] = "ColorsDealer",
				[2] = "2"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end 
	end
end)

Main:Toggle("Auto Observation Haki v2",_G.AutoObservationv2,function(value)
	_G.AutoObservationv2 = value
	StopTween(_G.AutoObservationv2)
end)

spawn(function()
	while wait() do
		if _G.AutoObservationv2 then
			if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Start") == 0 then
				topos(CFrame.new(-10920.125, 624.20275878906, -10266.995117188))
				wait(1.1)
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Buy")
			else
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fruit Bowl") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fruit Bowl") then
					topos(CFrame.new(-10920.125, 624.20275878906, -10266.995117188))
					wait(1.1)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Start")
				else
					if game:GetService("Workspace").AppleSpawner:FindFirstChild("Apple") then
						game:GetService("Workspace").AppleSpawner:FindFirstChild("Apple").Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
					else
						if game:GetService("Workspace").BananaSpawne:FindFirstChild("Banana") then
							game:GetService("Workspace").BananaSpawne:FindFirstChild("Banana").Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
						else
							if game:GetService("Workspace").PineappleSpawner:FindFirstChild("Pineapple") then
								game:GetService("Workspace").PineappleSpawner:FindFirstChild("Pineapple").Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
							end
						end
					end
					if (game:GetService("Players").LocalPlayer.Character:FindFirstChild("Apple") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Apple")) and (game:GetService("Players").LocalPlayer.Character:FindFirstChild("Pineapple") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Pineapple")) and (game:GetService("Players").LocalPlayer.Character:FindFirstChild("Banana") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Banana")) then
						topos(CFrame.new(-12444.78515625, 332.40396118164, -7673.1806640625)) 
						wait(1.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
						wait(.5)
					end
				end
			end
		end
	end
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.AutoObservationv2 then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)



------------------------------------------------------------------------------------------------------------------------------

Combat:Seperator(" \\\\ Kill Player // ")

Playerslist = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do
	table.insert(Playerslist,v.Name)
end

local SelectedPly = Combat:Dropdown("Select Players",Playerslist,function(value)
	_G.Select_Player = value
end)

Combat:Button("Refresh Player",function()
	Playerslist = {}
	SelectedPly:Clear()
	for i,v in pairs(game:GetService("Players"):GetChildren()) do  
		SelectedPly:Add(v.Name)
	end
end)

Combat:Toggle("Spectate Player",_G.Spectate_Player,function(value)
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

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		if UseGunKillPlayer then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
					if v.Name == _G.Select_Player then
						local args = {
							[1] = v.HumanoidRootPart.Position,
							[2] = v.HumanoidRootPart
						}
						game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
					end
				end
			end)
		end
	end)
end)

Combat:Toggle("Teleport to Player",_G.Teleport_to_Player,function(value)
	_G.Teleport_to_Player = value
	StopTween(_G.Teleport_to_Player)
end)


spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

spawn(function()
	while wait() do
		if _G.Teleport_to_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					topos(game.Players[_G.Select_Player].Character.HumanoidRootPart.CFrame)
				end
			end)
		end
	end
end)

Combat:Toggle("Auto Kill Player",_G.Auto_Kill_Player_Melee,function(value)
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
									topos(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0))
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									topos(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0))
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

Combat:Toggle("Auto Kill Player [Gun]",_G.Auto_Kill_Player_Gun,function(value)
	_G.Auto_Kill_Player_Gun = value
	StopTween(_G.Auto_Kill_Player_Gun)
end)

spawn(function()
	while wait() do
		for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if v:IsA("Tool") then
				if v:FindFirstChild("RemoteFunctionShoot") then 
					SelectToolWeaponGun = v.Name
				end
			end
		end
	end
end)

spawn(function()
	while wait() do 
		pcall(function()
			if _G.Auto_Kill_Player_Gun then
				if game.Players:FindFirstChild(_G.Select_Player) then
					for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if v.Name == _G.Select_Player and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									topos(v.HumanoidRootPart.CFrame)
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									AutoHaki()
									EquipWeapon(SelectToolWeaponGun)
									UseGunKillPlayer = true
									game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].Cooldown.Value = 0
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.HumanoidRootPart.Transparency = 0.7
									topos(v.HumanoidRootPart.CFrame * CFrame.new(0,50,-10))
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								end
							until game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid.Health <= 0 or not _G.Auto_Kill_Player_Gun or not game.Players:FindFirstChild(_G.Select_Player)
						end
					end
				end
			else
				UseGunKillPlayer = false
			end
		end)
	end
end)

Combat:Seperator(" \\\\ PvP // ")

Combat:Toggle("Enabled PvP ",false,function(value)
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

Combat:Toggle("Safe Mode ",false,function(value)
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

Combat:Button("Respawn",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","") 
	wait()
end)

------------------------------------------------------------------------------------------------------------------------------

Stats:Seperator(" \\\\ Auto Stats // ")

local Pointstat = Stats:Label("Stat Points")

spawn(function()
	while wait() do
		pcall(function()
			Pointstat:Set("Stat Points : "..tostring(game:GetService("Players")["LocalPlayer"].Data.Points.Value))
		end)
	end
end)

Stats:Toggle("Auto Melee",_G.Auto_Melee,function(value)
	_G.Auto_Melee = value
end)

Stats:Toggle("Auto Defense",_G.Auto_Defense,function(value)
	_G.Auto_Defense = value
end)

Stats:Toggle("Auto Sword",_G.Auto_Sword,function(value)
	_G.Auto_Sword = value
end)

Stats:Toggle("Auto Gun",_G.Auto_Gun,function(value)
	_G.Auto_Gun = value
end)

Stats:Toggle("Auto Devil Fruits",_G.Auto_DevilFruit,function(value)
	_G.Auto_DevilFruit = value
end)

_G.PointStats = 1
Stats:Slider("Select Point",1,100,1,function(value)
	_G.PointStats = value
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

------------------------------------------------------------------------------------------------------------------------------

Stats:Seperator(" \\\\ Fake // ")

Stats:Toggle("Enabled Fake",_G.EnabledStat,function(value)
	_G.EnabledStat = value
end)

Stats:Textbox("Level","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Level.Value = tonumber(value)
	end
end)

Stats:Textbox("Exp ","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Exp.Value = tonumber(value)
	end
end)

Stats:Textbox("Beli","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Beli.Value = tonumber(value)
	end
end)

Stats:Textbox("Fragments","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["Localplayer"].Data.Fragments.Value = tonumber(value)
	end
end)

Stats:Textbox("Melee","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value = tonumber(value)
	end
end)

Stats:Textbox("Defense","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Defense.Level.Value = tonumber(value)
	end
end)

Stats:Textbox("Sword","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Sword.Level.Value = tonumber(value)
	end
end)

Stats:Textbox("Gun","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats.Gun.Level.Value = tonumber(value)
	end
end)
Stats:Textbox("Fruit","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].Data.Stats["Demon Fruit"].Level.Value = tonumber(value)
	end
end)

Stats:Textbox("Bounty","",true,function(value)
	if _G.EnabledStat then
		game:GetService("Players")["LocalPlayer"].leaderstats["Bounty/Honor"].Value = tonumber(value)
	end
end)

------------------------------------------------------------------------------------------------------------------------------

Teleport:Seperator(" \\\\ Island // ")

Teleport:Seperator("World - Monster")

Teleport:Button("Teleport To Old World",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end)

Teleport:Button("Teleport To Second Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
end)

Teleport:Button("Teleport To Third Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end)


if World1 then
	Teleport:Dropdown("Select Island",{
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
	},function(value)
		_G.SelectIsland = value
	end)
end

if World2 then
	Teleport:Dropdown("Select Island",{
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
	},function(value)
		_G.SelectIsland = value
	end)
end

if World3 then
	Teleport:Dropdown("Select Island",{
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
		"Sea to Treats New"
	},function(value)
		_G.SelectIsland = value
	end)
end

Teleport:Toggle("Teleport",false,function(value)
	_G.TeleportIsland = value
	if _G.TeleportIsland == true then
		repeat wait()
			if _G.SelectIsland == "WindMill" then
				topos(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
			elseif _G.SelectIsland == "Marine" then
				topos(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
			elseif _G.SelectIsland == "Middle Town" then
				topos(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
			elseif _G.SelectIsland == "Jungle" then
				topos(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
			elseif _G.SelectIsland == "Pirate Village" then
				topos(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
			elseif _G.SelectIsland == "Desert" then
				topos(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
			elseif _G.SelectIsland == "Snow Island" then
				topos(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
			elseif _G.SelectIsland == "MarineFord" then
				topos(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
			elseif _G.SelectIsland == "Colosseum" then
				topos( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
			elseif _G.SelectIsland == "Sky Island 1" then
				topos(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
			elseif _G.SelectIsland == "Sky Island 2" then  
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			elseif _G.SelectIsland == "Sky Island 3" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			elseif _G.SelectIsland == "Prison" then
				topos( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
			elseif _G.SelectIsland == "Magma Village" then
				topos(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
			elseif _G.SelectIsland == "Under Water Island" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			elseif _G.SelectIsland == "Fountain City" then
				topos(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
			elseif _G.SelectIsland == "Shank Room" then
				topos(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
			elseif _G.SelectIsland == "Mob Island" then
				topos(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
			elseif _G.SelectIsland == "The Cafe" then
				topos(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
			elseif _G.SelectIsland == "Frist Spot" then
				topos(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
			elseif _G.SelectIsland == "Dark Area" then
				topos(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
			elseif _G.SelectIsland == "Flamingo Mansion" then
				topos(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
			elseif _G.SelectIsland == "Flamingo Room" then
				topos(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
			elseif _G.SelectIsland == "Green Zone" then
				topos( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
			elseif _G.SelectIsland == "Factory" then
				topos(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
			elseif _G.SelectIsland == "Colossuim" then
				topos( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
			elseif _G.SelectIsland == "Zombie Island" then
				topos(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
			elseif _G.SelectIsland == "Two Snow Mountain" then
				topos(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
			elseif _G.SelectIsland == "Punk Hazard" then
				topos(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
			elseif _G.SelectIsland == "Cursed Ship" then
				topos(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
			elseif _G.SelectIsland == "Ice Castle" then
				topos(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
			elseif _G.SelectIsland == "Forgotten Island" then
				topos(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
			elseif _G.SelectIsland == "Ussop Island" then
				topos(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
			elseif _G.SelectIsland == "Mini Sky Island" then
				topos(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
			elseif _G.SelectIsland == "Great Tree" then
				topos(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
			elseif _G.SelectIsland == "Castle On The Sea" then
				topos(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
			elseif _G.SelectIsland == "MiniSky" then
				topos(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
			elseif _G.SelectIsland == "Port Town" then
				topos(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
			elseif _G.SelectIsland == "Hydra Island" then
				topos(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
			elseif _G.SelectIsland == "Floating Turtle" then
				topos(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
			elseif _G.SelectIsland == "Mansion" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
			elseif _G.SelectIsland == "Haunted Castle" then
				topos(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
			elseif _G.SelectIsland == "Ice Cream Island" then
				topos(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
			elseif _G.SelectIsland == "Peanut Island" then
				topos(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
			elseif _G.SelectIsland == "Cake Island" then
				topos(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
			elseif _G.SelectIsland == "Sea to Treats New" then
				topos(CFrame.new(-1141.0223388671875, 47.25519561767578, -14204.609375))	
			end
		until not _G.TeleportIsland
	end
	StopTween(_G.TeleportIsland)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.TeleportIsland then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

------------------------------------------------------------------------------------------------------------------------------

Dungeon:Seperator(" \\\\ Dungeon //")

Dungeon:Toggle("Auto Farm Dungeon ",_G.Auto_Raid,function(value)
	_G.Auto_Raid = value
	StopTween(_G.Auto_Raid)
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Auto_Raid or _G.Auto_Next then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,30,0))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,30,0))
					end
				end
			end
		end
	end)
end)

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		if _G.Auto_Raid or Auto_Next then
			if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)

Dungeon:Toggle("Kill Aura ",_G.Kill,function(value)
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

Dungeon:Toggle("Auto Next Island ",_G.Auto_Next,function(value)
	_G.Auto_Next = value
	StopTween(_G.Auto_Next)
end)

Dungeon:Dropdown("Select Chips",{"Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird: Phoenix","Dough"},function(value)
	_G.SelectChip = value
end)

Dungeon:Toggle("Auto Select Dungeon",_G.AutoSelectDungeon,function(value)
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

Dungeon:Toggle("Auto Buy Chip ",_G.AutoBuyChip,function(value)
	_G.AutoBuyChip = value
end)

Dungeon:Toggle("Auto Start Raid ",_G.Auto_StartRaid,function(value)
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

------------------------------------------------------------------------------------------------------------------------------

DevilFruit:Seperator(" \\\\ DevilFruit // ")

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

_G.SelectFruit = ""
DevilFruit:Dropdown("Select Fruits Sniper",FruitList,function(value)
	_G.SelectFruit = value
end)

DevilFruit:Toggle("Auto Buy Fruit Sniper",_G.AutoBuyDevilFruitSniper,function(value)
	_G.AutoBuyFruitSniper = value
end)



DevilFruit:Dropdown("Select Fruits Eat",FruitList,function(value)
	_G.SelectFruitEat = value
end)

DevilFruit:Toggle("Auto Eat Fruit",_G.AutoEatFruit,function(value)
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

DevilFruit:Toggle("Auto Eat Fruit Hop",_G.AutoEatFruitHop,function(value)
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

DevilFruit:Toggle("Auto Random Fruit",_G.Random_Auto,function(value)
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

DevilFruit:Button("Random Fruit",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
end)


DevilFruit:Toggle("Auto Drop Fruit",_G.DropFruit,function(value)
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

DevilFruit:Toggle("Auto Store Fruit",_G.AutoStoreFruit,function(value)
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


DevilFruit:Toggle("Grab Fruit",_G.BringFruit,function(value)
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

------------------------------------------------------------------------------------------------------------------------------

Shop:Seperator(" \\\\ Abilities // ")

Shop:Button("Buy Geppo [ $10,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
end)

Shop:Button("Buy Buso Haki [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
end)

Shop:Button("Buy Soru [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
end)

Shop:Button("Buy Observation Haki [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
end)

Shop:Toggle("Auto Buy Abilities", false, function(t)
	Abilities = t
	while Abilities do wait(.1)
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
	end
end)

Shop:Seperator(" \\\\  Boats // ")

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

Shop:Dropdown("Select Boats",BoatList,function(value)
	SelectBoat = value
end)

Shop:Button("Buy Boat",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat",_G.SelectBoat)
end)

Shop:Seperator(" \\\\ Fighting Style // ")

Shop:Button("Buy Black Leg [ $150,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
end)

Shop:Button("Buy Electro [ $550,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
end)

Shop:Button("Buy Fishman Karate [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
end)

Shop:Button("Buy Dragon Claw [ $1,500 Fragments ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
end)

Shop:Button("Buy Superhuman [ $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
end)

Shop:Button("Buy Death Step [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
end)

Shop:Button("Buy Sharkman Karate [ $5,000 Fragments $2,500,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
end)

Shop:Button("Buy Electric Claw [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
end)

Shop:Button("Buy Dragon Talon [ $5,000 Fragments $3,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
end)

Shop:Button("Buy God Human [ $5,000 Fragments $5,000,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
end)
-----Shop----------------

Shop:Seperator(" \\\\ Sword // ")

Shop:Button("Cutlass [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end)

Shop:Button("Katana [ $1,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end)

Shop:Button("Iron Mace [ $25,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end)

Shop:Button("Dual Katana [ $12,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end)

Shop:Button("Triple Katana [ $60,000 Beli ]", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end)

Shop:Button("Pipe [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end)

Shop:Button("Dual-Headed Blade [ $400,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end)

Shop:Button("Bisento [ $1,200,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end)

Shop:Button("Soul Cane [ $750,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end)

Shop:Button("Pole v.2 [ 5,000 Fragments ]",function()
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ThunderGodTalk")
end)

Shop:Toggle("Yama Sword [ Elite Hunter 30 ]",_G.AutoYama,function(value)
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
Shop:Seperator(" \\\\ Gun // ")

Shop:Button("Slingshot [ $5,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end)

Shop:Button("Musket [ $8,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end)

Shop:Button("Flintlock [ $10,500 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end)

Shop:Button("Refined Slingshot [ $30,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
end)

Shop:Button("Refined Flintlock [ $65,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Refined Flintlock"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Shop:Button("Cannon [ $100,000 Beli ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
end)

Shop:Button("Kabucha [ 1,500 Fragments]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end)

Shop:Button("Bizarre Rifle [ 250 Ectoplasm ]", function()
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

Shop:Seperator(" \\\\ Bones // ")

Shop:Button("Buy Surprise [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
end)

Shop:Button("Stat Refund [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,2)
end)

Shop:Button("Race Reroll [ $50 Bone ]",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,3)
end)

------------Stat------------------

Shop:Seperator(" \\\\ Stat // ")

Shop:Button("Reset Stats (Use 2.5K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end)

Shop:Button("Random Race (Use 3K Fragments)", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","2")
end)
--------------Accessories-----------------
Shop:Seperator(" \\\\ Accessories // ")
Shop:Button("Black Cape [ $50,000 Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Black Cape"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop:Button("Swordsman Hat [ 150k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Swordsman Hat"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop:Button("Tomoe Ring [ $500k Beli ]",function()
	local args = {
		[1] = "BuyItem",
		[2] = "Tomoe Ring"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

------------------------------------------------------------------------------------------------------------------------------

Misc:Seperator("Codes")

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

Misc:Button("Redeem All Codes",function()
	for i,v in pairs(x2Code) do
		UseCode(v)
	end
end)

Misc:Dropdown("Selected Codes",x2Code,function(value)
	_G.CodeSelect = value
end)

Misc:Button("Redeem Code",function()
	game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(_G.CodeSelect)
end)

Misc:Seperator(" \\\\  Abilities // ")

Misc:Toggle("Infinite Ability",false,function(infA)
	if infA then
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

Misc:Toggle("Infinite Obversation Range",false,function(value)
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
		elseif getgenv().InfiniteObRange == false and player then
			VisionRadius.Value = VS
		end
	end
end)

Misc:Toggle("Infinite Geppo",false,function(value)
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
									until not getgenv().InfGeppo or game:GetService("Players").LocalPlayer.Character.Humanoid.Health <= 0 
								end
							end
						end
					end
				end
			end
		end)
	end
end)

Misc:Toggle("Infinite Soru",false,function(value)
	_G.InfSoru = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if getgenv().InfSoru and game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") ~= nil  then
				for i,v in next, getgc() do
					if game:GetService("Players").LocalPlayer.Character.Soru then
						if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.Character.Soru then
							for i2,v2 in next, getupvalues(v) do
								if typeof(v2) == "table" then
									repeat wait(.1)
										v2.LastUse = 0
									until not getgenv().InfSoru or game:GetService("Players").LocalPlayer.Character.Humanoid.Health <= 0
								end
							end
						end
					end
				end
			end
		end)
	end
end)

Misc:Toggle("Infinite Jump",false, function(State)
	_G.Infinite = State
end)
game:GetService("UserInputService").JumpRequest:connect(function()
	if _G.Infinite then
		game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
	end
end)

Misc:Seperator(" \\\\ Highlight // ")

Misc:Toggle("Show Chat disabled", _G.chat, function(value)
	_G.chat = value
	if _G.chat == true then
		local StarterGui = game:GetService('StarterGui')
		StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Chat, false)    
	elseif _G.chat == false then
		local StarterGui = game:GetService('StarterGui')
		StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Chat, true)    
	end
end)

Misc:Toggle("Show leaderboard disabled", _G.leaderboard, function(a)
	_G.leaderboard = a
	if _G.leaderboard == true then
		local StarterGui = game:GetService('StarterGui')
		game:GetService('StarterGui'):SetCoreGuiEnabled(Enum.CoreGuiType.PlayerList, false)   
	elseif _G.leaderboard == false then
		local StarterGui = game:GetService('StarterGui')
		game:GetService('StarterGui'):SetCoreGuiEnabled(Enum.CoreGuiType.PlayerList, true)   
	end
end)

Misc:Toggle("Highlight Mode",false,function(value)
	if value == true then
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Beli.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.HP.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Energy.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.StatsButton.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ShopButton.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Skills.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Level.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.MenuButton.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Code.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Settings.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Mute.Visible = false
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.CrewButton.Visible = false
	else
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Beli.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.HP.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Energy.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.StatsButton.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ShopButton.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Skills.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Level.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.MenuButton.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Code.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Settings.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Mute.Visible = true
		game:GetService("Players")["LocalPlayer"].PlayerGui.Main.CrewButton.Visible = true
	end
end)

local transparent = false -- xray
function x(v)
	if v then
		for _,i in pairs(workspace:GetDescendants()) do
			if i:IsA("BasePart") and not i.Parent:FindFirstChild("Humanoid") and not i.Parent.Parent:FindFirstChild("Humanoid") then
				i.LocalTransparencyModifier = 0.7
			end
		end
	else
		for _,i in pairs(workspace:GetDescendants()) do
			if i:IsA("BasePart") and not i.Parent:FindFirstChild("Humanoid") and not i.Parent.Parent:FindFirstChild("Humanoid") then
				i.LocalTransparencyModifier = 0
			end
		end
	end
end

---- [RainbowHaki]
spawn(function()
	while wait() do
		if RainbowHaki then
			pcall(function()
				if game.Players.LocalPlayer.Character.HasBuso then
					for i,v in pairs(game.Players.LocalPlayer.Character.Humanoid:GetChildren()) do
						if v.Name == "RightLowerArm_BusoLayer1" or v.Name == "RightLowerArm_BusoLayer2" or v.Name == "RightHand_BusoLayer1" or v.Name == "RightHand_BusoLayer2" or v.Name == "LeftLowerArm_BusoLayer1" or v.Name == "LeftLowerArm_BusoLayer2" or v.Name == "LeftHand_BusoLayer1" or v.Name == "LeftHand_BusoLayer2" or v.Name == "LeftHand_BusoLayer1" or v.Name == "RightUpperArm_BusoLayer1" or v.Name == "RightUpperArm_BusoLayer2" or v.Name == "LeftUpperArm_BusoLayer1" or v.Name == "LeftUpperArm_BusoLayer2" or v.Name == "UpperTorso_BusoLayer1" or v.Name == "UpperTorso_BusoLayer2" or v.Name == "LowerTorso_BusoLayer1" or v.Name == "LowerTorso_BusoLayer2" or v.Name == "Head_BusoLayer1" or v.Name == "Head_BusoLayer2" or v.Name == "RightUpperLeg_BusoLayer1" or v.Name == "RightUpperLeg_BusoLayer2" or v.Name == "LeftUpperLeg_BusoLayer1" or v.Name == "LeftUpperLeg_BusoLayer2" or v.Name == "RightLowerLeg_BusoLayer1" or v.Name == "RightLowerLeg_BusoLayer2" or v.Name == "LeftLowerLeg_BusoLayer1" or v.Name == "LeftLowerLeg_BusoLayer2" or v.Name == "LeftFoot_BusoLayer1" or v.Name == "LeftFoot_BusoLayer2" or v.Name == "RightFoot_BusoLayer1" or v.Name == "RightFoot_BusoLayer2" then
							v.Color = Color3.fromHSV(tick() * 24 % 255/255, 1, 1)
						end
					end
				end
			end)
		end
	end
end)

Misc:Toggle("Rainbow Haki",false,function(value)
	RainbowHaki = value
end)

Misc:Toggle("Rainbow Yoru",false,function(value)
	RainbowYoru = value
end)

---- [RainbowYoru]

spawn(function()
	while wait() do
		if RainbowYoru then
			pcall(function()
				for i,v in pairs(game.Players.LocalPlayer.Character.DarkBlade.Right:GetChildren()) do
					if v.Name == "Runes" or v.Name == "Hold" or v.Name == "Bottom" or v.Name == "Gems" or v.Name == "Wings" or v.Name == "Blade" or v.Name == "Tape" then
						v.Color = Color3.fromHSV(tick() * 24 % 255/255, 1, 1)
						v.Material = "Neon"
					end

				end
			end)
		end
	end
end)

spawn(function()
	while wait(1) do
		if RainbowYoru then
			pcall(function()
				for i,v in pairs(game.Players.LocalPlayer.Character.DarkBlade.Right.Handle:GetChildren()) do
					if v.Name == "Trail" then
						v.LightEmission = 1
					end

				end
			end)
		end
	end
end)

spawn(function()
	while wait(1) do
		if RainbowYoru then
			pcall(function()
				for i,v in pairs(game.Players.LocalPlayer.Character.DarkBlade.Right.Handle.Attachment0:GetChildren()) do
					if v.Name == "Beam" then
						v.LightEmission = 1 v.Texture = 0 v.Width0 = 0 v.Width1 = 0
					end

				end
			end)
		end
	end
end)

Misc:Seperator(" \\\\ Server // ")

Misc:Button("Rejoin Server",function()
	game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end)

Misc:Button("Server Hop",function()
	Hop()
end)

Misc:Button("Hop To Lower Player",function()
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

JobiJoin = ""

Misc:Textbox("JOJ ID","",true,function(value)
	JobiJoin = Value
end)

Misc:Button("Join Server",function()
	game:GetService("TeleportService"):TeleportToPlaceInstance(game.placeId, JobiJoin, game.Players.LocalPlayer)
end)


Misc:Seperator(" \\\\ Misc // ")

Misc:Toggle("Auto Rejoin",true,function(value)
	_G.AutoRejoin = value
end)

spawn(function()
	while wait() do
		if _G.AutoRejoin then
			getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
				if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
					game:GetService("TeleportService"):Teleport(game.PlaceId)
				end
			end)
		end
	end
end)

Misc:Toggle("No Clip",_G.NoClip,function()
	_G.NoClip = value
end)

local WebHookLog = {}

local AllRequest = http_request or request or HttpPost or syn.request
function WebHookLog:WebHookKaiTanSend(WebHookUrl)

	function GetFightingStyle(Style)
		local ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAwaken()
		local ReturnText = ""
		local Awakened_Z = ":x:"
		local Awakened_X = ":x:"
		local Awakened_C = ":x:"
		local Awakened_V = ":x:"
		local Awakened_F = ":x:"
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							"\n"..":regional_indicator_x:"..Awakened_X..
							"\n"..":regional_indicator_c:"..Awakened_C..
							"\n"..":regional_indicator_v:"..Awakened_V..
							"\n"..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							"\n"..":regional_indicator_x:"..Awakened_X..
							"\n"..":regional_indicator_c:"..Awakened_C..
							"\n"..":regional_indicator_v:"..Awakened_V..
							"\n"..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeapon(Rare)
		if Rare == "Common" then
			RareNumber = 0
		elseif Rare == "Uncommon" then
			RareNumber = 1
		elseif Rare == "Rare" then
			RareNumber = 2
		elseif Rare == "Legendary" then
			RareNumber = 3
		elseif Rare == "Mythical" then
			RareNumber = 4
		else
			return "Worng InPut"
		end
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryWeapons")) do
			if type(v) == "table" then
				if v.Rarity then
					if tonumber(v.Rarity) == RareNumber then
						ReturnText = ReturnText .. v.Name .. "\n"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetFruitInU()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
			if type(v) == "table" then
				if v ~= nil then
					ReturnText = ReturnText .. v.Name .. " : " .. v.Price .. "\n"
				end
			end
		end

		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAllMelee()
		local BuyDragonTalon = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true))
		if BuyDragonTalon then
			if BuyDragonTalon == 1 then
				TalComplete = true
			end
		end
		local BuySuperhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true))
		if BuySuperhuman then
			if BuySuperhuman == 1 then
				SupComplete = true
			end
		end
		local BuySharkmanKarate = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true))
		if BuySharkmanKarate then
			if BuySharkmanKarate == 1 then
				SharkComplete = true
			end
		end
		local BuyDeathStep = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true))
		if BuyDeathStep then
			if BuyDeathStep == 1 then
				DeathComplete = true
			end
		end
		local BuyElectricClaw = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true))
		if BuyElectricClaw then
			if BuyElectricClaw == 1 then
				EClawComplete = true
			end
		end
		local BuyGod = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true))
		if BuyGod then
			if BuyGod == 1 then
				GodComplete = true
			end
		end
		ReturnText = {}
		if SupComplete == true then
			table.insert(ReturnText,"SuperHuman")
		end
		if EClawComplete == true then
			table.insert(ReturnText,"Electric Claw")
		end
		if TalComplete == true then
			table.insert(ReturnText,"Dragon Talon")
		end
		if SharkComplete == true then
			table.insert(ReturnText,"Sharkman Karate")
		end
		if DeathComplete == true then
			table.insert(ReturnText,"Death Step")
		end
		if GodComplete == true then
			table.insert(ReturnText,"God Human")
		end

		if #ReturnText ~= 0 then
			return table.concat(ReturnText,",")
		else
			return "Not Have"
		end
	end

	local Embeds = {{
		["title"] = "**Maruko Hub Webhooks Status**",
		["color"] = tonumber(0xD936FF),
		["fields"] = {
			{
				["name"] = "User Name",
				["value"] = "||"..tostring(game.Players.LocalPlayer.Name).."||",
				["inline"] = true
			},
			{
				["name"] = "Level",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Level").Value),
				["inline"] = true
			},
			{
				["name"] = "Fragments",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Fragments").Value),
				["inline"] = true
			},
			{
				["name"] = "Bounty/Honor",
				["value"] = tostring(game:GetService("Players").LocalPlayer.leaderstats["Bounty/Honor"].Value),
				["inline"] = true
			},
			{
				["name"] = "Beli",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Beli").Value),
				["inline"] = true
			},
			{
				["name"] = "Fighting Style",
				["value"] = GetFightingStyle("Melee"),
				["inline"] = true
			},
			{
				["name"] = "Sword",
				["value"] = GetFightingStyle("Sword"),
				["inline"] = true
			},
			{
				["name"] = "Devil Fruit",
				["value"] = GetFightingStyle("Blox Fruit"),
				["inline"] = true
			},
			{
				["name"] = "Gun",
				["value"] = GetFightingStyle("Gun"),
				["inline"] = true
			},
			{
				["name"] = "Accessory",
				["value"] = GetFightingStyle("Wear"),
				["inline"] = true
			},
			{
				["name"] = "Race",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Race").Value),
				["inline"] = true
			},
			{
				["name"] = "Awakened",
				["value"] = tostring(GetAwaken()),
				["inline"] = true
			},
			{
				["name"] = "Status",
				["value"] = "```sml\n"..tostring("Melee : "..game:GetService("Players").LocalPlayer.Data.Stats.Melee:WaitForChild("Level").Value .. 
					"\nDefense : "..game:GetService("Players").LocalPlayer.Data.Stats.Defense:WaitForChild("Level").Value .. 
					"\nSword : "..game:GetService("Players").LocalPlayer.Data.Stats.Sword:WaitForChild("Level").Value.. 
					"\nGun : "..game:GetService("Players").LocalPlayer.Data.Stats.Gun:WaitForChild("Level").Value .. 
					"\nDevil Fruit : "..game:GetService("Players").LocalPlayer.Data.Stats["Demon Fruit"]:WaitForChild("Level").Value).."```",
				["inline"] = true
			},
			{
				["name"] = "Common :blue_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Common")).."```",
				["inline"] = true
			},
			{
				["name"] = "Uncommon :green_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Uncommon")).."```",
				["inline"] = true
			},
			{
				["name"] = "Rare :yellow_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Rare")).."```",
				["inline"] = true
			},
			{
				["name"] = "Legendary :purple_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Legendary")).."```",
				["inline"] = true
			},
			{
				["name"] = "Mythical :red_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Mythical")).."```",
				["inline"] = true
			},
			{
				["name"] = "Fruit In Inventory",
				["value"] = "```sml\n"..tostring(GetFruitInU()).."```",
				["inline"] = true
			},
			{
				["name"] = "All Melee",
				["value"] = "```sml\n"..tostring(GetAllMelee()).."```",
				["inline"] = true
			},



			{
				["name"] = "ㅤ",
				["value"] = tostring("ㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤ"),
				["inline"] = false
			}},
		["footer"] = {
			["text"] = "Made by ! aExeur#4748".."\nTime".." : "..os.date("%c").." ("..os.date("%X")..")",
			["icon_url"] = "https://cdn.discordapp.com/attachments/834780708551393349/1035779918795112448/20221013140538_1.png"
		},
	}}

	local Message
	if _G.SendWebHookPing then
		Message = {
			['username'] = "Unique Webhook",
			["avatar_url"] = "https://cdn.discordapp.com/attachments/834780708551393349/1035779918795112448/20221013140538_1.png",
			["content"] = "@everyone",
			["embeds"] = Embeds,
		}
	else
		Message = {
			['username'] = "Unique Webhook",
			["avatar_url"] = "https://cdn.discordapp.com/attachments/834780708551393349/1035779918795112448/20221013140538_1.png",
			["embeds"] = Embeds,
		}
	end

	local DataCallBack = AllRequest({
		Url = WebHookUrl,
		Method = 'POST',
		Headers = {
			["Content-Type"] = "application/json"
		},
		Body = game:GetService("HttpService"):JSONEncode(Message)
	})
	return DataCallBack
end

function WebHookLog:SheetBestLogSend(SheetBestUrl)

	function GetFightingStyle(Style)
		ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAllMelee()
		BuyDragonTalon = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true))
		if BuyDragonTalon then
			if BuyDragonTalon == 1 then
				TalComplete = true
			end
		end
		BuySuperhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true))
		if BuySuperhuman then
			if BuySuperhuman == 1 then
				SupComplete = true
			end
		end
		BuySharkmanKarate = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true))
		if BuySharkmanKarate then
			if BuySharkmanKarate == 1 then
				SharkComplete = true
			end
		end
		BuyDeathStep = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true))
		if BuyDeathStep then
			if BuyDeathStep == 1 then
				DeathComplete = true
			end
		end
		BuyElectricClaw = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true))
		if BuyElectricClaw then
			if BuyElectricClaw == 1 then
				EClawComplete = true
			end
		end
		BuyGod = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true))
		if BuyGod then
			if BuyGod == 1 then
				GodComplete = true
			end
		end
		ReturnText = {}
		if SupComplete == true then
			table.insert(ReturnText,"SuperHuman")
		end
		if EClawComplete == true then
			table.insert(ReturnText,"Electric Claw")
		end
		if TalComplete == true then
			table.insert(ReturnText,"Dragon Talon")
		end
		if SharkComplete == true then
			table.insert(ReturnText,"Sharkman Karate")
		end
		if DeathComplete == true then
			table.insert(ReturnText,"Death Step")
		end
		if GodComplete == true then
			table.insert(ReturnText,"God Human")
		end

		if #ReturnText ~= 0 then
			return table.concat(ReturnText,",")
		else
			return "Not Have"
		end
	end

	function GetAwaken()
		ReturnText = ""
		Awakened_Z = "❌"
		Awakened_X = "❌"
		Awakened_C = "❌"
		Awakened_V = "❌"
		Awakened_F = "❌"
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = "Z"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = "X"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = "C"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = "V"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = "F"
						end
						ReturnText = Awakened_Z..
							" : "..Awakened_X..
							" : "..Awakened_C..
							" : "..Awakened_V..
							" : "..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							" : "..":regional_indicator_x:"..Awakened_X..
							" : "..":regional_indicator_c:"..Awakened_C..
							" : "..":regional_indicator_v:"..Awakened_V..
							" : "..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeapon()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryWeapons")) do
			if type(v) == "table" then
				if v.Name then
					ReturnText = ReturnText .. v.Name .. " "
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetFruitInU()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
			if type(v) == "table" then
				if v ~= nil then
					ReturnText = ReturnText .. v.Name .. " "
				end
			end
		end

		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeaponMastery(Style)
		ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v:FindFirstChild("Level").Value
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v:FindFirstChild("Level").Value
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function Abbreviate(x)
		local abbreviations = {
			"K", -- 4 digits
			"M", -- 7 digits
			"B", -- 10 digits
			"T", -- 13 digits
			"QD", -- 16 digits
			"QT", -- 19 digits
			"SXT", -- 22 digits
			"SEPT", -- 25 digits
			"OCT", -- 28 digits
			"NON", -- 31 digits
			"DEC", -- 34 digits
			"UDEC", -- 37 digits
			"DDEC", -- 40 digits
		}
		if x < 1000 then 
			return tostring(x)
		end

		local digits = math.floor(math.log10(x)) + 1
		local index = math.min(#abbreviations, math.floor((digits - 1) / 3))
		local front = x / math.pow(10, index * 3)

		return string.format("%i%s+", front, abbreviations[index])
	end

	local Message
	Message = {
		["UserName"] = tostring(game.Players.LocalPlayer.Name),
		["Level"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Level").Value),
		["Weapon inventory"] = tostring(GetWeapon()),
		["Fruit inventory"] = tostring(GetFruitInU()),
		["Melee"] = tostring(GetAllMelee()),
		["Fruit"] = tostring(GetFightingStyle("Blox Fruit")),
		["Fruit Mastery"] = tostring(GetWeaponMastery("Blox Fruit")),
		["Fruit Awake"] = tostring(GetAwaken()),
		["Beli"] = tostring(Abbreviate(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Beli").Value)),
		["Fragment"] = tostring(Abbreviate(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Fragments").Value)),
		["Race"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Race").Value)
	}

	local DataCallBack = AllRequest({
		Url = SheetBestUrl,
		Method = 'POST',
		Headers = {
			["Content-Type"] = "application/json"
		},
		Body = game:GetService("HttpService"):JSONEncode(Message)
	})
	return DataCallBack
end

Misc:Seperator(" \\\\ Main - Mob // ")

Misc:Button("Remove Lave",function()
	for i,v in pairs(game.Workspace:GetDescendants()) do
		if v.Name == "Lava" then   
			v:Destroy()
		end
	end
	for i,v in pairs(game.ReplicatedStorage:GetDescendants()) do
		if v.Name == "Lava" then   
			v:Destroy()
		end
	end
end)

Misc:Button("Invisible (lag)",function()
	game.Players.LocalPlayer.Character.LowerTorso.Root:Destroy()
end)

Misc:Button("Invisible [Remove]",function()
	local removeNametags = true -- remove custom billboardgui nametags from hrp, could trigger anticheat

	local plr = game:GetService("Players").LocalPlayer
	local character = plr.Character
	local hrp = character.HumanoidRootPart
	local old = hrp.CFrame

	if not character:FindFirstChild("LowerTorso") or character.PrimaryPart ~= hrp then
		return print("unsupported")
	end

	if removeNametags then
		local tag = hrp:FindFirstChildOfClass("BillboardGui")
		if tag then tag:Destroy() end

		hrp.ChildAdded:Connect(function(item)
			if item:IsA("BillboardGui") then
				task.wait()
				item:Destroy()
			end
		end)
	end

	local newroot = character.LowerTorso.Root:Clone()
	hrp.Parent = workspace
	character.PrimaryPart = hrp
	character:MoveTo(Vector3.new(old.X,9e9,old.Z))
	hrp.Parent = character
	task.wait(0.5)
	newroot.Parent = hrp
	hrp.CFrame = old
end)

Misc:Button("Max Zoom", function()
	while wait() do
		game.Players.LocalPlayer.CameraMaxZoomDistance = 9223372036854718
	end
end)

Misc:Textbox("BaseSheet","",true,function(value)
	Baselink = Value
end)

Misc:Button("Send BaseSheet", function()
	WebHookLog:SheetBestLogSend(Baselink)
end)

Misc:Button("Max Zoom", function()
	while wait() do
		game.Players.LocalPlayer.CameraMaxZoomDistance = 9223372036854718
	end
end)

Misc:Seperator(" \\\\ State // ")

Misc:Dropdown("Select Haki State",{"State 0","State 1","State 2","State 3","State 4","State 5"},function(value)
	_G.SelectStateHaki = value
end)

Misc:Button("Change Buso Haki State",function()
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

Misc:Seperator(" \\\\ Boost FPS // ")

Misc:Button("FPS Booster",function()
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

Misc:Button("Invisible",function()
	game:GetService("Players").LocalPlayer.Character.LowerTorso:Destroy()
end)

Misc:Button("Click TP Tool",function()
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

Misc:Toggle("Remove Fog",false,function(value)
	_G.RVFG_SsXz = value
end)

task.spawn(function()
	while wait(0.01) do
		pcall(function()
			if _G.RVFG_SsXz then
				if game:GetService("Lighting"):FindFirstChild("Sky") then game:GetService("Lighting").Sky:Destroy()
				end
			end
		end)
	end
end)

Misc:Toggle("Auto Click",false,function(value)
	_G.click = value
end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		if _G.click then
			pcall(function()
				game:GetService'VirtualUser':CaptureController()
				game:GetService'VirtualUser':Button1Down(Vector2.new(0,1,0,1))
			end)
		end
	end)
end)
