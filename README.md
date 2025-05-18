local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")
local player = Players.LocalPlayer

-- Função para criar o bloco
local function criarBloco()
	local bloco = Instance.new("Part")
	bloco.Size = Vector3.new(4, 4, 4)
	bloco.Position = player.Character and player.Character.HumanoidRootPart.Position + Vector3.new(0, 5, 0) or Vector3.new(0, 10, 0)
	bloco.Anchored = true
	bloco.BrickColor = BrickColor.Random()
	bloco.Parent = workspace
end

-- Detecta tecla pressionada
UserInputService.InputBegan:Connect(function(input, isProcessed)
	if isProcessed then return end -- Ignora se já foi processado por outro script

	if input.KeyCode == Enum.KeyCode.B then
		criarBloco()
	end
end)
