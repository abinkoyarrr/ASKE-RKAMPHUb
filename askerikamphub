wait(0.5)

local Players = game:GetService("Players")
local StarterGui = game:GetService("StarterGui")
local UserInputService = game:GetService("UserInputService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Eski GUI sil
for _, v in pairs(playerGui:GetChildren()) do
    if v.Name == "AskeriKampPanel" then
        v:Destroy()
    end
end

-- Değişkenler
local flying = false
local flyConnection = nil
local isExercising = false
local isMinimized = false

-- Notification
local function notify(text)
    game.StarterGui:SetCore("SendNotification", {
        Title = "Askeri Kamp";
        Text = text;
        Duration = 3;
    })
end

-- Chat
local function chat(msg)
    if player.Character and player.Character:FindFirstChild("Head") then
        game:GetService("Chat"):Chat(player.Character.Head, msg)
    end
end

local function findUser(username)
    for _, p in pairs(Players:GetPlayers()) do
        if p.Name:lower():find(username:lower()) or p.DisplayName:lower():find(username:lower()) then
            return p
        end
    end
    return nil
end

-- TO Teleport fonksiyonu
local function teleportToUser(username)
    local targetPlayer = findUser(username)
    
    if not targetPlayer then
        notify("Kullanici bulunamadi!")
        return
    end
    
    if targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
        if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = targetPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3)
            notify("Isinlandin: " .. targetPlayer.Name)
        end
    else
        notify("Oyuncunun karakteri bulunamadi!")
    end
end

-- JJ
local function startJJ(count)
    if isExercising then return end
    isExercising = true
    
    spawn(function()
        local sayilar = {"BIR", "IKI", "UC", "DORT", "BES", "ALTI", "YEDI", "SEKIZ", "DOKUZ", "ON"}
        for i = 1, count do
            if not isExercising then break end
            
            if player.Character and player.Character:FindFirstChild("Humanoid") then
                player.Character.Humanoid.Jump = true
            end
            
            local sayi = sayilar[i] or tostring(i)
            chat(sayi)
            wait(1.2)
        end
        isExercising = false
    end)
end

-- GJ
local function startGJ(count)
    if isExercising then return end
    isExercising = true
    
    spawn(function()
        local sayilar = {"Bir.", "Iki.", "Uc.", "Dort.", "Bes.", "Alti.", "Yedi.", "Sekiz.", "Dokuz.", "On."}
        for i = 1, count do
            if not isExercising then break end
            
            if player.Character and player.Character:FindFirstChild("Humanoid") then
                player.Character.Humanoid.Jump = true
            end
            
            local sayi = sayilar[i] or (tostring(i) .. ".")
            chat(sayi)
            wait(1.2)
        end
        isExercising = false
    end)
end

-- GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "AskeriKampPanel"
screenGui.Parent = playerGui

local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 450, 0, 300)
mainFrame.Position = UDim2.new(0.5, -225, 0.5, -150)
mainFrame.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Parent = screenGui

-- Corner
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 10)
corner.Parent = mainFrame

-- Title Bar
local titleBar = Instance.new("Frame")
titleBar.Size = UDim2.new(1, 0, 0, 35)
titleBar.BackgroundColor3 = Color3.new(0.08, 0.08, 0.08)
titleBar.BorderSizePixel = 0
titleBar.Parent = mainFrame

local titleCorner = Instance.new("UICorner")
titleCorner.CornerRadius = UDim.new(0, 10)
titleCorner.Parent = titleBar

local titleMask = Instance.new("Frame")
titleMask.Size = UDim2.new(1, 0, 0, 15)
titleMask.Position = UDim2.new(0, 0, 0, 20)
titleMask.BackgroundColor3 = Color3.new(0.08, 0.08, 0.08)
titleMask.BorderSizePixel = 0
titleMask.Parent = titleBar

-- Title
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, -100, 1, 0)
title.Position = UDim2.new(0, 10, 0, 0)
title.BackgroundTransparency = 1
title.Text = "Askeri Kamp Hub"
title.TextColor3 = Color3.new(1, 1, 1)
title.TextSize = 12
title.Font = Enum.Font.SourceSansBold
title.TextXAlignment = Enum.TextXAlignment.Left
title.Parent = titleBar

