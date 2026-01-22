# Namcuto.lua
-- -- SCRIPT NAMCUTO-VIP PRO (FULL FUNCTIONS & OVERRIDE 2026)
local plr = game:GetService("Players").LocalPlayer
local Library = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local OpenBtn = Instance.new("TextButton")

Library.Name = "NamCutoVip_Pro_2026_Full"
Library.Parent = plr:WaitForChild("PlayerGui")
Library.ResetOnSpawn = false

-- NÚT MỞ LẠI (NÚT NHỎ KHI ẨN)
OpenBtn.Name = "RestoreButton"
OpenBtn.Parent = Library
OpenBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 0)
OpenBtn.Position = UDim2.new(0, 10, 0.4, 0)
OpenBtn.Size = UDim2.new(0, 45, 0, 45)
OpenBtn.Text = "N"
OpenBtn.Visible = false
local CornerBtn = Instance.new("UICorner", OpenBtn)
CornerBtn.CornerRadius = UDim.new(0, 50)

-- KHUNG CHÍNH
MainFrame.Name = "MainFrame"
MainFrame.Parent = Library
MainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
MainFrame.Position = UDim2.new(0.5, -125, 0.2, 0)
MainFrame.Size = UDim2.new(0, 250, 0, 580) 
MainFrame.Active = true
MainFrame.Draggable = true
Instance.new("UICorner", MainFrame)

Title.Parent = MainFrame
Title.Size = UDim2.new(1, 0, 0, 40)
Title.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Title.Text = "NAMCUTO-VIP PRO V4" 
Title.TextColor3 = Color3.fromRGB(255, 255, 0)
Title.TextSize = 18
Title.Font = Enum.Font.SourceSansBold

-- [MỤC 1] XÂM CHIẾM THẾ GIỚI
local IdInput = Instance.new("TextBox", MainFrame)
IdInput.PlaceholderText = "ID Ảnh..."
IdInput.Text = "111495121127546"
IdInput.Size = UDim2.new(0.8, 0, 0, 30)
IdInput.Position = UDim2.new(0.1, 0, 0.08, 0)
IdInput.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
IdInput.TextColor3 = Color3.fromRGB(255, 255, 255)

local ChangeBtn = Instance.new("TextButton", MainFrame)
ChangeBtn.Text = "XÂM CHIẾM TOÀN BỘ"
ChangeBtn.Size = UDim2.new(0.8, 0, 0, 35)
ChangeBtn.Position = UDim2.new(0.1, 0, 0.15, 0)
ChangeBtn.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
ChangeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
ChangeBtn.MouseButton1Click:Connect(function()
    local id = "rbxassetid://" .. IdInput.Text
    pcall(function()
        local sky = game:GetService("Lighting"):FindFirstChildOfClass("Sky") or Instance.new("Sky", game:GetService("Lighting"))
        sky.SkyboxBk = id sky.SkyboxDn = id sky.SkyboxFt = id
        sky.SkyboxLf = id sky.SkyboxRt = id sky.SkyboxUp = id
        local function apply(parent)
            for _, v in pairs(parent:GetDescendants()) do
                pcall(function()
                    if v:IsA("BasePart") then
                        for _, face in pairs(Enum.NormalId:GetEnumItems()) do
                            local d = Instance.new("Decal", v) d.Texture = id d.Face = face
                        end
                    elseif v:IsA("ImageLabel") or v:IsA("ImageButton") then v.Image = id
                    elseif v:IsA("MeshPart") then v.TextureID = id
                    end
                end)
            end
        end
        apply(workspace)
        apply(plr.PlayerGui)
        pcall(function() apply(game:GetService("CoreGui")) end)
    end)
end)

