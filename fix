
local player = game.Players.LocalPlayer

local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Lolosor/Alice/main/Orion"))()
local Window = OrionLib:MakeWindow({Name = "Alice Animations", HidePremium = false, SaveConfig = false, ConfigFolder = "OrionTest"})
OrionLib:Init()

-- Create the Toggle Screen GUI outside of Orion
local OrionScreenGui = game.CoreGui:FindFirstChild("Orion")

if not OrionScreenGui then
    warn("Orion ScreenGui not found")
    return
end

-- Define the toggle state
local isOffScreen = false

-- Function to toggle the Orion GUI on and off
local function ToggleScreenGui()
    OrionScreenGui.Enabled = not OrionScreenGui.Enabled
end

-- Create the Toggle Screen GUI outside of Orion
local ToggleScreenGu = Instance.new("ScreenGui")
ToggleScreenGu.Name = "Toggle"
ToggleScreenGu.ResetOnSpawn = false
ToggleScreenGu.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

-- Create the ImageButton (Toggle)
local Toggle = Instance.new("ImageButton")
Toggle.Name = "Toggle"
Toggle.Parent = ToggleScreenGu
Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Optional: Set background color if needed
Toggle.Position = UDim2.new(0.5, 170, -0.08, 0) -- Adjust the position as needed
Toggle.Size = UDim2.new(0, 40, 0, 40) -- Square size (change as needed)
Toggle.Image = "rbxassetid://70926775732023" -- The provided image ID
Toggle.Draggable = true -- Make the button draggable

-- Make the corners rounded (Optional)
local Corner = Instance.new("UICorner")
Corner.Parent = Toggle

-- Connect the ImageButton to toggle the Orion GUI
Toggle.MouseButton1Click:Connect(ToggleScreenGui)

-- Notification for successful loading
OrionLib:MakeNotification({
    Name = "Successfully Loaded",
    Content = "Enjoy My Friend!",
    Image = "rbxassetid://4483345998",
    Time = 5
})

-- Ensure the Humanoid is available before proceeding
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid") -- Wait until Humanoid is available

-- Example of animation loading with checks
local function playAnimation(animationId)
    if not humanoid then
        print("Humanoid not found!")
        return
    end

    local anim = Instance.new("Animation")
    anim.AnimationId = "rbxassetid://" .. animationId

    local playAnim = humanoid:LoadAnimation(anim)
    playAnim:Play()
end

-- Example usage of the playAnimation function
playAnimation("15957366251") -- Replace with the desired animation ID
