
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Trash Hub", "DarkTheme")
local Tab = Window:NewTab("Auto farm")
local Section = Tab:NewSection("Auto farm")

game:GetService("Workspace").Enemies.SetInstances:Destroy()

HWID = game:GetService("RbxAnalyticsService"):GetClientId()
local Nae = game.Players.LocalPlayer.Name

spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Nametag.Text = "Protect by Hello man#1720"

        
    end)
end)
end)



--funtion
function Skill(use)
        game:GetService("VirtualInputManager"):SendKeyEvent(true,use,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
        wait(.1)
        game:GetService("VirtualInputManager"):SendKeyEvent(false,use,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end
--end

-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextButton = Instance.new("TextButton")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.ResetOnSpawn = false

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.131121635, 0, 0.170283809, 0)
Frame.Size = UDim2.new(0, 50, 0, 50)
Frame.Active = true
Frame.Draggable = true

TextButton.Parent = Frame
TextButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextButton.Position = UDim2.new(-0.0199996941, 0, 0, 0)
TextButton.Size = UDim2.new(0, 50, 0, 50)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "Hide ui"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 14.000
TextButton.MouseButton1Down:connect(function()
	Library:ToggleUI()
if TextButton.Text == "Hide ui" then
TextButton.Text = "Open ui"
elseif TextButton.Text == "Open ui" then
TextButton.Text = "Hide ui"
end
end)


local Npc = {}
local Weaponlist = {}
local Weapon = nil


for i,v in pairs(game:GetService("Workspace").Merchants:GetChildren()) do
    table.insert(Npc,v.Name)
end

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end

local pa = Instance.new("Part",workspace)
   pa.Name = "fuck"
game:GetService("Workspace").fuck.Size = Vector3.new(100, 1, 100)
game:GetService("Workspace").fuck.Anchored = true
game:GetService("Workspace").fuck.CFrame = CFrame.new(-477.8727111816406, math.random(10000,100000), -291.1473083496094)

Section:NewToggle("Auto farm all stats (safe mode)", "", function(uymyky)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").fuck.CFrame * CFrame.new(0,10,0)
_G.Autoallstats = uymyky
end)

Section:NewToggle("Auto farm Haki", "", function(ytnttm)
_G.AutoHaki = ytnttm
end)

Section:NewToggle("Auto farm Haki (super fast using with hop)", "", function(uykm)
_G.AutoHakiFast = uykm
end)

Section:NewToggle("Auto farm ( pro )", "", function(ytgntg)
    _G.Autofarm = ytgntg
    end)
    
    Section:NewToggle("Auto farm ( noob )", "", function(yttthn)
    _G.Autofarmnoob = yttthn
    end)
    
    Section:NewToggle("Auto attack", "", function(yuytmt)
    _G.Autoattack = yuytmt
    end)
    
    Section:NewToggle("Auto Quest", "", function(ytnht)
    _G.AutoQuest = ytnht
    end)
    
    Section:NewToggle("Auto Equip", " ", function(a)
    AutoEquiped = a
    end)
    
    local dropdown = Section:NewDropdown("Select weapon","Info", Weaponlist, function(aaaa)
    Weapon = aaaa
    end)
    
    Section:NewButton("Refresh Weapon", "Refreshes Dropdown", function(aa)
    Weaponlist = {}
    for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
        table.insert(Weaponlist,v.Name)
    end
    dropdown:Refresh(Weaponlist)
    end)
    
    Section:NewToggle("Auto Haki", "", function(ebgegeben)
    _G.HAKI = ebgegeben
    end)
    
    

local Tab = Window:NewTab("More")
local Section = Tab:NewSection("More")

Section:NewToggle("Auto farm haki + hop", "", function(rgnhytm)
    _G.HakiHop = rgnhytm
end)

Section:NewToggle("Light Auto farm", "", function(btrgtynh)
    _G.Lightkill = btrgtynh
end)

Section:NewToggle("Magma Auto farm", "", function(btrgtynh)
    _G.Lightkill = btrgtynh
end)

Section:NewToggle("Flare Auto farm", "", function(btrgtynh)
    _G.Flảekill = btrgtynh
end)

Section:NewButton("Boost fps", "", function()
workspace:FindFirstChildOfClass('Terrain').WaterWaveSize = 0
	workspace:FindFirstChildOfClass('Terrain').WaterWaveSpeed = 0
	workspace:FindFirstChildOfClass('Terrain').WaterReflectance = 0
	workspace:FindFirstChildOfClass('Terrain').WaterTransparency = 0
	game:GetService("Lighting").GlobalShadows = false
	game:GetService("Lighting").FogEnd = 9e9
	settings().Rendering.QualityLevel = 1
	for i,v in pairs(game:GetDescendants()) do
		if v:IsA("Part") or v:IsA("UnionOperation") or v:IsA("MeshPart") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
		elseif v:IsA("Decal") then
			v.Transparency = 1
		elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
			v.Lifetime = NumberRange.new(0)
		elseif v:IsA("Explosion") then
			v.BlastPressure = 1
			v.BlastRadius = 1
		end
	end
	for i,v in pairs(game:GetService("Lighting"):GetDescendants()) do
		if v:IsA("BlurEffect") or v:IsA("SunRaysEffect") or v:IsA("ColorCorrectionEffect") or v:IsA("BloomEffect") or v:IsA("DepthOfFieldEffect") then
			v.Enabled = false
		end
	end
	workspace.DescendantAdded:Connect(function(child)
		coroutine.wrap(function()
			if child:IsA('ForceField') then
				game:GetService('RunService').Heartbeat:Wait()
				child:Destroy()
			elseif child:IsA('Sparkles') then
				game:GetService('RunService').Heartbeat:Wait()
				child:Destroy()
			elseif child:IsA('Smoke') or child:IsA('Fire') then
				game:GetService('RunService').Heartbeat:Wait()
				child:Destroy()
			end
		end)()
	end)


end)

local Tab = Window:NewTab("Auto Sam")
local Section = Tab:NewSection("Auto Sam")

Section:NewToggle("Auto Get Compass", "", function(rtrbrhrhnr)
    _G.GetCompass = rtrbrhrhnr
end)

Section:NewToggle("Auto Find Compass", "", function(rtbrnhrnr)
    _G.Compass = rtbrnhrnr
end)



local Tab = Window:NewTab("Auto Skill")
local Section = Tab:NewSection("Auto Skill")

Section:NewToggle("Auto skill Z", "ToggleInfo", function(yntnrnr)
    _G.SkillZ = yntnrnr
end)

Section:NewToggle("Auto skill X", "ToggleInfo", function(eretbhe)
    _G.SkillX = eretbhe
end)

Section:NewToggle("Auto skill C", "ToggleInfo", function(rtbnrn)
    _G.SkillC = rtbnrn
end)

Section:NewToggle("Auto skill V", "ToggleInfo", function(erbtne)
    _G.SkillV = erbtne
end)

Section:NewToggle("Auto skill E", "ToggleInfo", function(srynrjr)
    _G.SkillE = srynrjr
end)

Section:NewToggle("Auto skill F", "ToggleInfo", function(stynt)
    _G.SkillF = stynt
end)

Section:NewToggle("Auto skill N", "ToggleInfo", function(rtbgrn)
    _G.SkillN = rtbgrn
end)


local Tab = Window:NewTab("Teleport")
 local Section = Tab:NewSection("Npc")

Section:NewDropdown("Select Npc", "", Npc, function(rbrhrynr)
    Choose = rbrhrynr
end)

Section:NewButton("Teleport", "", function()
for i,v in pairs(game:GetService("Workspace").Merchants:GetChildren()) do
if v.Name == Choose then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
end
end
end)

Section:NewButton("Talk", "", function()
for i,v in pairs(game:GetService("Workspace").Merchants:GetChildren()) do
    if v.Name == Choose then
        fireclickdetector(v.Clickable.ClickDetector)
end
end
end)



local Tab = Window:NewTab("Misc")
 local Section = Tab:NewSection("Misc")
 Section:NewKeybind("Hide UI", "", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)

Section:NewToggle("Auto Respawn", "", function(symym)
    _G.Autorespawn = symym
end)


Section:NewButton("No water damage", "", function()
local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    game.Workspace.UserData["User_"..Final].Data["DevilFruit"].Value = "None"
    game.Workspace.UserData["User_"..Final].Data["DevilFruit2"].Value = "None"
end)

local Tab = Window:NewTab("Setting")
local Section = Tab:NewSection("Soon .....")





 local Tab = Window:NewTab("Credit")
 local Section = Tab:NewSection("Credit")
 Section:NewButton("Discord", "Let join", function()
    setclipboard('https://discord.gg/4njGXZbh74')
end)

Section:NewButton("Youtube", "sub now", function()
    setclipboard('https://www.youtube.com/channel/UCBBJZTGE5txsKpRBY_27u9A')
end)




--src
spawn(function()
    while game:GetService("RunService").Stepped:wait(10) do
        character = game.Players.LocalPlayer.Character 
        if _G.NoClip then
            pcall(function()
                for _, v in pairs(character:GetDescendants()) do
                    pcall(function()
                        if v:IsA("BasePart") then
                            pcall(function()
                            v.CanCollide = false
                            end)
                        end
                    end)
                end
            end)
        end
    end
end)

spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)

