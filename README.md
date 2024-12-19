-- Danxhub resolution

-- Função para ajustar a resolução da tela
function adjustResolution(desiredWidth, desiredHeight)
    local player = game.Players.LocalPlayer
    local screenGui = Instance.new("ScreenGui", player.PlayerGui)
    local frame = Instance.new("Frame", screenGui)

    -- Configura a resolução desejada
    frame.Size = UDim2.new(0, desiredWidth, 0, desiredHeight)
    frame.Position = UDim2.new(0.5, -desiredWidth / 2, 0.5, -desiredHeight / 2)
    frame.BackgroundTransparency = 1 -- Torna o frame invisível

    -- Ajusta a escala da tela
    local scaleX = desiredWidth / workspace.CurrentCamera.ViewportSize.X
    local scaleY = desiredHeight / workspace.CurrentCamera.ViewportSize.Y
    workspace.CurrentCamera.ViewportSize = Vector2.new(desiredWidth, desiredHeight)
    frame.Size = UDim2.new(scaleX, 0, scaleY, 0)
end

-- Exemplo de uso da função
adjustResolution(1920, 1080)