-- Minimize Button
local minBtn = Instance.new("TextButton")
minBtn.Size = UDim2.new(0, 22, 0, 22)
minBtn.Position = UDim2.new(1, -50, 0, 6)
minBtn.BackgroundColor3 = Color3.new(0.6, 0.6, 0.2)
minBtn.Text = "-"
minBtn.TextColor3 = Color3.new(1, 1, 1)
minBtn.TextSize = 16
minBtn.BorderSizePixel = 0
minBtn.Parent = titleBar

local minBtnCorner = Instance.new("UICorner")
minBtnCorner.CornerRadius = UDim.new(0, 5)
minBtnCorner.Parent = minBtn

-- Close Button
local closeBtn = Instance.new("TextButton")
closeBtn.Size = UDim2.new(0, 22, 0, 22)
closeBtn.Position = UDim2.new(1, -25, 0, 6)
closeBtn.BackgroundColor3 = Color3.new(0.8, 0.2, 0.2)
closeBtn.Text = "X"
closeBtn.TextColor3 = Color3.new(1, 1, 1)
closeBtn.TextSize = 12
closeBtn.BorderSizePixel = 0
closeBtn.Parent = titleBar

local closeBtnCorner = Instance.new("UICorner")
closeBtnCorner.CornerRadius = UDim.new(0, 5)
closeBtnCorner.Parent = closeBtn

-- Left Panel
local leftPanel = Instance.new("Frame")
leftPanel.Size = UDim2.new(0, 120, 1, -35)
leftPanel.Position = UDim2.new(0, 0, 0, 35)
leftPanel.BackgroundColor3 = Color3.new(0.12, 0.12, 0.12)
leftPanel.BorderSizePixel = 0
leftPanel.Parent = mainFrame

-- Right Panel
local rightPanel = Instance.new("Frame")
rightPanel.Size = UDim2.new(1, -120, 1, -35)
rightPanel.Position = UDim2.new(0, 120, 0, 35)
rightPanel.BackgroundColor3 = Color3.new(0.15, 0.15, 0.15)
rightPanel.BorderSizePixel = 0
rightPanel.Parent = mainFrame

-- Content Frames
local homeFrame = Instance.new("Frame")
homeFrame.Size = UDim2.new(1, -10, 1, -10)
homeFrame.Position = UDim2.new(0, 5, 0, 5)
homeFrame.BackgroundTransparency = 1
homeFrame.Visible = true
homeFrame.Parent = rightPanel

local tpFrame = Instance.new("Frame")
tpFrame.Size = UDim2.new(1, -10, 1, -10)
tpFrame.Position = UDim2.new(0, 5, 0, 5)
tpFrame.BackgroundTransparency = 1
tpFrame.Visible = false
tpFrame.Parent = rightPanel

local playerFrame = Instance.new("Frame")
playerFrame.Size = UDim2.new(1, -10, 1, -10)
playerFrame.Position = UDim2.new(0, 5, 0, 5)
playerFrame.BackgroundTransparency = 1
playerFrame.Visible = false
playerFrame.Parent = rightPanel

local exerciseFrame = Instance.new("Frame")
exerciseFrame.Size = UDim2.new(1, -10, 1, -10)
exerciseFrame.Position = UDim2.new(0, 5, 0, 5)
exerciseFrame.BackgroundTransparency = 1
exerciseFrame.Visible = false
exerciseFrame.Parent = rightPanel

-- Tab Buttons
local homeBtn = Instance.new("TextButton")
homeBtn.Size = UDim2.new(1, -8, 0, 25)
homeBtn.Position = UDim2.new(0, 4, 0, 8)
homeBtn.BackgroundColor3 = Color3.new(0.2, 0.4, 0.8)
homeBtn.Text = "⌂ Anasayfa"
homeBtn.TextColor3 = Color3.new(1, 1, 1)
homeBtn.TextSize = 10
homeBtn.TextXAlignment = Enum.TextXAlignment.Left
homeBtn.BorderSizePixel = 0
homeBtn.Parent = leftPanel

