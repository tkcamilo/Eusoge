-- Sistema de Key - Tema Negro/Rosa
-- Key: 301451

local Players = game:GetService("Players")
local Player = Players.LocalPlayer
local GuiService = game:GetService("GuiService")

-- Interface com tema negro/rosa
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = Player.PlayerGui
ScreenGui.Name = "KeySystemBlackPink"
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.ResetOnSpawn = false
ScreenGui.IgnoreGuiInset = true -- Importante para celular

-- Fundo semi-transparente
local Background = Instance.new("Frame")
Background.Size = UDim2.new(1, 0, 1, 0)
Background.Position = UDim2.new(0, 0, 0, 0)
Background.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Background.BackgroundTransparency = 0.4
Background.BorderSizePixel = 0
Background.Parent = ScreenGui

-- Janela principal (centralizada no celular)
local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0.85, 0, 0.7, 0) -- 85% da largura, 70% da altura
MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
MainFrame.AnchorPoint = Vector2.new(0.5, 0.5) -- Centraliza perfeitamente
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 25) -- Preto escuro
MainFrame.BorderSizePixel = 0
MainFrame.Parent = ScreenGui

-- Borda rosa
local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 20)
UICorner.Parent = MainFrame

local UIStroke = Instance.new("UIStroke")
UIStroke.Color = Color3.fromRGB(255, 105, 180) -- Rosa forte
UIStroke.Thickness = 3
UIStroke.Parent = MainFrame

-- Cabeçalho rosa
local Header = Instance.new("Frame")
Header.Size = UDim2.new(1, 0, 0.22, 0)
Header.Position = UDim2.new(0, 0, 0, 0)
Header.BackgroundColor3 = Color3.fromRGB(255, 105, 180) -- Rosa
Header.BorderSizePixel = 0
Header.Parent = MainFrame

local HeaderCorner = Instance.new("UICorner")
HeaderCorner.CornerRadius = UDim.new(0, 20)
HeaderCorner.Parent = Header

-- Gradiente no cabeçalho
local HeaderGradient = Instance.new("UIGradient")
HeaderGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 105, 180)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 20, 147))
})
HeaderGradient.Rotation = 45
HeaderGradient.Parent = Header

-- Título
local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, -40, 0.6, 0)
Title.Position = UDim2.new(0, 20, 0.1, 0)
Title.BackgroundTransparency = 1
Title.Text = "🔐 VERIFICAÇÃO"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 22
Title.Parent = Header

-- Subtítulo
local Subtitle = Instance.new("TextLabel")
Subtitle.Size = UDim2.new(1, -40, 0.3, 0)
Subtitle.Position = UDim2.new(0, 20, 0.6, 0)
Subtitle.BackgroundTransparency = 1
Subtitle.Text = "Digite a key de ativação"
Subtitle.TextColor3 = Color3.fromRGB(255, 255, 255)
Subtitle.Font = Enum.Font.Gotham
Subtitle.TextSize = 16
Subtitle.TextTransparency = 0.3
Subtitle.Parent = Header

-- Área de conteúdo
local Content = Instance.new("Frame")
Content.Size = UDim2.new(1, -30, 0.68, 0)
Content.Position = UDim2.new(0, 15, 0.25, 0)
Content.BackgroundTransparency = 1
Content.Parent = MainFrame

-- Instrução
local Instruction = Instance.new("TextLabel")
Instruction.Size = UDim2.new(1, 0, 0.12, 0)
Instruction.Position = UDim2.new(0, 0, 0, 0)
Instruction.BackgroundTransparency = 1
Instruction.Text = "Para obter a key, acesse:"
Instruction.TextColor3 = Color3.fromRGB(200, 200, 220)
Instruction.Font = Enum.Font.Gotham
Instruction.TextSize = 16
Instruction.TextXAlignment = Enum.TextXAlignment.Left
Instruction.Parent = Content

-- Botão para copiar link
local LinkButton = Instance.new("TextButton")
LinkButton.Size = UDim2.new(1, 0, 0.18, 0)
LinkButton.Position = UDim2.new(0, 0, 0.13, 0)
LinkButton.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
LinkButton.Text = "🔗 https://mineurl.com/777356"
LinkButton.TextColor3 = Color3.fromRGB(255, 182, 193) -- Rosa claro
LinkButton.Font = Enum.Font.GothamMedium
LinkButton.TextSize = 14
LinkButton.TextXAlignment = Enum.TextXAlignment.Left
LinkButton.Parent = Content

local LinkCorner = Instance.new("UICorner")
LinkCorner.CornerRadius = UDim.new(0, 10)
LinkCorner.Parent = LinkButton