spawn(function()
    while wait() do
    pcall(function()
        if _G.Autoallstats then
plr = game.Players.LocalPlayer
                                            for i,v in pairs(game:GetService("Workspace").Barrels.Crates:GetDescendants()) do
                                                if v:IsA("ClickDetector") then
                                                fireclickdetector(v)
                                                end
                                            end
                                            
                                            for i,v in pairs(game:GetService("Workspace").Barrels:GetDescendants()) do
                                                if v:IsA("ClickDetector") then
                                                fireclickdetector(v)
                                                end
                                            end
                                            
                                            for i,v in pairs(game.Workspace:GetChildren()) do 
                                                if v.ClassName == "Tool" then
                                                    game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
                                                end
                                            end
                
                                            wait()
                                            for i,v in pairs(game:GetService("Workspace").Island8.Kitchen:GetDescendants()) do
                                                if v:IsA("ClickDetector") then
                                                fireclickdetector(v)
                                                end
                                            end

for a,h in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                    if h:IsA("Tool") and string.find(h.Name, "Juice") or string.find(h.Name, "Milk") or string.find(h.Name, "Cider") or string.find(h.Name, "Lemonade") or string.find(h.Name, "Smoothie") or string.find(h.Name, "Golden") then
                                            game.Players.LocalPlayer.Character.Humanoid:EquipTool(h)
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                        end
                                    end

end
end)
end
end)

