print('========\\//========')
print('==================')
print('Loading Key Verification...')

-- SPJ Services
local UserInputService = game:GetService("UserInputService")
local StarterGui = game:GetService("StarterGui")

-- Local API Keys (Replace with your actual keys)
local validKeys = {'TPS_Key', 'TPS_Key'}

-- Function to verify API Key
local function verifyApiKey(apiKey, callback)
    for _, key in pairs(validKeys) do
        if key == apiKey then
            callback(true)
            return
        end
    end
    callback(false)
end

-- Create Key Input Window
local function createKeyWindow()
    local ScreenGui = Instance.new("ScreenGui")
    local Frame = Instance.new("Frame")
    local TextBox = Instance.new("TextBox")
    local TextButton = Instance.new("TextButton")

    ScreenGui.Parent = game.Players.LocalPlayer.PlayerGui

    Frame.Parent = ScreenGui
    Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    Frame.Position = UDim2.new(0.5, -100, 0.5, -50)
    Frame.Size = UDim2.new(0, 200, 0, 100)

    TextBox.Parent = Frame
    TextBox.BackgroundColor3 = Color3.fromRGB(200, 200, 200)
    TextBox.Position = UDim2.new(0.1, 0, 0.2, 0)
    TextBox.Size = UDim2.new(0.8, 0, 0.3, 0)
    TextBox.PlaceholderText = "Enter The Key"

    TextButton.Parent = Frame
    TextButton.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
    TextButton.Position = UDim2.new(0.1, 0, 0.6, 0)
    TextButton.Size = UDim2.new(0.8, 0, 0.3, 0)
    TextButton.Text = "Verify"

    TextButton.MouseButton1Click:Connect(function()
        local apiKey = TextBox.Text
        verifyApiKey(apiKey, function(isValid)
            if isValid then
                StarterGui:SetCore("SendNotification", {
                    Title = "The Key Is Valid",
                    Text = "Access Granted. Loading script...",
                    Duration = 2
                })
                ScreenGui:Destroy()
                loadstring(game:HttpGet("https://raw.githubusercontent.com/akramthegoat/The-Real-One/refs/heads/main/Real", true))()
            else
                StarterGui:SetCore("SendNotification", {
                    Title = "API Key Invalid",
                    Text = "Invalid API Key. Please try again.",
                    Duration = 2
                })
            end
        end)
    end)
end

createKeyWindow() -- Show key window on start