-- Campo para digitar a key
local KeyLabel = Instance.new("TextLabel")
KeyLabel.Size = UDim2.new(1, 0, 0.12, 0)
KeyLabel.Position = UDim2.new(0, 0, 0.34, 0)
KeyLabel.BackgroundTransparency = 1
KeyLabel.Text = "Digite a key aqui:"
KeyLabel.TextColor3 = Color3.fromRGB(200, 200, 220)
KeyLabel.Font = Enum.Font.Gotham
KeyLabel.TextSize = 16
KeyLabel.TextXAlignment = Enum.TextXAlignment.Left
KeyLabel.Parent = Content

local KeyInput = Instance.new("TextBox")
KeyInput.Size = UDim2.new(1, 0, 0.22, 0)
KeyInput.Position = UDim2.new(0, 0, 0.47, 0)
KeyInput.BackgroundColor3 = Color3.fromRGB(30, 30, 40)
KeyInput.TextColor3 = Color3.fromRGB(255, 255, 255)
KeyInput.Font = Enum.Font.GothamBold
KeyInput.TextSize = 20
KeyInput.PlaceholderText = "••••••"
KeyInput.PlaceholderColor3 = Color3.fromRGB(100, 100, 120)
KeyInput.Text = ""
KeyInput.Parent = Content

local InputCorner = Instance.new("UICorner")
InputCorner.CornerRadius = UDim.new(0, 12)
InputCorner.Parent = KeyInput

local InputStroke = Instance.new("UIStroke")
InputStroke.Color = Color3.fromRGB(255, 105, 180)
InputStroke.Thickness = 2
InputStroke.Parent = KeyInput

-- Botão de ativar (GRANDE para celular)
local ActivateButton = Instance.new("TextButton")
ActivateButton.Size = UDim2.new(1, 0, 0.22, 0)
ActivateButton.Position = UDim2.new(0, 0, 0.72, 0)
ActivateButton.BackgroundColor3 = Color3.fromRGB(255, 105, 180)
ActivateButton.Text = "✨ ATIVAR SCRIPT"
ActivateButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ActivateButton.Font = Enum.Font.GothamBold
ActivateButton.TextSize = 18
ActivateButton.Parent = Content

local ActivateCorner = Instance.new("UICorner")
ActivateCorner.CornerRadius = UDim.new(0, 15)
ActivateCorner.Parent = ActivateButton

-- Gradiente no botão
local ActivateGradient = Instance.new("UIGradient")
ActivateGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 105, 180)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 20, 147))
})
ActivateGradient.Parent = ActivateButton

-- Mensagem de status
local MessageLabel = Instance.new("TextLabel")
MessageLabel.Size = UDim2.new(1, 0, 0.15, 0)
MessageLabel.Position = UDim2.new(0, 0, 0.96, 0)
MessageLabel.BackgroundTransparency = 1
MessageLabel.Text = ""
MessageLabel.TextColor3 = Color3.fromRGB(255, 105, 180)
MessageLabel.Font = Enum.Font.Gotham
MessageLabel.TextSize = 14
MessageLabel.TextWrapped = true
MessageLabel.Parent = Content

-- Botão de fechar (X rosa)
local CloseButton = Instance.new("TextButton")
CloseButton.Size = UDim2.new(0, 35, 0, 35)
CloseButton.Position = UDim2.new(1, -40, 0, 10)
CloseButton.BackgroundTransparency = 1
CloseButton.Text = "✕"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.Font = Enum.Font.GothamBold
CloseButton.TextSize = 22
CloseButton.Parent = Header

-- Ícone decorativo
local KeyIcon = Instance.new("ImageLabel")
KeyIcon.Size = UDim2.new(0, 25, 0, 25)
KeyIcon.Position = UDim2.new(0, 20, 0.5, -12)
KeyIcon.BackgroundTransparency = 1
KeyIcon.Image = "rbxassetid://3926305904"
KeyIcon.ImageRectOffset = Vector2.new(964, 324)
KeyIcon.ImageRectSize = Vector2.new(36, 36)
KeyIcon.ImageColor3 = Color3.fromRGB(255, 255, 255)
KeyIcon.Parent = LinkButton

-- Função para executar o script
local function ExecuteScript()
    MessageLabel.Text = "⏳ Verificando key..."
    MessageLabel.TextColor3 = Color3.fromRGB(255, 215, 0) -- Amarelo
    
    ActivateButton.Text = "⏳ VERIFICANDO..."
    ActivateButton.BackgroundColor3 = Color3.fromRGB(255, 215, 0)
    
    wait(1.5)
    
    -- Executar seu script
    loadstring(game:HttpGet('https://raw.githubusercontent.com/ltseverydayyou/uuuuuuu/refs/heads/main/PhantomBallz.luau'))()
    
    MessageLabel.Text = "✅ Script ativado com sucesso!"
    MessageLabel.TextColor3 = Color3.fromRGB(50, 205, 50) -- Verde
    
    ActivateButton.Text = "✅ ATIVADO"
    ActivateButton.BackgroundColor3 = Color3.fromRGB(50, 205, 50)
    
    wait(2)
    ScreenGui:Destroy()
