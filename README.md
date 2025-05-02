-- Criando a GUI local
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local TopBar = Instance.new("Frame")
local CloseButton = Instance.new("TextButton")
local Title = Instance.new("TextLabel")
local InputFrame = Instance.new("Frame")
local InputBox = Instance.new("TextBox")
local InputLabel = Instance.new("TextLabel")
local AutoJJsButton = Instance.new("TextButton")
local StatusLabel = Instance.new("TextLabel")
local UICorner_Main = Instance.new("UICorner")
local UICorner_TopBar = Instance.new("UICorner")
local UICorner_InputFrame = Instance.new("UICorner")
local UICorner_Button = Instance.new("UICorner")
local UICorner_Input = Instance.new("UICorner")
local UIStroke_Main = Instance.new("UIStroke")
local UIStroke_Input = Instance.new("UIStroke")
local UIGradient = Instance.new("UIGradient")

-- Configurando a GUI
ScreenGui.Name = "AutoJJsGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.ResetOnSpawn = false

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
MainFrame.Size = UDim2.new(0, 400, 0, 300)
MainFrame.Position = UDim2.new(0.5, -200, 0.5, -150)
MainFrame.Active = true
MainFrame.Draggable = true
UICorner_Main.Parent = MainFrame
UICorner_Main.CornerRadius = UDim.new(0, 10)

UIStroke_Main.Parent = MainFrame
UIStroke_Main.Color = Color3.fromRGB(0, 170, 255)
UIStroke_Main.Thickness = 2
UIStroke_Main.ApplyStrokeMode = Enum.ApplyStrokeMode.Border

-- Barra superior
TopBar.Name = "TopBar"
TopBar.Parent = MainFrame
TopBar.BackgroundColor3 = Color3.fromRGB(0, 140, 230)
TopBar.Size = UDim2.new(1, 0, 0, 40)
TopBar.Position = UDim2.new(0, 0, 0, 0)
UICorner_TopBar.Parent = TopBar
UICorner_TopBar.CornerRadius = UDim.new(0, 10)

UIGradient.Parent = TopBar
UIGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(0, 170, 255)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(0, 120, 210))
})
UIGradient.Rotation = 45

CloseButton.Name = "CloseButton"
CloseButton.Parent = TopBar
CloseButton.BackgroundColor3 = Color3.fromRGB(255, 70, 70)
CloseButton.Size = UDim2.new(0, 25, 0, 25)
CloseButton.Position = UDim2.new(1, -32, 0.5, -12.5)
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.Font = Enum.Font.GothamBold
CloseButton.TextSize = 14
CloseButton.AutoButtonColor = true
Instance.new("UICorner").Parent = CloseButton

Title.Name = "Title"
Title.Parent = TopBar
Title.BackgroundTransparency = 1
Title.Size = UDim2.new(1, -70, 1, 0)
Title.Position = UDim2.new(0, 15, 0, 0)
Title.Text = "Auto JJs"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 20
Title.TextXAlignment = Enum.TextXAlignment.Left

-- Frame para Input
InputFrame.Name = "InputFrame"
InputFrame.Parent = MainFrame
InputFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 45)
InputFrame.Size = UDim2.new(0, 350, 0, 180)
InputFrame.Position = UDim2.new(0.5, -175, 0.5, -60)
UICorner_InputFrame.Parent = InputFrame
UICorner_InputFrame.CornerRadius = UDim.new(0, 8)

InputLabel.Name = "InputLabel"
InputLabel.Parent = InputFrame
InputLabel.BackgroundTransparency = 1
InputLabel.Size = UDim2.new(1, -30, 0, 30)
InputLabel.Position = UDim2.new(0, 15, 0, 15)
InputLabel.Text = "Digite quantos JJs você quer:"
InputLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
InputLabel.Font = Enum.Font.Gotham
InputLabel.TextSize = 16
InputLabel.TextXAlignment = Enum.TextXAlignment.Left