-- [MỤC 2] BAY (ĐÃ FIX LINK)
local FlyBtn = Instance.new("TextButton", MainFrame)
FlyBtn.Text = "Bật/Tắt Bay"
FlyBtn.Size = UDim2.new(0.8, 0, 0, 35)
FlyBtn.Position = UDim2.new(0.1, 0, 0.23, 0)
FlyBtn.BackgroundColor3 = Color3.fromRGB(0, 120, 255)
FlyBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
FlyBtn.MouseButton1Click:Connect(function()
    pcall(function() 
        loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/FlyGuiV3/main/FlyGuiV3.txt"))() 
    end)
end)

-- [MỤC 3] TÀNG HÌNH V2
local InviBtn = Instance.new("TextButton", MainFrame)
InviBtn.Text = "Tàng Hình V2"
InviBtn.Size = UDim2.new(0.8, 0, 0, 35)
InviBtn.Position = UDim2.new(0.1, 0, 0.31, 0)
InviBtn.BackgroundColor3 = Color3.fromRGB(80, 80, 80)
InviBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
InviBtn.MouseButton1Click:Connect(function()
    pcall(function() 
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Awesome-Invisible-man-21074"))() 
    end)
end)

-- [MỤC 4] FLING VŨ
local FlingBtn = Instance.new("TextButton", MainFrame)
FlingBtn.Text = "Fling Vũ"
FlingBtn.Size = UDim2.new(0.8, 0, 0, 35)
FlingBtn.Position = UDim2.new(0.1, 0, 0.39, 0)
FlingBtn.BackgroundColor3 = Color3.fromRGB(255, 100, 0)
FlingBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
FlingBtn.MouseButton1Click:Connect(function()
    pcall(function() 
        loadstring(game:HttpGet("https://raw.githubusercontent.com/long191910/all-my-roblox-script/refs/heads/main/touchfling.lua"))() 
    end)
end)

-- [MỤC 5] ADMIN (IY)
local IYBtn = Instance.new("TextButton", MainFrame)
IYBtn.Text = "Mở Admin (IY)"
IYBtn.Size = UDim2.new(0.8, 0, 0, 35)
IYBtn.Position = UDim2.new(0.1, 0, 0.47, 0)
IYBtn.BackgroundColor3 = Color3.fromRGB(138, 43, 226)
IYBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
IYBtn.MouseButton1Click:Connect(function()
    pcall(function() loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))() end)
end)

-- [MỤC 6] NÚT CẶC (ĐÃ CẬP NHẬT LỆNH MỚI)
local CacBtn = Instance.new("TextButton", MainFrame)
CacBtn.Text = "Cặc"
CacBtn.Size = UDim2.new(0.8, 0, 0, 35)
CacBtn.Position = UDim2.new(0.1, 0, 0.55, 0)
CacBtn.BackgroundColor3 = Color3.fromRGB(100, 0, 150)
CacBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
CacBtn.MouseButton1Click:Connect(function()
    pcall(function() 
        loadstring(game:HttpGet("https://pastefy.app/wa3v2Vgm/raw"))("Spider Script")
    end)
end)

-- [HỆ THỐNG] ẨN & ĐÓNG
local HideBtn = Instance.new("TextButton", MainFrame)
HideBtn.Text = "ẨN MENU"
HideBtn.Size = UDim2.new(0.8, 0, 0, 35)
HideBtn.Position = UDim2.new(0.1, 0, 0.75, 0)
HideBtn.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
HideBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
HideBtn.MouseButton1Click:Connect(function()
    MainFrame.Visible = false
    OpenBtn.Visible = true
end)

OpenBtn.MouseButton1Click:Connect(function()
    MainFrame.Visible = true
    OpenBtn.Visible = false
end)

local CloseBtn = Instance.new("TextButton", MainFrame)
CloseBtn.Text = "X"
CloseBtn.Size = UDim2.new(0, 35, 0, 35)
CloseBtn.Position = UDim2.new(1, -40, 0, 2)
CloseBtn.BackgroundColor3 = Color3.fromRGB(200, 0, 0)
CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseBtn.MouseButton1Click:Connect(function() Library:Destroy() end)
