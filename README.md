-- Criando a GUI
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local CloseButton = Instance.new("TextButton")
local Title = Instance.new("TextLabel")
local AutoJJsButton = Instance.new("TextButton")
local InputBox = Instance.new("TextBox")
local InputLabel = Instance.new("TextLabel")

-- Configurando a GUI
ScreenGui.Name = "AutoJJsGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
MainFrame.Size = UDim2.new(0, 300, 0, 200)
MainFrame.Position = UDim2.new(0.5, -150, 0.5, -100)
MainFrame.Active = true
MainFrame.Draggable = true

CloseButton.Name = "CloseButton"
CloseButton.Parent = MainFrame
CloseButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -35, 0, 5)
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)

Title.Name = "Title"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
Title.Size = UDim2.new(1, -40, 0, 30)
Title.Position = UDim2.new(0, 10, 0, 5)
Title.Text = "Auto JJ's"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.SourceSansBold
Title.TextSize = 20

InputLabel.Name = "InputLabel"
InputLabel.Parent = MainFrame
InputLabel.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
InputLabel.Size = UDim2.new(0, 200, 0, 30)
InputLabel.Position = UDim2.new(0, 10, 0, 50)
InputLabel.Text = "Digite quantos JJ's você quer:"
InputLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
InputLabel.Font = Enum.Font.SourceSans
InputLabel.TextSize = 16

InputBox.Name = "InputBox"
InputBox.Parent = MainFrame
InputBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
InputBox.Size = UDim2.new(0, 100, 0, 30)
InputBox.Position = UDim2.new(0, 10, 0, 90)
InputBox.Font = Enum.Font.SourceSans
InputBox.TextSize = 16
InputBox.PlaceholderText = "Ex: 5"

AutoJJsButton.Name = "AutoJJsButton"
AutoJJsButton.Parent = MainFrame
AutoJJsButton.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
AutoJJsButton.Size = UDim2.new(0, 100, 0, 30)
AutoJJsButton.Position = UDim2.new(0, 10, 0, 130)
AutoJJsButton.Text = "Ativar"
AutoJJsButton.TextColor3 = Color3.fromRGB(255, 255, 255)
AutoJJsButton.Font = Enum.Font.SourceSansBold
AutoJJsButton.TextSize = 16

-- Função para fechar a GUI
CloseButton.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)

-- Função para ativar o Auto JJ's
AutoJJsButton.MouseButton1Click:Connect(function()
    local count = tonumber(InputBox.Text)
    if count and count > 0 then
        for i = 0, count - 1 do
            game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(tostring(i) .. " !", "All")
            wait(0.8)
        end
    else
        warn("Por favor, insira um número válido!")
    end
end)