InputBox.Name = "InputBox"
InputBox.Parent = InputFrame
InputBox.BackgroundColor3 = Color3.fromRGB(50, 50, 55)
InputBox.Size = UDim2.new(0, 200, 0, 35)
InputBox.Position = UDim2.new(0, 15, 0, 55)
InputBox.Font = Enum.Font.Gotham
InputBox.TextSize = 16
InputBox.PlaceholderText = "Ex: 5"
InputBox.TextColor3 = Color3.fromRGB(255, 255, 255)
InputBox.PlaceholderColor3 = Color3.fromRGB(180, 180, 180)
UICorner_Input.Parent = InputBox
UICorner_Input.CornerRadius = UDim.new(0, 6)

UIStroke_Input.Parent = InputBox
UIStroke_Input.Color = Color3.fromRGB(80, 80, 85)
UIStroke_Input.Thickness = 1

AutoJJsButton.Name = "AutoJJsButton"
AutoJJsButton.Parent = InputFrame
AutoJJsButton.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
AutoJJsButton.Size = UDim2.new(0, 200, 0, 40)
AutoJJsButton.Position = UDim2.new(0, 15, 0, 105)
AutoJJsButton.Text = "ATIVAR"
AutoJJsButton.TextColor3 = Color3.fromRGB(255, 255, 255)
AutoJJsButton.Font = Enum.Font.GothamBold
AutoJJsButton.TextSize = 18
AutoJJsButton.AutoButtonColor = true
UICorner_Button.Parent = AutoJJsButton
UICorner_Button.CornerRadius = UDim.new(0, 6)

-- Efeito de gradiente para o botão
local ButtonGradient = Instance.new("UIGradient")
ButtonGradient.Parent = AutoJJsButton
ButtonGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(0, 170, 255)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(0, 140, 210))
})
ButtonGradient.Rotation = 45

StatusLabel.Name = "StatusLabel"
StatusLabel.Parent = MainFrame
StatusLabel.BackgroundTransparency = 1
StatusLabel.Size = UDim2.new(0, 350, 0, 30)
StatusLabel.Position = UDim2.new(0.5, -175, 1, -40)
StatusLabel.Text = "Status: Aguardando..."
StatusLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
StatusLabel.Font = Enum.Font.Gotham
StatusLabel.TextSize = 15
StatusLabel.TextXAlignment = Enum.TextXAlignment.Center

-- Array com os números por extenso
local numeros = {
    "UM",
    "DOIS",
    "TRÊS",
    "QUATRO",
    "CINCO",
    "SEIS",
    "SETE",
    "OITO",
    "NOVE",
    "DEZ",
    "ONZE",
    "DOZE",
    "TREZE",
    "QUATORZE",
    "QUINZE",
    "DEZESSEIS",
    "DEZESSETE",
    "DEZOITO",
    "DEZENOVE",
    "VINTE",
    "VINTE E UM",
    "VINTE E DOIS",
    "VINTE E TRÊS",
    "VINTE E QUATRO",
    "VINTE E CINCO",
    "VINTE E SEIS",
    "VINTE E SETE",
    "VINTE E OITO",
    "VINTE E NOVE",
    "TRINTA",
    -- Adicione mais números se necessário
}

-- Função para converter o número em texto
local function numeroParaTexto(n)
    if n <= #numeros then
        return numeros[n]
    else
        return tostring(n)
    end
end

-- IMPORTANTE: Detecta o sistema de chat para garantir compatibilidade
local chatSystem = "Legacy" -- Padrão
local function detectarSistemaChat()
    if game:GetService("TextChatService") and pcall(function() return game:GetService("TextChatService").ChatVersion end) then
        chatSystem = "TextChatService"
    elseif game.ReplicatedStorage:FindFirstChild("DefaultChatSystemChatEvents") and 
           game.ReplicatedStorage.DefaultChatSystemChatEvents:FindFirstChild("SayMessageRequest") then
        chatSystem = "Legacy"
    else
        -- Tenta encontrar outros módulos de chat
        for _, v in pairs(game.ReplicatedStorage:GetDescendants()) do
            if v.Name == "SayMessageRequest" and v:IsA("RemoteEvent") then
                chatSystem = "Custom"
                return v
            end
        end
    end
    return game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest
end

-- Executa a detecção no início
local chatRemote = detectarSistemaChat()

