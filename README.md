-- Create the GUI
local screenGui = Instance.new("ScreenGui")
local frame = Instance.new("Frame")
local textLabel = Instance.new("TextLabel")

-- Properties for the GUI
screenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

frame.Size = UDim2.new(0, 300, 0, 200)
frame.Position = UDim2.new(0.5, -150, 0.5, -100)
frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
frame.Parent = screenGui

textLabel.Size = UDim2.new(1, 0, 0, 50)
textLabel.Position = UDim2.new(0, 0, 0, 0)
textLabel.Text = "team8x8x8x8 F3X GUI"
textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
textLabel.BackgroundTransparency = 1
textLabel.Parent = frame

-- Functions for F3X features
local function applySkybox()
    -- Add your skybox logic here
    local sky = Instance.new("Sky")
    sky.SkyboxBk = "rbxassetid://98888049206418" -- Replace with actual Skybox ID
    sky.SkyboxDn = "rbxassetid://98888049206418"
    sky.SkyboxFt = "rbxassetid://98888049206418"
    sky.SkyboxLf = "rbxassetid://98888049206418"
    sky.SkyboxRt = "rbxassetid://98888049206418"
    sky.SkyboxUp = "rbxassetid://98888049206418"
    sky.Parent = workspace
end

local function spawnDecals()
    for _, part in pairs(workspace:GetChildren()) do
        if part:IsA("BasePart") then
            local decal = Instance.new("Decal")
            decal.Texture = "rbxassetid://98888049206418" -- Replace with actual Decal ID
            decal.Parent = part
        end
    end
end

local function createFire()
    for _, part in pairs(workspace:GetChildren()) do
        if part:IsA("BasePart") then
            local fire = Instance.new("Fire")
            fire.Parent = part
        end
    end
end

local function killAll()
    for _, player in pairs(game.Players:GetPlayers()) do
        player.Character:BreakJoints()
    end
end

local function bigHead()
    for _, player in pairs(game.Players:GetPlayers()) do
        local head = player.Character:FindFirstChild("Head")
        if head then
            head.Size = Vector3.new(4, 4, 4) -- Make the head bigger
        end
    end
end

-- Create buttons
local skyboxButton = Instance.new("TextButton")
skyboxButton.Size = UDim2.new(0, 100, 0, 50)
skyboxButton.Position = UDim2.new(0, 10, 0, 60)
skyboxButton.Text = "Skybox"
skyboxButton.Parent = frame
skyboxButton.MouseButton1Click:Connect(applySkybox)

local decalButton = Instance.new("TextButton")
decalButton.Size = UDim2.new(0, 100, 0, 50)
decalButton.Position = UDim2.new(0, 120, 0, 60)
decalButton.Text = "Decal Spam"
decalButton.Parent = frame
decalButton.MouseButton1Click:Connect(spawnDecals)

local fireButton = Instance.new("TextButton")
fireButton.Size = UDim2.new(0, 100, 0, 50)
fireButton.Position = UDim2.new(0, 10, 0, 120)
fireButton.Text = "Fire All"
fireButton.Parent = frame
fireButton.MouseButton1Click:Connect(createFire)

local killButton = Instance.new("TextButton")
killButton.Size = UDim2.new(0, 100, 0, 50)
killButton.Position = UDim2.new(0, 120, 0, 120)
killButton.Text = "Kill All"
killButton.Parent = frame
killButton.MouseButton1Click:Connect(killAll)

local bigHeadButton = Instance.new("TextButton")
bigHeadButton.Size = UDim2.new(0, 100, 0, 50)
bigHeadButton.Position = UDim2.new(0, 10, 0, 180)
bigHeadButton.Text = "Big Head"
bigHeadButton.Parent = frame
bigHeadButton.MouseButton1Click:Connect(bigHead)
