-- Espera até que o personagem esteja completamente carregado
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

-- Função para tornar o personagem invisível
local function tornarInvisivel()
    -- Espera o personagem ter a parte "HumanoidRootPart"
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    -- Torna as partes do personagem invisíveis e desativa a colisão
    for _, parte in pairs(character:GetChildren()) do
        if parte:IsA("BasePart") then
            parte.Transparency = 1  -- Torna a parte invisível
            parte.CanCollide = false  -- Desativa a colisão
        end
    end

    -- Opcional: Remover acessórios do personagem (chapéus, roupas, etc.)
    for _, acessorio in pairs(character:GetChildren()) do
        if acessorio:IsA("Accessory") then
            acessorio:Destroy()
        end
    end
end

-- Chama a função para tornar o personagem invisível assim que o personagem for carregado
tornarInvisivel()
# Script-Hub