spawn(function()
   while wait(WT) do
       
  if _G.Webhook then
Name = game.Players.LocalPlayer.Name
level = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.TotalLevel.Text
Melee = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Melee.Text
Def = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Defense.Text
Sni = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Sniper.Text
Swo = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Sword.Text
Haki = game:GetService("Players").LocalPlayer.PlayerGui.Menu.Frame.C.Frame.Haki.Text
sammy = game:GetService("Players").LocalPlayer .PlayerGui.Menu.Frame.C.Frame.A.Sam.SamTimer.Text
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = 'Name : ' .. '||' .. Name .. '||'})
      }
  );
  
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = level })
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = Melee})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = Def})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = Sni})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = Swo})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = Haki})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = 'Credit By Trash Hub'})
      }
  );
  
  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = "Sam Quest" .. sammy })
      }
  );

  local response = syn.request(
      {
          Url = wbh,
          Method = 'POST',
          Headers = {
              ['Content-Type'] = 'application/json'
          },
          Body = game:GetService('HttpService'):JSONEncode({content = '-------------------------------------'})
      }
  );
 end
  
end
end)

spawn(function()
   while wait(0.1) do
        if _G.Autoattack then
            game:GetService'VirtualUser':CaptureController()
            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
        end
    end
end)

spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.Autofarm then
            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
    if v.DevilFruit ~= "" then