end

-- Função para verificar a key
local function CheckKey(input)
    return tostring(input):gsub("%s+", "") == "301451"
end

-- Botão ATIVAR
ActivateButton.MouseButton1Click:Connect(function()
    local userInput = KeyInput.Text
    
    if CheckKey(userInput) then
        MessageLabel.Text = "✅ Key correta! Ativando..."
        MessageLabel.TextColor3 = Color3.fromRGB(50, 205, 50)
        
        -- Efeito visual de sucesso
        for i = 1, 3 do
            KeyInput.BackgroundColor3 = Color3.fromRGB(50, 205, 50)
            wait(0.15)
            KeyInput.BackgroundColor3 = Color3.fromRGB(30, 30, 40)
            wait(0.15)
        end
        
        ExecuteScript()
    else
        MessageLabel.Text = "❌ Key incorreta! Acesse o link acima para obter a key."
        MessageLabel.TextColor3 = Color3.fromRGB(255, 69, 0) -- Vermelho laranja
        
        -- Efeito de erro
        KeyInput.BackgroundColor3 = Color3.fromRGB(255, 69, 0)
        wait(0.3)
        KeyInput.BackgroundColor3 = Color3.fromRGB(30, 30, 40)
        
        -- Piscar o botão do link
        LinkButton.BackgroundColor3 = Color3.fromRGB(255, 105, 180)
        wait(0.2)
        LinkButton.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
    end
end)

-- Botão COPIAR LINK
LinkButton.MouseButton1Click:Connect(function()
    -- Copiar para área de transferência
    pcall(function()
        setclipboard("https://mineurl.com/777356")
    end)
    
    -- Feedback visual
    local originalText = LinkButton.Text
    LinkButton.Text = "✅ Link copiado!"
    LinkButton.BackgroundColor3 = Color3.fromRGB(50, 205, 50)
    
    MessageLabel.Text = "📋 Link copiado! Cole no navegador."
    MessageLabel.TextColor3 = Color3.fromRGB(100, 200, 255)
    
    wait(1.5)
    
    LinkButton.Text = originalText
    LinkButton.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
    
    MessageLabel.Text = ""
end)

-- Botão FECHAR
CloseButton.MouseButton1Click:Connect(function()
    -- Animação de fechar
    for i = 1, 10 do
        MainFrame.Size = MainFrame.Size * UDim2.new(0.9, 0, 0.9, 0)
        MainFrame.BackgroundTransparency = i / 10
        wait(0.02)
    end
    ScreenGui:Destroy()
end)

-- Efeitos de hover
ActivateButton.MouseEnter:Connect(function()
    ActivateButton.Size = UDim2.new(1.02, 0, 0.23, 0)
    ActivateButton.Position = UDim2.new(-0.01, 0, 0.715, 0)
end)

ActivateButton.MouseLeave:Connect(function()
    ActivateButton.Size = UDim2.new(1, 0, 0.22, 0)
    ActivateButton.Position = UDim2.new(0, 0, 0.72, 0)
end)

LinkButton.MouseEnter:Connect(function()
    LinkButton.BackgroundColor3 = Color3.fromRGB(50, 50, 60)
end)

LinkButton.MouseLeave:Connect(function()
    LinkButton.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
end)

-- Foco automático no campo
wait(0.5)
KeyInput:CaptureFocus()

-- Ajustar para diferentes orientações
local function UpdateOrientation()
    local viewport = workspace.CurrentCamera.ViewportSize
    
    if viewport.X > viewport.Y then
        -- Paisagem
        MainFrame.Size = UDim2.new(0.65, 0, 0.8, 0)
    else
        -- Retrato
        MainFrame.Size = UDim2.new(0.85, 0, 0.7, 0)
    end
    
    -- Re-centralizar
    MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
end

-- Ajustar quando a tela mudar
workspace.CurrentCamera:GetPropertyChangedSignal("ViewportSize"):Connect(UpdateOrientation)

-- Ajuste inicial
UpdateOrientation()

-- Animação de entrada
MainFrame.Size = UDim2.new(0.1, 0, 0.1, 0)
MainFrame.BackgroundTransparency = 1

for i = 1, 10 do
    local size = UDim2.new(0.1 + (i * 0.075), 0, 0.1 + (i * 0.06), 0)
    MainFrame.Size = size
    MainFrame.BackgroundTransparency = 1 - (i / 10)
    wait(0.02)
end

-- Aplicar tamanho final
UpdateOrientation()

-- Garantir que fique no topo
ScreenGui.DisplayOrder = 999