local homeBtnCorner = Instance.new("UICorner")
homeBtnCorner.CornerRadius = UDim.new(0, 5)
homeBtnCorner.Parent = homeBtn

local tpBtn = Instance.new("TextButton")
tpBtn.Size = UDim2.new(1, -8, 0, 25)
tpBtn.Position = UDim2.new(0, 4, 0, 36)
tpBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
tpBtn.Text = "▶ Teleportlar"
tpBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
tpBtn.TextSize = 10
tpBtn.TextXAlignment = Enum.TextXAlignment.Left
tpBtn.BorderSizePixel = 0
tpBtn.Parent = leftPanel

local tpBtnCorner = Instance.new("UICorner")
tpBtnCorner.CornerRadius = UDim.new(0, 5)
tpBtnCorner.Parent = tpBtn

local playerBtn = Instance.new("TextButton")
playerBtn.Size = UDim2.new(1, -8, 0, 25)
playerBtn.Position = UDim2.new(0, 4, 0, 64)
playerBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
playerBtn.Text = "▶ TO - Fly"
playerBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
playerBtn.TextSize = 10
playerBtn.TextXAlignment = Enum.TextXAlignment.Left
playerBtn.BorderSizePixel = 0
playerBtn.Parent = leftPanel

local playerBtnCorner = Instance.new("UICorner")
playerBtnCorner.CornerRadius = UDim.new(0, 5)
playerBtnCorner.Parent = playerBtn

local toolBtn = Instance.new("TextButton")
toolBtn.Size = UDim2.new(1, -8, 0, 25)
toolBtn.Position = UDim2.new(0, 4, 0, 92)
toolBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
toolBtn.Text = "▶ Toollar"
toolBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
toolBtn.TextSize = 10
toolBtn.TextXAlignment = Enum.TextXAlignment.Left
toolBtn.BorderSizePixel = 0
toolBtn.Parent = leftPanel

local toolBtnCorner = Instance.new("UICorner")
toolBtnCorner.CornerRadius = UDim.new(0, 5)
toolBtnCorner.Parent = toolBtn

local exerciseBtn = Instance.new("TextButton")
exerciseBtn.Size = UDim2.new(1, -8, 0, 25)
exerciseBtn.Position = UDim2.new(0, 4, 0, 120)
exerciseBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
exerciseBtn.Text = "▶ Jacklar"
exerciseBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
exerciseBtn.TextSize = 10
exerciseBtn.TextXAlignment = Enum.TextXAlignment.Left
exerciseBtn.BorderSizePixel = 0
exerciseBtn.Parent = leftPanel

local exerciseBtnCorner = Instance.new("UICorner")
exerciseBtnCorner.CornerRadius = UDim.new(0, 5)
exerciseBtnCorner.Parent = exerciseBtn

local discordBtn = Instance.new("TextButton")
discordBtn.Size = UDim2.new(1, -8, 0, 25)
discordBtn.Position = UDim2.new(0, 4, 0, 148)
discordBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
discordBtn.Text = "▶ Discord"
discordBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
discordBtn.TextSize = 10
discordBtn.TextXAlignment = Enum.TextXAlignment.Left
discordBtn.BorderSizePixel = 0
discordBtn.Parent = leftPanel

local discordBtnCorner = Instance.new("UICorner")
discordBtnCorner.CornerRadius = UDim.new(0, 5)
discordBtnCorner.Parent = discordBtn

local otherBtn = Instance.new("TextButton")
otherBtn.Size = UDim2.new(1, -8, 0, 25)
otherBtn.Position = UDim2.new(0, 4, 0, 176)
otherBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
otherBtn.Text = "▶ Diger"
otherBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
otherBtn.TextSize = 10
otherBtn.TextXAlignment = Enum.TextXAlignment.Left
otherBtn.BorderSizePixel = 0
otherBtn.Parent = leftPanel

local otherBtnCorner = Instance.new("UICorner")
otherBtnCorner.CornerRadius = UDim.new(0, 5)
otherBtnCorner.Parent = otherBtn