if v.Name ~= "SetInstances" then
    if v.Name ~= "Lv40 Cave Demon" then
        if v.Name ~= "Lv188 Cave Demon" then
            if v.Name ~= "Lv186 Cave Demon" then
                if v.Name ~= "Lv219 Cave Demon" then
                    if v.Name ~= "Lv198 Cave Demon" then
                                    v.Humanoid.WalkSpeed = 0
            v.Humanoid.JumpPower = 0
                        v.Humanoid:ChangeState(11)
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,4)
    
if v.Humanoid.Health == 0 then
        v:Destroy()
    end
end

end
end
end
end
end
end
end
        end
    end)
end)
end)


spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
if _G.AutoQuest then
if game:GetService("Players").LocalPlayer.PlayerGui.MissionGui.Frame.Frame.Header.Text ~= "Mission Objective" then
local Event = game:GetService("Workspace").Merchants.ExpertiseMerchant.Clickable.Retum
Event:FireServer()
end
end
    end)
end)
end)

spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.Autofarmnoob then
            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
if v.DevilFruit ~= "" then
if v.Humanoid.MaxHealth <= 2000 then
    if v.Name ~= "SetInstances" then
        if v.Name ~= "Lv40 Cave Demon" then
            v.Humanoid.WalkSpeed = 0
            v.Humanoid.JumpPower = 0
            v.Humanoid:ChangeState(11)
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,4)
    
if v.Humanoid.Health == 0 then
        v:Destroy()
    end
end
end
end
end
end
        end
    end)
end)
end)

spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
if _G.AutoHaki then
for i,v in pairs(game:GetService("Workspace").UserData:GetChildren()) do
if v.Name ~= "UserIdName" then
local args = {
    [1] = "On",
    [2] = 1
}

v.III:FireServer(unpack(args))
wait(0.1)
local args = {
    [1] = "Off",
    [2] = 1
}

v.III:FireServer(unpack(args))
end
end
end
end)
        end)
end)

spawn(function()
        while wait() do
            if _G.SkillZ then
                pcall(function()
                    Skill("Z")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillX then
                pcall(function()
                    Skill("X")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillC then
                pcall(function()
                    Skill("C")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillV then
                pcall(function()
                    Skill("V")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillE then
                pcall(function()
                    Skill("E")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillF then
                pcall(function()
                    Skill("F")
                end)
            end
        end
end)

spawn(function()
        while wait() do
            if _G.SkillN then
                pcall(function()
                    Skill("N")
                end)
            end
        end
end)


spawn(function()
   while wait(10) do
       if _G.Autorespawn then
if game:GetService("Players").LocalPlayer.PlayerGui.Load.Frame.Visible == true then
                        repeat wait()
                            for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Load.Frame.Load.MouseButton1Click)) do
                                v.Function()
                            end
                        until game:GetService("Players").LocalPlayer.PlayerGui.Load.Frame.Visible == false
end

end
   end
end)

spawn(function()
        while wait(1) do
            pcall(function()
                if _G.Compass then
                    game.Workspace.Merchants.QuestMerchant.Clickable.Retum:FireServer()
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Compass") and not game.Players.LocalPlayer.Character:FindFirstChild("Compass") then
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Compass").Parent = game.Players.LocalPlayer.Character
                    elseif game.Players.LocalPlayer.Character:FindFirstChild("Compass") then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(game.Players.LocalPlayer.Character:FindFirstChild("Compass").Poser.Value)
                    end
                    game:GetService'VirtualUser':CaptureController()
                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                end
            end)
        end
end)

spawn(function()
        while wait() do
            if _G.GetCompass then
                -- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = "Claim1"
}

workspace.Merchants.QuestMerchant.Clickable.Retum:FireServer(unpack(args))

            end
        end
end)

spawn(function()
        while wait() do
            if _G.HAKI then
local id = "User_" .. game.Players.LocalPlayer.UserId

for i,v in pairs(game:GetService("Workspace").UserData:GetChildren()) do
    if v.Name == id then
        for i,v2 in pairs(v:GetChildren()) do
            if v.UsingHaki.Value == false then
                Skill("Q")
            end
        end
    end
end
            end
        end
end)

spawn(function()
        while wait() do
            if _G.HakiHop then
ha = game.Players.LocalPlayer.UserId
if game:GetService("Workspace").UserData["User_"..ha].HakiBar.Value == 0 then
    game:GetService("TeleportService"):Teleport(game.PlaceId)
end
            end
        end
end)

spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
if _G.AutoHakiFast then
for i,v in pairs(game:GetService("Workspace").UserData:GetChildren()) do
if v.Name ~= "UserIdName" then
local args = {
    [1] = "On",
    [2] = 1
}

v.III:FireServer(unpack(args))
wait(0.05)
local args = {
    [1] = "Off",
    [2] = 1
}

v.III:FireServer(unpack(args))
end
end
end
end)
        end)
