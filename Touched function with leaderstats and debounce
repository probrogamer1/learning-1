local part = game.Workspace.Lavabrick
local coin = game.Workspace.coin
game.Players.PlayerAdded:Connect(function(player)
	local leaderstats = Instance.new("Folder")
	leaderstats.Parent = player
	leaderstats.Name = "leaderstats"
	local coins = Instance.new("IntValue")
	coins.Name = "Coins"
	coins.Value = 0
	coins.Parent = leaderstats
	print("leaderstats created")
	
end)

local function onTouch(hitpart)
	local character = hitpart.parent
	local humanoid = character:FindFirstChild("Humanoid")
	if humanoid then
		hitpart.parent.Humanoid.Health = 0
	end
end
local debounce = false
local function coincollect(hitpart)

	if debounce == true then return end
	local character = hitpart.parent
	local player = game.Players:GetPlayerFromCharacter(character)
	local leaderstats = player:WaitForChild("leaderstats")
	local coins = leaderstats:WaitForChild("Coins")
	if player then
		coins.Value += 5
		coin.Transparency = 1 
		coin.CanCollide = false
		debounce = true
		
		task.wait(10)
		
		coin.Transparency = 0
		coin.CanCollide = true
		debounce = false
		print("coin collected")
		
	end
	
	
end
part.Touched:Connect(onTouch)
coin.Touched:Connect(coincollect)