-- HOME CONTENT
local homeTitle = Instance.new("TextLabel")
homeTitle.Size = UDim2.new(1, 0, 0, 25)
homeTitle.Position = UDim2.new(0, 0, 0, 10)
homeTitle.BackgroundTransparency = 1
homeTitle.Text = "Tum Askeri Kamplar"
homeTitle.TextColor3 = Color3.new(1, 1, 1)
homeTitle.TextSize = 14
homeTitle.Font = Enum.Font.SourceSansBold
homeTitle.Parent = homeFrame

local homeInfo = Instance.new("TextLabel")
homeInfo.Size = UDim2.new(1, 0, 0, 180)
homeInfo.Position = UDim2.new(0, 0, 0, 40)
homeInfo.BackgroundTransparency = 1
homeInfo.Text = "Kurucu: OWNEROFWORLDXD\nDost: KaanFriztche"
homeInfo.TextColor3 = Color3.new(0.9, 0.9, 0.9)
homeInfo.TextSize = 11
homeInfo.TextXAlignment = Enum.TextXAlignment.Left
homeInfo.TextYAlignment = Enum.TextYAlignment.Top
homeInfo.Parent = homeFrame

-- TELEPORT CONTENT
local waypoints = {
    {"Spawn", Vector3.new(0, 50, 0)},
    {"Merkez", Vector3.new(100, 50, 100)},
    {"Park", Vector3.new(-100, 50, 100)},
    {"Okul", Vector3.new(200, 50, -200)}
}

for i, wp in ipairs(waypoints) do
    local wpBtn = Instance.new("TextButton")
    wpBtn.Size = UDim2.new(0.45, 0, 0, 30)
    wpBtn.Position = UDim2.new(((i-1) % 2) * 0.52, 0, 0, math.floor((i-1) / 2) * 35 + 10)
    wpBtn.BackgroundColor3 = Color3.new(0.25, 0.25, 0.25)
    wpBtn.Text = wp[1]
    wpBtn.TextColor3 = Color3.new(1, 1, 1)
    wpBtn.TextSize = 11
    wpBtn.BorderSizePixel = 0
    wpBtn.Parent = tpFrame
    
    local wpBtnCorner = Instance.new("UICorner")
    wpBtnCorner.CornerRadius = UDim.new(0, 5)
    wpBtnCorner.Parent = wpBtn
    
    wpBtn.MouseButton1Click:Connect(function()
        if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(wp[2])
            notify("Teleport: " .. wp[1])
        end
    end)
end

-- PLAYER CONTENT
local flyBtn = Instance.new("TextButton")
flyBtn.Size = UDim2.new(1, 0, 0, 30)
flyBtn.Position = UDim2.new(0, 0, 0, 10)
flyBtn.BackgroundColor3 = Color3.new(0.2, 0.5, 0.8)
flyBtn.Text = "UCMA MODU"
flyBtn.TextColor3 = Color3.new(1, 1, 1)
flyBtn.TextSize = 11
flyBtn.BorderSizePixel = 0
flyBtn.Parent = playerFrame

local flyBtnCorner = Instance.new("UICorner")
flyBtnCorner.CornerRadius = UDim.new(0, 5)
flyBtnCorner.Parent = flyBtn

-- TO Input
local toLabel = Instance.new("TextLabel")
toLabel.Size = UDim2.new(1, 0, 0, 15)
toLabel.Position = UDim2.new(0, 0, 0, 50)
toLabel.BackgroundTransparency = 1
toLabel.Text = "Oyuncuya Isinlan (TO)"
toLabel.TextColor3 = Color3.new(1, 1, 1)
toLabel.TextSize = 10
toLabel.Font = Enum.Font.SourceSansBold
toLabel.TextXAlignment = Enum.TextXAlignment.Left
toLabel.Parent = playerFrame

