local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

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
	local ui = game.CoreGui:FindFirstChild("ManakeUiLib")
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
	NameHub.Size = UDim2.new(0, 110, 0, 20)
	NameHub.Font = Enum.Font.Gotham
	NameHub.Text = text
	NameHub.TextColor3 = Color3.fromRGB(255, 0, 0)
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

	function uitab:AddTab(text,image)
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

		local PageImage = Instance.new("ImageLabel")
		PageImage.Name = "PageImage"
		PageImage.Parent = PageButton
		PageImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		PageImage.BackgroundTransparency = 1.000
		PageImage.Position = UDim2.new(0, -20, 0, 3)
		PageImage.Size = UDim2.new(0, 15, 0, 15)
		PageImage.Image = "rbxassetid://"..tostring(Image)

		local MainTab = Instance.new("Frame")
		MainTab.Name = "MainTab"
		MainTab.Parent = TabFolder
		MainTab.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
		MainTab.BorderSizePixel = 0
		MainTab.Position = UDim2.new(0.208333328, 0, 0, 0)
		MainTab.Size = UDim2.new(0, 475, 0, 350)
		MainTab.Visible = false

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
					{TextColor3 = Color3.fromRGB(255, 0, 0)}
				):Play()
			end
		end)

		if ff == false then
			TweenService:Create(
				PageButton,
				TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
				{TextColor3 = Color3.fromRGB(255, 0, 0)}
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

		function main:AddButton(text,callback)
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
					{TextColor3 = Color3.fromRGB(255, 0, 0)}
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

		function main:AddToggle(text,config,callback)
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
			ToggleImage2.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
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
					{TextColor3 = Color3.fromRGB(255, 0, 0)}
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

		function main:AddTextbox(text,holder,disappear,callback)
			local Textboxx = Instance.new("Frame")
			local TextboxxCorner = Instance.new("UICorner")
			local TextboxTitle = Instance.new("TextLabel")
			local Textbox = Instance.new("TextBox")
			local TextboxCorner = Instance.new("UICorner")

			Textboxx.Name = "Textboxx"
			Textboxx.Parent = ScrollTab
			Textboxx.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
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

		function main:AddDropdown(text,table,callback)
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
						{TextColor3 = Color3.fromRGB(255, 0, 0)}
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

		function main:AddSlider(text,min,max,set,callback)
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
			Bar.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
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
		function main:AddSeperator(text)
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
			Sep1.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
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
			Sep2.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
			Sep2.BorderSizePixel = 0
			Sep2.Position = UDim2.new(0, 305, 0, 10)
			Sep2.Size = UDim2.new(0, 150, 0, 1)
		end
		function main:AddLine()
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
			Linee.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
			Linee.BorderSizePixel = 0
			Linee.Position = UDim2.new(0, 0, 0, 10)
			Linee.Size = UDim2.new(0, 455, 0, 1)
		end
		function main:AddLabel(text)
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

getgenv().ToTarget = function(Pos)
	local r = game:GetService("Players").LocalPlayer
	local xTweenPosition = {}
	if not game.Players.LocalPlayer.Character:FindFirstChild("Root")then 
		local K = Instance.new("Part",game.Players.LocalPlayer.Character) -- Create part
		K.Size = Vector3.new(20,0.5,20)
		K.Name = "Root"
		K.Anchored = true
		K.Transparency = 1
		K.CanCollide = false
		K.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,0.6,0) --spawn at player
	end

	if _G.FastTween == true then
		Speed = 575	
	else
		Speed = 350
	end

	local Tween_Service = game:service"TweenService"
	local TweenPosition = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude -- diatance 
	local Magnitude=TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.Root.Position-Pos.Position).Magnitude/Speed,Enum.EasingStyle.Linear) -- Create Tween
	local function PartToPlayers() --teleport parta to player
		game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
	end

	local function PlayersToPart() -- teleport player to part
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.Root.CFrame
	end

	function xTweenPosition:Stop() --stop tween
		tween:Cancel()
		game.Players.LocalPlayer.Character["Root"]:Destroy()
		return tween
	end

	if TweenPosition <= 0 then
		pcall(function()
			tween:Cancel()
			game.Players.LocalPlayer.Character.Root.CFrame = Pos
			game.Players.LocalPlayer.Character["Root"]:Destroy()
		end)
	end

	spawn(function()
		while wait() do -- or RenderStepped
			pcall(function()
				PlayersToPart()
				if(game.Players.LocalPlayer.Character.Root.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude >= 1 then
					PartToPlayers()
				elseif (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1 then
					game.Players.LocalPlayer.Character["Root"]:Destroy()
				end
			end)
		end
	end)
	if game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health <= 0 then 
		if tween then 
			tween:Cancel()
			game.Players.LocalPlayer.Character["Root"]:Destroy()
		end 
		repeat wait() until game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health > 0; wait(0.2)
	end

	local tween,error = pcall(function()
		tween=Tween_Service:Create(
			game.Players.LocalPlayer.Character["Root"],Magnitude,{CFrame=Pos})
		tween:Play() 
	end)
	if not tween then return error end

	return xTweenPosition
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

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
	local p13 = CbFw2.activeController
	local ret = p13.blades[1]
	if not ret then return end
	while ret.Parent ~= game.Players.LocalPlayer.Character do ret=ret.Parent end
	return ret
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

function InfAbility()
	if _G.Infinit_Ability then
		if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
			local inf = Instance.new("ParticleEmitter")
			inf.Acceleration = Vector3.new(0,0,0)
			inf.Archivable = true
			inf.Drag = 20
			inf.EmissionDirection = Enum.NormalId.Top
			inf.Enabled = true
			inf.Lifetime = NumberRange.new(0.2,0.2)
			inf.LightInfluence = 0
			inf.LockedToPart = true
			inf.Name = "Agility"
			inf.Rate = 500
			local numberKeypoints2 = {
				NumberSequenceKeypoint.new(0, 0); 
				NumberSequenceKeypoint.new(1, 4); 
			}

			inf.Size = NumberSequence.new(numberKeypoints2)
			inf.RotSpeed = NumberRange.new(999, 9999)
			inf.Rotation = NumberRange.new(0, 0)
			inf.Speed = NumberRange.new(30, 30)
			inf.SpreadAngle = Vector2.new(360,360)
			inf.Texture = "rbxassetid://243098098"
			inf.VelocityInheritance = 0
			inf.ZOffset = 2
			inf.Transparency = NumberSequence.new(0)
			inf.Color = ColorSequence.new(Color3.fromRGB(0, 255, 255),Color3.fromRGB(0, 255, 255))
			inf.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
		end
	else
		if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
			game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility"):Destroy()
		end
	end
end

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

local LocalPlayer = game:GetService'Players'.LocalPlayer
local originalstam = LocalPlayer.Character.Energy.Value
function InfinitEnergy()
	game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
		if _G.Infinit_Energy then
			LocalPlayer.Character.Energy.Value = originalstam
		end 
	end)
end

function SoruNoCoolDown()
	for i, v in pairs(getgc()) do
		if type(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character:WaitForChild("Soru") then
			for i2,v2 in pairs(debug.getupvalues(v)) do
				if type(v2) == 'table' then
					if v2.LastUse then
						repeat wait()
							setupvalue(v, i2, {LastAfter = 0,LastUse = 0})
						until not _G.Infinit_Soru
					end
				end
			end
		end
	end
end

function RemoveSpaces(str)
	return str:gsub(" Fruit", "")
end

local function formatNumber(number)
	local i, k, j = tostring(number):match("(%-?%d?)(%d*)(%.?.*)")
	return i..k:reverse():gsub("(%d%d%d)", "%1,"):reverse()..j
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

spawn(function()
	while wait() do
		if setscriptable then
			setscriptable(game.Players.LocalPlayer, "SimulationRadius", true)
			game.Players.LocalPlayer.SimulationRadius = math.huge
		end
	end
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
		for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
			if v:IsA("Tool") then
				if v:FindFirstChild("RemoteFunctionShoot") then 
					SelectToolWeaponGun = v.Name
				end
			end
		end
	end
end)

spawn(function()
	local gg = getrawmetatable(game)
	local old = gg.__namecall
	setreadonly(gg,false)
	gg.__namecall = newcclosure(function(...)
		local method = getnamecallmethod()
		local args = {...}
		if tostring(method) == "FireServer" then
			if tostring(args[1]) == "RemoteEvent" then
				if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
					if UseSkillMasteryDevilFruit then
						args[2] = PositionSkillMasteryDevilFruit
						return old(unpack(args))
					elseif AimSkillNearest then
						args[2] = AimBotSkillPosition
						return old(unpack(args))
					end
				end
			end
		end
		return old(...)
	end)
end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		if UseGun then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if v.Name == Ms then
						local args = {
							[1] = "TAP",
							[2] = v.HumanoidRootPart.Position
						}

						game:GetService("Players").LocalPlayer.Character.Humanoid:FindFirstChild("Soul Guitar"):InvokeServer(unpack(args))
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

local lp = game:GetService('Players').LocalPlayer
local mouse = lp:GetMouse()
spawn(function()
	while wait() do
		if _G.Aimbot_Skill_Fov then
			pcall(function()
				local MaxDist, Closest = math.huge
				for i,v in pairs(game:GetService("Players"):GetChildren()) do 
					local Head = v.Character:FindFirstChild("HumanoidRootPart")
					local Pos, Vis = game.Workspace.CurrentCamera.WorldToScreenPoint(game.Workspace.CurrentCamera, Head.Position)
					local MousePos, TheirPos = Vector2.new(mouse.X, mouse.Y), Vector2.new(Pos.X, Pos.Y)
					local Dist = (TheirPos - MousePos).Magnitude
					if Dist < MaxDist and Dist <= _G.Select_Size_Fov and v.Name ~= game.Players.LocalPlayer.Name then
						MaxDist = Dist
						_G.Aim_Players = v
					end
				end
			end)
		end
	end
end)

spawn(function()
	local gg = getrawmetatable(game)
	local old = gg.__namecall
	setreadonly(gg,false)
	gg.__namecall = newcclosure(function(...)
		local method = getnamecallmethod()
		local args = {...}
		if tostring(method) == "FireServer" then
			if tostring(args[1]) == "RemoteEvent" then
				if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
					if _G.Aimbot_Skill_Fov then
						args[2] = _G.Aim_Players.Character.HumanoidRootPart.Position
						return old(unpack(args))
					end
				end
			end
		end
		return old(...)
	end)
end)

----------------------------------------------------------------------------------------------

local SOMEXHUB = library:AddWindow("Maruko Hub",Enum.KeyCode.RightControl)

local Main = SOMEXHUB:AddTab("Main","6026568198")
local Stats1 = SOMEXHUB:AddTab("Stats","7040410130")
local Teleport = SOMEXHUB:AddTab("Teleport","6035190846")
local Dungeon = SOMEXHUB:AddTab("Dungeon","7044284832")
local Shop = SOMEXHUB:AddTab("Shop","6031265976")
local Misc = SOMEXHUB:AddTab("Misc","7040347038")

Main:AddSeperator("Chack All")

Time = Main:AddLabel("Server Time")

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

Main:AddSeperator("Auto Farm Level")

Main:AddLabel("Auto Farm Level")

Main:AddToggle("Auto Farm Level",false,function(value)
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
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
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
							getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame * Method)
						else	
							getgenv().ToTarget(CFrameMon)
						end
					end
				end
			end)
		end
	end
end)

----------------------------------------------------------------------------------------------


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

local SelectWeapona = Main:AddDropdown("Select Weapon",Weapon,function(value)
	SelectWeapon = value
end)

-------------------------------------------------------------------------------------------------------------------------------------------------------

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function() CheckQuest()
		pcall(function()
			if _G.Brimob then
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Level and StartMagnet and v.Name == Ms and (v.HumanoidRootPart.Position - PosMon.Position).magnitude <= 300 then
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

--------------------------------------------------------------------------------------------------------------------------------------------------
if World1 then

	Main:AddSeperator("World")

	Main:AddToggle("Auto New World",false,function(value)
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

	Main:AddSeperator("World")	

	Main:AddToggle("Auto Third World",false,function(value)
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

Main:AddSeperator("Chest")

Main:AddToggle("Auto Farm Chest",false,function(value)
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

Main:AddToggle("Auto Farm Chest Fast",false,function(value)
	_G.ChestBypass = value
	StopTween(_G.ChestBypass)
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


Main:AddToggle("Auto Farm Chest Hop",false,function(value)
	_G.Auto_Farm_Chest_Hop = value
end)

-----------------------------------------------------------------------------------------------------------------------


if World3 then

	Main:AddSeperator("EliteHunter")

	local EliteProgress = Main:AddLabel("")

	spawn(function()
		pcall(function()
			while wait() do
				EliteProgress:Set("Elite Progress : "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress"))
			end
		end)
	end)

	Main:AddToggle("Auto Elite Hunter",_G.AutoElitehunter,function(value)
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

	Main:AddToggle("Auto Elite Hunter Hop",_G.AutoElitehunterHop,function(value)
		_G.AutoElitehunterHop = value
	end)
end

-------------------------------------------------------------------------

if World2 then

	Main:AddSeperator("Swan Glasses")

	Main:AddToggle("Auto Swan Glasses",false,function(value)
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

	Main:AddToggle("Auto Swan Glasses Hop",false,function(value)
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

	Main:AddSeperator("Bone")

	local BoneFarm = Main:AddToggle("Auto Farm Bone",_G.Auto_Farm_Bone,function(value)
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

	Main:AddToggle("Auto Random Surprise",_G.Auto_Random_Bone,function(value)
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

	Main:AddSeperator("Cake Prince")

	local CakePrince = Main:AddLabel("")

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

	local SpawnCake = Main:AddToggle("Auto Spawn Cake Prince",true,function(value)
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

	local AutoFarmCake = Main:AddToggle("Auto Cake Prince",false,function(value)
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

------------------------------------------------------------------------------------------------------------------------------------------------------------------------
if World2 then
	Main:AddSeperator("Ectoplasm")

	local CheckingEctoplasm = Main:AddLabel("")

	spawn(function()
		pcall(function()
			while wait() do
				CheckingEctoplasm:Set("Checking Ectoplasm : "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check").." Ectoplasm")
			end
		end)
	end)

	Main:AddToggle("Auto Ectoplasm", false, function(value)
		_G.AutoEctoplasm = value
		StopTween(_G.AutoEctoplasm)
	end)

	spawn(function()
		while wait() do 
			if _G.AutoEctoplasm then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Ship Deckhand [Lv. 1250]" or v.Name == "Ship Engineer [Lv. 1275]" or v.Name == "Ship Steward [Lv. 1300]" or v.Name == "Ship Officer [Lv. 1325]" then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat task.wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid.WalkSpeed = 0
										v.Head.CanCollide = false 
										EctoplasmMon = v.HumanoidRootPart.CFrame
										StartEctoplasmMagnet = true
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
									until not _G.AutoEctoplasm or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartEctoplasmMagnet = false
						local Distance = (Vector3.new(911.35827636719, 125.95812988281, 33159.5390625) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
						if Distance > 18000 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
						end
						getgenv().ToTarget(CFrame.new(-9515.751953125, 144.33457946777344, 5787.08935546875))
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Ship Deckhand [Lv. 1250]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)                         
							elseif v.Name == "Ship Engineer [Lv. 1275]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)                         
							elseif v.Name == "Ship Steward [Lv. 1300]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)                         
							elseif v.Name == "Ship Officer [Lv. 1325]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)                         
							end
						end
					end
				end)
			end
		end
	end)
end

if World2 then
	Main:AddSeperator("Order Sword")

	Main:Toggle("Auto Order Sword",_G.Auto_Kill_Law,function(value)
		_G.Auto_Kill_Law = value
		StopTween(_G.Auto_Kill_Law)
	end)

	Main:AddToggle("Auto Order Sword Hop", _G.Auto_Kill_LawHop,function(value)
		_G.Auto_Kill_LawHop = value
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
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * Method)
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								until not _G.Auto_Kill_Law or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					end 
				end)
			end
		end
	end)

	Main:AddToggle("Auto Buy Microchip Order",_G.MicrochipOrder,function(value)
		_G.MicrochipOrder = value
	end)

	spawn(function()
		while wait() do
			if _G.MicrochipOrder then
				local args = {
					[1] = "BlackbeardReward",
					[2] = "Microchip",
					[3] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)

	Main:AddToggle("Auto Start Raid Order",_G.AutoStartRaidOrder,function(value)
		_G.AutoStartRaidOrder = value
	end)

	spawn(function()
		while wait(.1) do
			pcall(function()
				if _G.AutoStartRaidOrder then
					if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
						if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") then
							if World2 then
								fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
							end
						end
					end
				end
			end)
		end
	end)

	Main:AddButton("Buy Microchip Order",function()
		local args = {
			[1] = "BlackbeardReward",
			[2] = "Microchip",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)

	Main:AddButton("Start Raid Order",function()
		fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
	end)
end

---------------------------------------------------------------------------------

Stats1:AddSeperator("Stats")

local Pointstat = Stats1:AddLabel("Stat Points")

spawn(function()
	while wait() do
		pcall(function()
			Pointstat:Set("Stat Points : "..tostring(game:GetService("Players")["LocalPlayer"].Data.Points.Value))
		end)
	end
end)

Stats1:AddToggle("Auto Melee",_G.Auto_Melee,function(value)
	_G.Auto_Melee = value
end)

Stats1:AddToggle("Auto Defense",_G.Auto_Defense,function(value)
	_G.Auto_Defense = value
end)

Stats1:AddToggle("Auto Sword",_G.Auto_Sword,function(value)
	_G.Auto_Sword = value
end)

Stats1:AddToggle("Auto Gun",_G.Auto_Gun,function(value)
	_G.Auto_Gun = value
end)

Stats1:AddToggle("Auto Devil Fruits",_G.Auto_DevilFruit,function(value)
	_G.Auto_DevilFruit = value
end)

_G.PointStats = 1
Stats1:AddSlider("Select Point",1,100,1,function(value)
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

-----------------------------------------------------------------------------------------

Dungeon:AddSeperator("Dungeon")

local TimeRaid = Dungeon:AddLabel("Wait For Dungeon")

spawn(function()
	pcall(function()
		while wait() do
			if game:GetService("Players").LocalPlayer.PlayerGui.Main.Timer.Visible == true then
				TimeRaid:Set(game:GetService("Players").LocalPlayer.PlayerGui.Main.Timer.Text)
			else
				TimeRaid:Set("Wait For Dungeon")
			end
		end
	end)
end)

Dungeon:AddToggle("Auto Farm Dungeon",_G.Auto_Dungeon,function(value)
	_G.Auto_Dungeon = value
	StopTween(_G.Auto_Dungeon)
end)

spawn(function()
	pcall(function() 
		while wait() do
			if _G.Auto_Dungeon then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
						if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
							pcall(function()
								repeat task.wait()                                    
									v.Humanoid.Health = 0
									v.HumanoidRootPart.CanCollide = false
									sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
								until not _G.Auto_Dungeon or not v.Parent or v.Humanoid.Health <= 0
							end)
						end
					end
				end
			end
		end
	end)
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Auto_Dungeon then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(100,70,100))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(100,70,100))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(100,70,100))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(100,70,100))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(100,70,100))
					end
				end
			end
		end
	end)
end)

Dungeon:AddToggle("Auto Awakener",_G.Auto_Awakener,function(value)
	_G.Auto_Awakener = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Auto_Awakener then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
			end
		end
	end)
end)

Dungeon:AddLine()

Dungeon:AddDropdown("Select Chips",{"Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird: Phoenix"},function(value)
	_G.SelectChip = value
end)

Dungeon:AddToggle("Auto Select Dungeon",_G.AutoSelectDungeon,function(value)
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

Dungeon:AddToggle("Auto Buy Chip",_G.AutoBuyChip,function(value)
	_G.AutoBuyChip = value
end)

Dungeon:AddToggle("Auto Start Raid",_G.Auto_StartRaid,function(value)
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

Dungeon:AddLine()

Dungeon:AddButton("Next Island",function()
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
end)

if World2 then
	Dungeon:AddButton("Teleport to Lab",function()
		getgenv().ToTarget(CFrame.new(-6438.73535, 250.645355, -4501.50684))
	end)
elseif World3 then
	Dungeon:AddButton("Teleport to Lab",function()
		getgenv().ToTarget(CFrame.new(-5017.40869, 314.844055, -2823.0127, -0.925743818, 4.48217499e-08, -0.378151238, 4.55503146e-09, 1, 1.07377559e-07, 0.378151238, 9.7681621e-08, -0.925743818))
	end)
end

if World2 then
	Dungeon:AddButton("Awakening Room",function()
		getgenv().ToTarget(CFrame.new(266.227783, 1.39509034, 1857.00732))
	end)
elseif World3 then
	Dungeon:AddButton("Awakening Room",function()
		getgenv().ToTarget(CFrame.new(-11571.440429688, 49.172668457031, -7574.7368164062))
	end)
end

----------------------------------------------------------------------------------------
Teleport:AddSeperator("World - Monster")

Teleport:AddButton("Teleport To Old World",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end)

Teleport:AddButton("Teleport To Second Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
end)

Teleport:AddButton("Teleport To Third Sea",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end)


Teleport:AddSeperator("Island")

if World1 then
	Teleport:AddDropdown("Select Island",{
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
	Teleport:AddDropdown("Select Island",{
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
	Teleport:AddDropdown("Select Island",{
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
	},function(value)
		_G.SelectIsland = value
	end)
end

Teleport:AddToggle("Teleport",false,function(value)
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

--------------------------------------------------------------------------------------------

Shop:AddSeperator("Abilities")

Shop:AddButton("Buy Geppo",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
end)

Shop:AddButton("Buy Buso Haki",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
end)

Shop:AddButton("Buy Soru",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
end)

Shop:AddButton("Buy Observation(Ken) Haki",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
end)

Shop:AddSeperator("Fighting Style")

Shop:AddButton("Buy Black Leg",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
end)

Shop:AddButton("Buy Electro",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
end)

Shop:AddButton("Buy Fishman Karate",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
end)

Shop:AddButton("Buy Dragon Claw",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
end)

Shop:AddButton("Buy Superhuman",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
end)

Shop:AddButton("Buy Death Step",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
end)

Shop:AddButton("Buy Sharkman Karate",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
end)

Shop:AddButton("Buy Electric Claw",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
end)

Shop:AddButton("Buy Dragon Talon",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
end)

Shop:AddButton("Buy God Human Talon",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
end)

-----Shop----------------
Shop:AddSeperator("Accessory")

Shop:AddButton("Tomoe Ring",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Tomoe Ring")
end)

Shop:AddButton("Black Cape",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Black Cape")
end)

Shop:AddButton("Swordsman Hat",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Swordsman Hat")
end)

Shop:AddSeperator("Sword")

Shop:AddButton("Cutlass",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end)

Shop:AddButton("Katana",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end)

Shop:AddButton("Iron Mace",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end)

Shop:AddButton("Duel Katana",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end)

Shop:AddButton("Triple Katana", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end)

Shop:AddButton("Pipe",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end)

Shop:AddButton("Dual Headed Blade",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end)

Shop:AddButton("Bisento",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end)

Shop:AddButton("Soul Cane",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end)

Shop:AddSeperator("Gun")

Shop:AddButton("Slingshot",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end)

Shop:AddButton("Musket",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end)

Shop:AddButton("Flintlock",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end)

Shop:AddButton("Refined Flintlock",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
end)

Shop:AddButton("Cannon",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
end)

Shop:AddButton("Kabucha",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end)
------------Bone------------------

Shop:AddSeperator("Bones")

Shop:AddButton("Buy Surprise",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
end)

Shop:AddButton("Stat Refund",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,2)
end)

Shop:AddButton("Race Reroll",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,3)
end)

Shop:AddSeperator("Fragments")

Shop:AddButton("Stat Refund",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end)

Shop:AddSeperator("Boats")

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

Shop:AddDropdown("Select Boats",BoatList,function(value)
	SelectBoat = value
end)

Shop:AddButton("Buy Boat",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat",_G.SelectBoat)
end)

-----------------------------------------------------------------------------------------------

Misc:AddSeperator("Main")

Misc:AddToggle("Auto Set Spawn Points",true,function(value)
	_G.AutoSetSpawn = value
end)

spawn(function()
	pcall(function()
		while wait() do
			if _G.AutoSetSpawn then
				if game:GetService("Players").LocalPlayer.Character.Humanoid.Health > 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
				end
			end
		end
	end)
end)

_G.Select_Weapon_Method = 15
Misc:AddSlider("Method Y",1,50,_G.Select_Weapon_Method,function(value)
	_G.Select_Weapon_Method = value
end)

_G.Method = "Behind"
Misc:AddDropdown("Select Farm Method", {
	"Behind","Below","Upper"
},function(value)
	_G.Method = value
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Method == "Behind" then
				Method = CFrame.new(0,0,_G.Select_Weapon_Method)
			elseif _G.Method == "Below" then
				Method = CFrame.new(0,-_G.Select_Weapon_Method,0)
			elseif _G.Method == "Upper" then
				Method = CFrame.new(0,_G.Select_Weapon_Method,0)
			else
				Method = CFrame.new(0,_G.Select_Weapon_Method,0)
			end
		end)
	end
end)

_G.Select_Weapon_Method1 = 0


Misc:AddToggle("Fast Attack",true, function(value)
	_G.FastAttack = value
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
		while wait(0.059) do
			if _G.FastAttack  then
				if SeraphFrame.activeController then
					SeraphFrame.activeController.timeToNextAttack = (math.huge^math.huge^math.huge)
					SeraphFrame.activeController.focusStart = 0
					SeraphFrame.activeController.hitboxMagnitude = 40
					SeraphFrame.activeController.humanoid.AutoRotate = true
					SeraphFrame.activeController.increment = 1 + 1 / 1
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

local cdnormal = 0
local Animation = Instance.new("Animation")
local CooldownFastAttack = 120
Attack = function()
	local ac = SeraphFrame.activeController
	if ac and ac.equipped then
		task.spawn(
			function()
				if tick() - cdnormal > 0.5 then
					ac:attack()
					cdnormal = tick()
				else
					Animation.AnimationId = ac.anims.basic[1]
					ac.humanoid:LoadAnimation(Animation):Play(1, 1)
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(CooldownFastAttack), 2, "")
				end
			end)
	end
end

b = tick()
spawn(function()
	while wait(0.059) do
		if _G.FastAttack then
			if b - tick() > 0.75 then
				wait(0.059)
				b = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
							Attack()
							wait(0.059)
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
	while wait(0.059) do
		if _G.FastAttack  then
			if k - tick() > 0.75 then
				wait(0.059)
				k = tick()
			end
			pcall(function()
				for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Humanoid.Health > 0 then
						if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
							wait(0.059)
							Unboost()
							game:GetService'VirtualUser':CaptureController()
							game:GetService'VirtualUser':Button1Down(Vector2.new(0,1,0,1))
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
							d:Play(0.25, 0.25, 0.25)
							h(i)
							b.play = shared.cpc
							wait(.5)
							d:Stop()
						end
					end
				end
			)
		end
	end
)

local CameRA = require(game:GetService("ReplicatedStorage").Util.CameraShaker)CameRA:Stop()
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
			game:GetService("RunService").Stepped:Connect(function()
				STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
					local Hits = STOPRL.getBladeHits(b,c,d)
					if Hits then
						if _G.FastAttack then
							STOP.play = function() end
							a:Play(0.1,0.1,0.1)
							func(Hits)
							STOP.play = shared.cpc
							wait(a.length * 0.5)
							a:Stop()
						else
							func(Hits)
							STOP.play = shared.cpc
							wait(a.length * 0.5)
							a:Stop()
						end
					end
				end
			end)
		end)
	end)
end)

Misc:AddToggle("Fast Tween",false,function(value)
	_G.FastTween = value
end)

Misc:AddToggle("Bring Mob",true,function(value)
	_G.Brimob = value
end)

----------------------------------------------------------------------------------------------------------------------------------------

Misc:AddSeperator("WhiteScreen")

Misc:AddToggle(" WhiteScreen",_G.WhiteScreen,function(value)

	_G.WhiteScreen = value

	if _G.WhiteScreen == true then
		game:GetService("RunService"):Set3dRenderingEnabled(false)
	elseif _G.WhiteScreen == false then
		game:GetService("RunService"):Set3dRenderingEnabled(true)
	end
end)

Misc:AddButton("FPS Booster",function()
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

----------------------------------------------------------------------------------------------------------------------------------------



----------------------------------------------------------------------------------------------------------------------------------------

Misc:AddButton("All Redeem Code",function()
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

----------------------------------------------------------------------------------------------------------------------------------------

Misc:AddSeperator("Server")

Misc:AddButton("Rejoin Server",function()
	game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end)

Misc:AddButton("Server Hop",function()
	Hop()
end)

Misc:AddButton("Hop To Lower Player",function()
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

----------------------------------------------------------------------------------------------------------------------------------------

Misc:AddSeperator("Gui")

Misc:AddButton("Delete Ui",function()
	game:GetService("CoreGui")["ManakeUiLib"]:destroy()
	game:GetService("CoreGui")["SOMEXGUI"]:destroy()
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

----------------------------------------------------------------------------------------------------------------------------------------


function Delete()
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
		game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
	end
	if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
		game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
	end
end

Delete()


----------------------------------------------------------------------------------------------------------------------------------------

while wait() do
	if _G.Auto_Farm_Level or _G.Auto_Farm_Chest or _G.Auto_Farm_Bone or _G.Auto_Cake_Prince or _G.Auto_Raid or _G.TeleportIsland or _G.Auto_Next or _G.Auto_New_World or _G.Auto_Third_World or _G.AutoElitehunter or _G.AutoBudySword or _G.AutoFarmBossHallow or _G.AutoFarmBossHallow or _G.AutoDarkDagger or _G.Auto_Electric_Claw or _G.Auto_Dragon_Talon or _G.Auto_God_Human or _G.AutoFarmSwanGlasses then
		if not game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI') then
			local Test = Instance.new('Highlight')
			Test.Name = "MAKEHI"
			Test.Enabled = true
			Test.FillColor = Color3.fromRGB(2, 197, 60)
			Test.OutlineColor = Color3.fromRGB(0, 181, 6)
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
