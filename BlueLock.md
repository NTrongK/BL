-- Load DrRay Library
local DrRayLibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/AZYsGithub/DrRay-UI-Library/main/DrRay.lua"))()
local window = DrRayLibrary:Load("Flows GUI by @NTrongK", "Default")  -- Custom window title

-- Flows Tab
local FlowsTab = DrRayLibrary.newTab("Flows", "")

-- Function to roll for the desired flow
local function rollFlow(flowName)
    local player = game.Players.LocalPlayer
    local flowService = game:GetService("ReplicatedStorage").Packages.Knit.Services.FlowService.RE.Spin

    while true do
        task.wait(0.3) -- Add a slight delay for performance
        if player:FindFirstChild("PlayerStats") and player.PlayerStats:FindFirstChild("Flow") then
            if player.PlayerStats.Flow.Value ~= flowName then
                flowService:FireServer()
            else
                print(flowName .. " Flow activated!")
                break -- Stop the loop when the flow is achieved
            end
        end
    end
end

-- Add buttons for each flow
flowsTab.newButton("Lightning", "Roll for Lightning Flow", function()
    rollFlow("Lightning")
end)

flowsTab.newButton("Puzzle", "Roll for Puzzle Flow", function()
    rollFlow("Puzzle")
end)

flowsTab.newButton("Monster", "Roll for Monster Flow", function()
    rollFlow("Monster")
end)

flowsTab.newButton("Gale Burst", "Roll for Gale Burst Flow", function()
    rollFlow("Gale Burst")
end)

flowsTab.newButton("Genius", "Roll for Genius Flow", function()
    rollFlow("Genius")
end)

flowsTab.newButton("Demon Wings", "Roll for DemonW Wings Flow", function()
    rollFlow("Demon Wings")
end)

flowsTab.newButton("Wild Card", "Roll for Will Card Flow", function()
    rollFlow("Will Card")
end)

flowsTab.newButton("Awakened Genius", "Roll for Awakened Genius Flow", function()
    rollFlow("Awakened Genius")
end)

-- Show the window
window:Show()