local toInput = Instance.new("TextBox")
toInput.Size = UDim2.new(0.6, 0, 0, 25)
toInput.Position = UDim2.new(0, 0, 0, 70)
toInput.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
toInput.Text = ""
toInput.PlaceholderText = "Kullanici adi"
toInput.TextColor3 = Color3.new(1, 1, 1)
toInput.PlaceholderColor3 = Color3.new(0.6, 0.6, 0.6)
toInput.TextSize = 10
toInput.BorderSizePixel = 0
toInput.Parent = playerFrame

local toInputCorner = Instance.new("UICorner")
toInputCorner.CornerRadius = UDim.new(0, 3)
toInputCorner.Parent = toInput

local toBtn = Instance.new("TextButton")
toBtn.Size = UDim2.new(0.35, -5, 0, 25)
toBtn.Position = UDim2.new(0.65, 5, 0, 70)
toBtn.BackgroundColor3 = Color3.new(0.8, 0.4, 0.2)
toBtn.Text = "ISINLAN"
toBtn.TextColor3 = Color3.new(1, 1, 1)
toBtn.TextSize = 10
toBtn.BorderSizePixel = 0
toBtn.Parent = playerFrame

local toBtnCorner = Instance.new("UICorner")
toBtnCorner.CornerRadius = UDim.new(0, 3)
toBtnCorner.Parent = toBtn

-- EXERCISE CONTENT
local jjLabel = Instance.new("TextLabel")
jjLabel.Size = UDim2.new(1, 0, 0, 20)
jjLabel.Position = UDim2.new(0, 0, 0, 10)
jjLabel.BackgroundTransparency = 1
jjLabel.Text = "Jumping Jacks (JJ)"
jjLabel.TextColor3 = Color3.new(1, 1, 1)
jjLabel.TextSize = 12
jjLabel.Font = Enum.Font.SourceSansBold
jjLabel.TextXAlignment = Enum.TextXAlignment.Left
jjLabel.Parent = exerciseFrame

local jjInput = Instance.new("TextBox")
jjInput.Size = UDim2.new(0.25, 0, 0, 25)
jjInput.Position = UDim2.new(0, 0, 0, 35)
jjInput.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
jjInput.Text = "10"
jjInput.TextColor3 = Color3.new(1, 1, 1)
jjInput.TextSize = 11
jjInput.BorderSizePixel = 0
jjInput.Parent = exerciseFrame

local jjInputCorner = Instance.new("UICorner")
jjInputCorner.CornerRadius = UDim.new(0, 3)
jjInputCorner.Parent = jjInput

local jjBtn = Instance.new("TextButton")
jjBtn.Size = UDim2.new(0.7, -5, 0, 25)
jjBtn.Position = UDim2.new(0.3, 5, 0, 35)
jjBtn.BackgroundColor3 = Color3.new(0.2, 0.6, 0.2)
jjBtn.Text = "JJ Baslat"
jjBtn.TextColor3 = Color3.new(1, 1, 1)
jjBtn.TextSize = 11
jjBtn.BorderSizePixel = 0
jjBtn.Parent = exerciseFrame

local jjBtnCorner = Instance.new("UICorner")
jjBtnCorner.CornerRadius = UDim.new(0, 3)
jjBtnCorner.Parent = jjBtn

local gjLabel = Instance.new("TextLabel")
gjLabel.Size = UDim2.new(1, 0, 0, 20)
gjLabel.Position = UDim2.new(0, 0, 0, 70)
gjLabel.BackgroundTransparency = 1
gjLabel.Text = "Grammar Jacks (GJ)"
gjLabel.TextColor3 = Color3.new(1, 1, 1)
gjLabel.TextSize = 12
gjLabel.Font = Enum.Font.SourceSansBold
gjLabel.TextXAlignment = Enum.TextXAlignment.Left
gjLabel.Parent = exerciseFrame

local gjInput = Instance.new("TextBox")
gjInput.Size = UDim2.new(0.25, 0, 0, 25)
gjInput.Position = UDim2.new(0, 0, 0, 95)
gjInput.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
gjInput.Text = "10"
gjInput.TextColor3 = Color3.new(1, 1, 1)
gjInput.TextSize = 11
gjInput.BorderSizePixel = 0
gjInput.Parent = exerciseFrame