-- Função para simular a abertura do chat e enviar mensagem "jjs"
local function enviarJJsNoChat(numero)
    local mensagem = numeroParaTexto(numero) .. " jjs"
    
    -- Método 1: Usar o sistema legado mais comum
    local function metodo1()
        -- Pressionar / para abrir o chat
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Slash, false, game)
        wait(0.2)
        game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Slash, false, game)
        wait(0.3)
        
        -- Apaga o "/" que aparece automaticamente
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Backspace, false, game)
        game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Backspace, false, game)
        wait(0.1)
        
        -- Digita a mensagem
        for i = 1, #mensagem do
            local char = string.sub(mensagem, i, i)
            if char == " " then
                game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Space, false, game)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Space, false, game)
            else
                game:GetService("VirtualInputManager"):SendTextInputCharacterEvent(char, game)
            end
            wait(0.01)
        end
        
        -- Pressiona Enter para enviar
        wait(0.2)
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Return, false, game)
        wait(0.1)
        game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Return, false, game)
    end
    
    -- Método 2: Usar o sistema de chat direto
    local function metodo2()
        -- Usa o chat remoto detectado no início
        if chatSystem == "Legacy" or chatSystem == "Custom" then
            -- Sistema normal
            if chatRemote then
                chatRemote:FireServer(mensagem, "All")
            else
                -- Fallback para o caminho padrão
                game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(mensagem, "All")
            end
        elseif chatSystem == "TextChatService" then
            -- Novo sistema de chat
            game:GetService("TextChatService").TextChannels.RBXGeneral:SendAsync(mensagem)
        else
            -- Último caso, tenta o sistema mais comum
            game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(mensagem, "All")
        end
    end
    
    -- Método 3: Usar o sistema de foco no chat
    local function metodo3()
        -- Abre o chat pressionando a tecla padrão
        local starterGui = game:GetService("StarterGui")
        starterGui:SetCore("ChatActive", true)
        wait(0.3)
        
        -- Digita a mensagem usando TextBox automaticamente
        for i = 1, #mensagem do
            local char = string.sub(mensagem, i, i)
            if char == " " then
                game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Space, false, game)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Space, false, game)
            else
                game:GetService("VirtualInputManager"):SendTextInputCharacterEvent(char, game)
            end
            wait(0.01)
        end
        
        -- Pressiona Enter para enviar
        wait(0.2)
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Return, false, game)
        wait(0.1)
        game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Return, false, game)
    end
    
    -- Método 4: Usando método direto de chat combinado com abertura de teclado
    local function metodo4()
        -- Tenta usar todos os métodos principais primeiro
        -- Abre o chat com "/" e depois Backspace
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Slash, false, game)
        wait(0.2)
        game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Slash, false, game)
        wait(0.3)
        
        -- Envia diretamente via FireServer
        game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(mensagem, "All")
    end
    
    -- Tenta todos os métodos, começando pelo mais confiável
    local success = pcall(function()
        -- Primeiro tentamos diretamente o método de envio do sistema
        metodo2()
        
        -- Em paralelo (para maior chance de funcionar) executamos o método 4
        spawn(function()
            metodo4()
        end)
    end)
    
    -- Se falhar o método principal, tenta os outros
    if not success then
        pcall(function()
            metodo1()
        end)
        
        wait(0.2)
        
        pcall(function() 
            metodo3() 
        end)
    end
end

-- Efeitos visuais para o botão
local function createButtonEffect()
    -- Efeito de pressionar
    AutoJJsButton.MouseButton1Down:Connect(function()
        game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.1), {
            Size = UDim2.new(0, 195, 0, 38),
            Position = UDim2.new(0, 17.5, 0, 106)
        }):Play()
    end)
    
    -- Efeito de soltar
    AutoJJsButton.MouseButton1Up:Connect(function()
        game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.1), {
            Size = UDim2.new(0, 200, 0, 40),
            Position = UDim2.new(0, 15, 0, 105)
        }):Play()
    end)
    
    -- Efeito de hover
    AutoJJsButton.MouseEnter:Connect(function()
        game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.2), {
            BackgroundColor3 = Color3.fromRGB(20, 180, 255)
        }):Play()
    end)
    
    -- Efeito de sair do hover
    AutoJJsButton.MouseLeave:Connect(function()
        game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.2), {
            BackgroundColor3 = Color3.fromRGB(0, 170, 255)
        }):Play()
    end)
