    amBold
    minBtn.TextSize = 24
    minBtn.Parent = header
    Instance.new("UICorner", minBtn).CornerRadius = UDim.new(0, 8)
    
    local closeBtn = Instance.new("TextButton")
    closeBtn.Size = UDim2.new(0, 34, 0, 34)
    closeBtn.Position = UDim2.new(1, -40, 0.5, -17)
    closeBtn.BackgroundColor3 = Color3.fromRGB(160, 30, 50)
    closeBtn.BorderSizePixel = 0
    closeBtn.Text = "✕"
    closeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
    closeBtn.Font = Enum.Font.GothamBold
    closeBtn.TextSize = 18
    closeBtn.Parent = header
    Instance.new("UICorner", closeBtn).CornerRadius = UDim.new(0, 8)
    
    -- Container principal
    local cont = Instance.new("Frame")
    cont.Size = UDim2.new(0.88, 0, 0.88, 0)
    cont.Position = UDim2.new(0.06, 0, 0.10, 0)
    cont.BackgroundTransparency = 1
    cont.Parent = main
    
    -- ==================== BOTÕES PRINCIPAIS ====================
    local function criarBtn(nome, posY, icone, corPadrao)
        local btn = Instance.new("TextButton")
        btn.Size = UDim2.new(1, 0, 0, 42)
        btn.Position = UDim2.new(0, 0, posY, 0)
        btn.BackgroundColor3 = corPadrao or Color3.fromRGB(140, 30, 50)
        btn.BorderSizePixel = 0
        btn.Text = icone .. " " .. nome .. " OFF"
        btn.TextColor3 = Color3.fromRGB(240, 230, 255)
        btn.Font = Enum.Font.GothamBold
        btn.TextSize = 12
        btn.Parent = cont
        Instance.new("UICorner", btn).CornerRadius = UDim.new(0, 10)
        return btn
    end
    
    local noclipBtn = criarBtn("NOCLIP", 0, "👁️")
    local flingBtn = criarBtn("ANTI-FLING", 0.13, "🛡️")
    local godBtn = criarBtn("GOD MODE", 0.26, "⚡")
    local speedBtn = criarBtn("SPEED", 0.39, "🏃")
    local autoBtn = criarBtn("AUTO-DESAB.", 0.52, "💀", Color3.fromRGB(60, 100, 200))
    autoBtn.Text = "💀 AUTO-DESAB. ON"
    
    -- ==================== SEPARADOR ====================
    local separator = Instance.new("Frame")
    separator.Size = UDim2.new(1, 0, 0, 2)
    separator.Position = UDim2.new(0, 0, 0.64, 0)
    separator.BackgroundColor3 = Color3.fromRGB(130, 60, 220)
    separator.BorderSizePixel = 0
    separator.BackgroundTransparency = 0.5
    separator.Parent = cont
    
    -- ==================== SEÇÃO SPEED (SEPARADA) ====================
    local speedSection = Instance.new("Frame")
    speedSection.Size = UDim2.new(1, 0, 0, 70)
    speedSection.Position = UDim2.new(0, 0, 0.67, 0)
    speedSection.BackgroundColor3 = Color3.fromRGB(20, 15, 35)
    speedSection.BorderSizePixel = 0
    speedSection.Parent = cont
    Instance.new("UICorner", speedSection).CornerRadius = UDim.new(0, 10)
    Instance.new("UIStroke", speedSection).Color = Color3.fromRGB(140, 80, 220)
    Instance.new("UIStroke", speedSection).Thickness = 1
    Instance.new("UIStroke", speedSection).Transparency = 0.5
    
    local speedHeader = Instance.new("TextLabel")
    speedHeader.Size = UDim2.new(1, 0, 0, 22)
    speedHeader.BackgroundTransparency = 1
    speedHeader.Text = "⚡ CONTROLE DE VELOCIDADE"
    speedHeader.TextColor3 = Color3.fromRGB(255, 180, 100)
    speedHeader.Font = Enum.Font.GothamBold
    speedHeader.TextSize = 11
    speedHeader.Parent = speedSection
    
    local speedValueLabel = Instance.new("TextLabel")
    speedValueLabel.Size = UDim2.new(0, 45, 0, 22)
    speedValueLabel.Position = UDim2.new(1, -50, 0, 0)
    speedValueLabel.BackgroundTransparency = 1
    speedValueLabel.Text = "50"
    speedValueLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
    speedValueLabel.Font = Enum.Font.GothamBold
    speedValueLabel.TextSize = 13
    speedValueLabel.TextXAlignment = Enum.TextXAlignment.Right
    speedValueLabel.Parent = speedSection
    
    local slider = Instance.new("Frame")
    slider.Size = UDim2.new(0.9, 0, 0, 6)
    slider.Position = UDim2.new(0.05, 0, 0.40, 0)
    slider.BackgroundColor3 = Color3.fromRGB(40, 20, 50)
    slider.BorderSizePixel = 0
    slider.Parent = speedSection
    Instance.new("UICorner", slider).CornerRadius = UDim.new(1, 0)
    
    local fill = Instance.new("Frame")
    fill.Size = UDim2.new(0.22, 0, 1, 0)
    fill.BackgroundColor3 = Color3.fromRGB(200, 120, 30)
    fill.BorderSizePixel = 0
    fill.Parent = slider
    Instance.new("UICorner", fill).CornerRadius = UDim.new(1, 0)
    
    local sliderBtn = Instance.new("TextButton")
    sliderBtn.Size = UDim2.new(0, 14, 0, 14)
    sliderBtn.Position = UDim2.new(0.22, -7, 0.5, -7)
    sliderBtn.BackgroundColor3 = Color3.fromRGB(200, 120, 30)
    sliderBtn.BorderSizePixel = 0
    sliderBtn.Text = ""
    sliderBtn.ZIndex = 2
    sliderBtn.Parent = slider
    Instance.new("UICorner", sliderBtn).CornerRadius = UDim.new(1, 0)
    
    local speedStatus = Instance.new("TextLabel")
    speedStatus.Size = UDim2.new(1, 0, 0, 18)
    speedStatus.Position = UDim2.new(0, 0, 0.70, 0)
    speedStatus.BackgroundTransparency = 1
    speedStatus.Text = "🔴 SPEED DESATIVADO"
    speedStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    speedStatus.Font = Enum.Font.GothamMedium
    speedStatus.TextSize = 10
    speedStatus.TextXAlignment = Enum.TextXAlignment.Center
    speedStatus.Parent = speedSection
    
    -- ==================== SEPARADOR 2 ====================
    local separator2 = Instance.new("Frame")
    separator2.Size = UDim2.new(1, 0, 0, 2)
    separator2.Position = UDim2.new(0, 0, 0.80, 0)
    separator2.BackgroundColor3 = Color3.fromRGB(130, 60, 220)
    separator2.BorderSizePixel = 0
    separator2.BackgroundTransparency = 0.5
    separator2.Parent = cont
    
    -- ==================== CRÉDITOS ====================
    local credit = Instance.new("TextLabel")
    credit.Size = UDim2.new(1, 0, 0, 25)
    credit.Position = UDim2.new(0, 0, 0.94, 0)
    credit.BackgroundTransparency = 1
    credit.Text = "💲 ADM_GOKUBLACK 💲"
    credit.TextColor3 = Color3.fromRGB(180, 130, 255)
    credit.Font = Enum.Font.GothamBlack
    credit.TextSize = 12
    credit.Parent = cont
    
    -- ==================== FUNÇÕES ====================
    local function aplicarGod(char)
        if not char then return end
        local hum = char:FindFirstChild("Humanoid")
        if hum then
            hum.MaxHealth = math.huge
            hum.Health = math.huge
            hum.BreakJointsOnDeath = false
            hum:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
        end
        if not char:FindFirstChild("GodModeFF") then
            local ff = Instance.new("ForceField")
            ff.Name = "GodModeFF"
            ff.Visible = false
            ff.Parent = char
        end
    end
    
    local function aplicarSpeed(val
