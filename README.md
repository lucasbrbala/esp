--[[ Script por ttk yt - espzin menu ]]--

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local Camera = workspace.CurrentCamera

-- CONFIGURAÇÕES
local aimbotAtivo = false
local fov = 100
local teamCheck = true

-- UI
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
ScreenGui.Name = "espzin"

local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 200, 0, 250)
Frame.Position = UDim2.new(0, 20, 0.5, -125)
Frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Frame.BorderSizePixel = 0
Frame.Active = true
Frame.Draggable = true

local Title = Instance.new("TextLabel", Frame)
Title.Text = "espzin"
Title.Size = UDim2.new(1, 0, 0, 30)
Title.TextColor3 = Color3.new(1,1,1)
Title.BackgroundColor3 = Color3.fromRGB(30,30,30)
Title.Font = Enum.Font.SourceSansBold
Title.TextSize = 20

local function criarBotao(nome, callback)
	local button = Instance.new("TextButton", Frame)
	button.Size = UDim2.new(1, -20, 0, 30)
	button.Position = UDim2.new(0, 10, 0, 40 + #Frame:GetChildren()*35)
	button.Text = nome
	button.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
	button.TextColor3 = Color3.new(1, 1, 1)
	button.Font = Enum.Font.SourceSans
	button.TextSize = 16
	button.MouseButton1Click:Connect(callback)
end

criarBotao("Ativar Aimbot", function()
	aimbotAtivo = not aimbotAtivo
end)

criarBotao("Aumentar FOV", function()
	fov = fov + 20
end)

criarBotao("Diminuir FOV", function()
	fov = math.max(20, fov - 20)
end)

-- FOV CÍRCULO
local fovCircle = Drawing.new("Circle")
fovCircle.Visible = true
fovCirc