local gjInputCorner = Instance.new("UICorner")
gjInputCorner.CornerRadius = UDim.new(0, 3)
gjInputCorner.Parent = gjInput

local gjBtn = Instance.new("TextButton")
gjBtn.Size = UDim2.new(0.7, -5, 0, 25)
gjBtn.Position = UDim2.new(0.3, 5, 0, 95)
gjBtn.BackgroundColor3 = Color3.new(0.6, 0.2, 0.6)
gjBtn.Text = "GJ Baslat"
gjBtn.TextColor3 = Color3.new(1, 1, 1)
gjBtn.TextSize = 11
gjBtn.BorderSizePixel = 0
gjBtn.Parent = exerciseFrame

local gjBtnCorner = Instance.new("UICorner")
gjBtnCorner.CornerRadius = UDim.new(0, 3)
gjBtnCorner.Parent = gjBtn

local stopBtn = Instance.new("TextButton")
stopBtn.Size = UDim2.new(1, 0, 0, 25)
stopBtn.Position = UDim2.new(0, 0, 0, 130)
stopBtn.BackgroundColor3 = Color3.new(0.8, 0.2, 0.2)
stopBtn.Text = "DURDUR"
stopBtn.TextColor3 = Color3.new(1, 1, 1)
stopBtn.TextSize = 11
stopBtn.BorderSizePixel = 0
stopBtn.Parent = exerciseFrame

local stopBtnCorner = Instance.new("UICorner")
stopBtnCorner.CornerRadius = UDim.new(0, 3)
stopBtnCorner.Parent = stopBtn

-- Functions
local function switchTab(tab)
    -- Reset all buttons
    homeBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    homeBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    tpBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    tpBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    playerBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    playerBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    toolBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    toolBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    exerciseBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    exerciseBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    discordBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    discordBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    otherBtn.BackgroundColor3 = Color3.new(0.18, 0.18, 0.18)
    otherBtn.TextColor3 = Color3.new(0.8, 0.8, 0.8)
    
    homeFrame.Visible = false
    tpFrame.Visible = false
    playerFrame.Visible = false
    exerciseFrame.Visible = false
    
    if tab == 1 then
        homeBtn.BackgroundColor3 = Color3.new(0.2, 0.4, 0.8)
        homeBtn.TextColor3 = Color3.new(1, 1, 1)
        homeFrame.Visible = true
    elseif tab == 2 then
        tpBtn.BackgroundColor3 = Color3.new(0.2, 0.4, 0.8)
        tpBtn.TextColor3 = Color3.new(1, 1, 1)
        tpFrame.Visible = true
    elseif tab == 3 then
        playerBtn.BackgroundColor3 = Color3.new(0.2, 0.4, 0.8)
        playerBtn.TextColor3 = Color3.new(1, 1, 1)
        playerFrame.Visible = true
    elseif tab == 4 then
        exerciseBtn.BackgroundColor3 = Color3.new(0.2, 0.4, 0.8)
        exerciseBtn.TextColor3 = Color3.new(1, 1, 1)
        exerciseFrame.Visible = true
    end
end

local function toggleFly()
    flying = not flying
    
    if flying then
        if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            local rootPart = player.Character.HumanoidRootPart
            local humanoid = player.Character.Humanoid
            
            humanoid.PlatformStand = true
            
            local bodyVelocity = Instance.new("BodyVelocity")
            bodyVelocity.MaxForce = Vector3.new(4000, 4000, 4000)
            bodyVelocity.Velocity = Vector3.new(0, 0, 0)
            bodyVelocity.Parent = rootPart
            
            flyConnection = game:GetService("RunService").Heartbeat:Connect(function()
                if not flying then return end
                
                local camera = workspace.CurrentCamera
                local moveVector = Vector3.new(0, 0, 0)
                
                if UserInputService:IsKeyDown(Enum.KeyCode.W) then
                    moveVector = moveVector + camera.CFrame.LookVector
                end
                if UserInputService:IsKeyDown(Enum.KeyCode.S) then
                    moveVector = moveVector - camera.CFrame.LookVector
                end
              
