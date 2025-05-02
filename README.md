-- Criando a GUI
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local CloseButton = Instance.new("TextButton")
local Title = Instance.new("TextLabel")
local AutoJJsButton = Instance.new("TextButton")
local InputBox = Instance.new("TextBox")
local InputLabel = Instance.new("TextLabel")
local StatusLabel = Instance.new("TextLabel")
local UICorner = Instance.new("UICorner")

-- Configurando a GUI
ScreenGui.Name = "AutoJJsGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
MainFrame.Size = UDim2.new(0, 400, 0, 300)
MainFrame.Position = UDim2.new(0.5, -200, 0.5, -150)
MainFrame.Active = true
MainFrame.Draggable = true

UICorner.Parent = MainFrame

CloseButton.Name = "CloseButton"
CloseButton.Parent = MainFrame
CloseButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -40, 0, 10)
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.Font = Enum.Font.GothamBold
CloseButton.TextSize = 18

Title.Name = "Title"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
Title.Size = UDim2.new(1, -50, 0, 50)
Title.Position = UDim2.new(0, 25, 0, 10)
Title.Text = "Auto JJ's"
Title.TextColor3 = Color3.fromRGB(0, 170, 255)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 28
Title.TextXAlignment = Enum.TextXAlignment.Center

InputLabel.Name = "InputLabel"
InputLabel.Parent = MainFrame
InputLabel.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
InputLabel.Size = UDim2.new(0, 350, 0, 30)
InputLabel.Position = UDim2.new(0, 25, 0, 80)
InputLabel.Text = "Digite quantos JJ's você quer:"
InputLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
InputLabel.Font = Enum.Font.Gotham
InputLabel.TextSize = 16
InputLabel.TextXAlignment = Enum.TextXAlignment.Left

InputBox.Name = "InputBox"
InputBox.Parent = MainFrame
InputBox.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
InputBox.Size = UDim2.new(0, 150, 0, 30)
InputBox.Position = UDim2.new(0, 25, 0, 120)
InputBox.Font = Enum.Font.Gotham
InputBox.TextSize = 16
InputBox.PlaceholderText = "Ex: 5"
InputBox.TextColor3 = Color3.fromRGB(255, 255, 255)

AutoJJsButton.Name = "AutoJJsButton"
AutoJJsButton.Parent = MainFrame
AutoJJsButton.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
AutoJJsButton.Size = UDim2.new(0, 150, 0, 40)
AutoJJsButton.Position = UDim2.new(0, 25, 0, 170)
AutoJJsButton.Text = "Ativar"
AutoJJsButton.TextColor3 = Color3.fromRGB(255, 255, 255)
AutoJJsButton.Font = Enum.Font.GothamBold
AutoJJsButton.TextSize = 18

StatusLabel.Name = "StatusLabel"
StatusLabel.Parent = MainFrame
StatusLabel.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
StatusLabel.Size = UDim2.new(0, 350, 0, 30)
StatusLabel.Position = UDim2.new(0, 25, 0, 230)
StatusLabel.Text = "Status: Aguardando..."
StatusLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
StatusLabel.Font = Enum.Font.Gotham
StatusLabel.TextSize = 14
StatusLabel.TextXAlignment = Enum.TextXAlignment.Left

-- Função para fechar a GUI
CloseButton.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)

-- Função para ativar o Auto JJ's
AutoJJsButton.MouseButton1Click:Connect(function()
    local count = tonumber(InputBox.Text)
    if count and count > 0 then
        StatusLabel.Text = "Status: Enviando mensagens..."
        AutoJJsButton.Text = "Ativando..."
        AutoJJsButton.BackgroundColor3 = Color3.fromRGB(0, 120, 200)
        AutoJJsButton.Active = false

        -- Enviando mensagens no chat
        coroutine.wrap(function()
            for i = 0, count - 1 do
                game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(tostring(i) .. " !", "All")
                wait(0.8)
            end

            -- Finalizando
            StatusLabel.Text = "Status: Concluído!"
            AutoJJsButton.Text = "Ativar"
            AutoJJsButton.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
            AutoJJsButton.Active = true
        end)()
    else
        StatusLabel.Text = "Status: Por favor, insira um número válido!"
    end
end)