end)

spawn(function()
    while wait() do
    pcall(function()    
        if _G.Lightkill then
                script = game:GetService("Players").LocalPlayer.Character.Powers.Light;
VTC = script.RemoteEvent.RemoteFunction:InvokeServer();
local pla = game.Players.LocalPlayer;
local Mouse = pla:GetMouse();
for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
    if v.Name ~= "SetInstances" then
        if v.Humanoid.MaxHealth <= 2000 then
            v.Humanoid:ChangeState(11)
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Head.CFrame * CFrame.new(0,10,0)
if v.Humanoid.Health == 0 then
        v:Destroy()
    end
local args = {
    [1] = VTC,
    [2] = "LightPower2",
    [3] = "StartCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = "Left"
}

game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(unpack(args))

wait(0.1)
-- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = VTC,
    [2] = "LightPower2",
    [3] = "StopCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = 100
}

game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(unpack(args))



end
end
end
end
end)
end
end)

spawn(function()
    while wait() do
    pcall(function()    
        if _G.Magmakill then
                script = game:GetService("Players").LocalPlayer.Character.Powers.Magma;
VTC = script.RemoteEvent.RemoteFunction:InvokeServer();
local pla = game.Players.LocalPlayer;
local Mouse = pla:GetMouse();
for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
    if v.Name ~= "SetInstances" then
        if v.Humanoid.MaxHealth <= 2000 then
            v.Humanoid:ChangeState(11)
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Head.CFrame * CFrame.new(0,10,0)
if v.Humanoid.Health == 0 then
        v:Destroy()
    end
local args = {
    [1] = VTC,
    [2] = "MagmaPower1",
    [3] = "StartCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = "Left"
}

game:GetService("Players").LocalPlayer.Character.Powers.Magma.RemoteEvent:FireServer(unpack(args))

wait(0.1)
-- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = VTC,
    [2] = "MagmaPower1",
    [3] = "StopCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = 100
}

game:GetService("Players").LocalPlayer.Character.Powers.Magma.RemoteEvent:FireServer(unpack(args))



end
end
end
end
end)
end
end)

spawn(function()
    while wait() do
    pcall(function()    
        if _G.Flarekill then
                script = game:GetService("Players").LocalPlayer.Character.Powers.Flare;
VTC = script.RemoteEvent.RemoteFunction:InvokeServer();
local pla = game.Players.LocalPlayer;
local Mouse = pla:GetMouse();
for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
    if v.Name ~= "SetInstances" then
        if v.Humanoid.MaxHealth <= 2000 then
            v.Humanoid:ChangeState(11)
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Head.CFrame * CFrame.new(0,10,0)
if v.Humanoid.Health == 0 then
        v:Destroy()
    end
local args = {
    [1] = VTC,
    [2] = "FlarePower2",
    [3] = "StartCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = "Left"
}

game:GetService("Players").LocalPlayer.Character.Powers.Flare.RemoteEvent:FireServer(unpack(args))

wait(0.1)
-- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = VTC,
    [2] = "FlarePower1",
    [3] = "StopCharging",
    [4] = game.Players.LocalPlayer.Character.Head.CFrame * CFrame.new(0,-10,0),
    [5] = Mouse.Target,
    [6] = 100
}

game:GetService("Players").LocalPlayer.Character.Powers.Flare.RemoteEvent:FireServer(unpack(args))



end
end
end
end
end)
end
end)