end

-- Inicializa efeitos do botão
createButtonEffect()

-- Função para fechar a GUI com animação
CloseButton.MouseButton1Click:Connect(function()
    -- Animação de fechamento
    game:GetService("TweenService"):Create(MainFrame, TweenInfo.new(0.3), {
        Size = UDim2.new(0, 0, 0, 0),
        Position = UDim2.new(0.5, 0, 0.5, 0),
        BackgroundTransparency = 1
    }):Play()
    
    -- Espera a animação terminar antes de destruir
    wait(0.3)
    ScreenGui:Destroy()
end)

-- Função para ativar o Auto JJ's
AutoJJsButton.MouseButton1Click:Connect(function()
    local count = tonumber(InputBox.Text)
    if count and count > 0 then
        StatusLabel.Text = "Status: Enviando mensagens..."
        
        -- Animação do botão durante execução
        game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.2), {
            BackgroundColor3 = Color3.fromRGB(0, 120, 200),
            Text = "ATIVANDO..."
        }):Play()
        
        AutoJJsButton.Active = false
        
        -- Primeira tentativa de ativar o chat antes do loop
        -- Isso ajuda a garantir que o chat esteja aberto
        pcall(function()
            -- Método direto de abrir o chat
            local starterGui = game:GetService("StarterGui")
            starterGui:SetCore("ChatActive", true)
            wait(0.3)
        end)
        
        -- Enviando mensagens no chat
        coroutine.wrap(function()
            -- Segurança adicional, tentando abrir o chat usando tecla
            pcall(function()
                game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Slash, false, game)
                wait(0.2)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Slash, false, game)
                wait(0.2)
                game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.Backspace, false, game)
                wait(0.1)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, Enum.KeyCode.Backspace, false, game)
            end)
            
            -- Agora começa a enviar as mensagens
            for i = 1, count do
                -- Atualiza o status durante envio
                StatusLabel.Text = "Status: Enviando " .. i .. " de " .. count
                
                -- Envia a mensagem
                enviarJJsNoChat(i)
                wait(0.8) -- Intervalo entre mensagens
            end
            
            -- Finalizando com animação
            StatusLabel.Text = "Status: Concluído!"
            game:GetService("TweenService"):Create(AutoJJsButton, TweenInfo.new(0.2), {
                BackgroundColor3 = Color3.fromRGB(0, 170, 255),
                Text = "ATIVAR"
            }):Play()
            AutoJJsButton.Active = true
            
            -- Efeito de sucesso temporário na label
            game:GetService("TweenService"):Create(StatusLabel, TweenInfo.new(0.2), {
                TextColor3 = Color3.fromRGB(0, 255, 130)
            }):Play()
            wait(2)
            game:GetService("TweenService"):Create(StatusLabel, TweenInfo.new(0.5), {
                TextColor3 = Color3.fromRGB(200, 200, 200)
            }):Play()
        end)()
    else
        -- Efeito visual de erro
        StatusLabel.Text = "Status: Por favor, insira um número válido!"
        game:GetService("TweenService"):Create(StatusLabel, TweenInfo.new(0.2), {
            TextColor3 = Color3.fromRGB(255, 100, 100)
        }):Play()
        
        -- Shake animation para o InputBox
        local originalPos = InputBox.Position
        for i = 1, 3 do
            InputBox.Position = originalPos + UDim2.new(0, 5, 0, 0)
            wait(0.03)
            InputBox.Position = originalPos - UDim2.new(0, 5, 0, 0)
            wait(0.03)
        end
        InputBox.Position = originalPos
        
        -- Retorna a cor normal após 1.5 segundos
        wait(1.5)
        game:GetService("TweenService"):Create(StatusLabel, TweenInfo.new(0.5), {
            TextColor3 = Color3.fromRGB(200, 200, 200)
        }):Play()
    end
end)
