local cac = require(game:GetService("Players").LocalPlayer.PlayerGui.Main.UIController.Inventory)
local Inventory = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")
local Items = {}
local RaityLevel = {"Mythical","Legendary","Rare","Uncommon","Common"}
local RaityColor =  {
    ["Common"] = Color3.fromRGB(179, 179, 179),
    ["Uncommon"] = Color3.fromRGB(92, 140, 211),
    ["Rare"] =  Color3.fromRGB(140, 82, 255),
    ["Legendary"] = Color3.fromRGB(213, 43, 228) ,
    ["Mythical"] =  Color3.fromRGB(238, 47, 50)
}
function GetRaity(color)
    for k,v in pairs(RaityColor) do 
        if v==color then return k end
    end
end

for k,v in pairs(Inventory) do 
    Items[v.Name] = v
end

local total = #getupvalue(cac.UpdateRender,4)
local rac = {}
local allitem = {}
local total2 = 0
while total2<total do 
    local i = 0
    while i < 25000 and total2<total do 
        game:GetService("Players").LocalPlayer.PlayerGui.Main.InventoryContainer.Right.Content.ScrollingFrame.CanvasPosition = Vector2.new(0,i)
        for k,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.InventoryContainer.Right.Content.ScrollingFrame.Frame:GetChildren()) do 
            if v:IsA("Frame") and not rac[v.ItemName.Text] and v.ItemName.Visible==true then 
                local vaihuhu = GetRaity(v.Background.BackgroundColor3)
                if vaihuhu then
                    print("Rac")
                    if not allitem[vaihuhu] then 
                        allitem[vaihuhu] = {}
                    end
                    table.insert(allitem[vaihuhu],v:Clone())
                end
                total2=total2+1
                rac[v.ItemName.Text] = true
            end
        end
        i=i+20
    end
    wait()
end
function GetXY(vec) 
    return vec*100
end

local tvk = Instance.new("UIListLayout")
tvk.FillDirection = Enum.FillDirection.Vertical
tvk.SortOrder = 2
tvk.Padding = UDim.new(0,20)

local Left = Instance.new("Frame",game.Players.LocalPlayer.PlayerGui.BubbleChat)
Left.BackgroundTransparency = 1
Left.Size = UDim2.new(.5,0,1,0) 
tvk.Parent = Left

local Right = Instance.new("Frame",game.Players.LocalPlayer.PlayerGui.BubbleChat)
Right.BackgroundTransparency = 1
Right.Size = UDim2.new(.5,0,1,0) 
Right.Position = UDim2.new(.6,0,0,0)
Right.Name = "Right"
tvk:Clone().Parent = Right
local bucac
for k,v in pairs(allitem) do 
    local cac = Instance.new("Frame",Left)
    cac.BackgroundTransparency = 1
    cac.Size = UDim2.new(1,0,0,0) 
    cac.LayoutOrder = table.find(RaityLevel,k)

    local cac2 = Instance.new("Frame",Right)
    cac2.BackgroundTransparency = 1
    cac2.Size = UDim2.new(1,0,0,0) 
    cac2.LayoutOrder = table.find(RaityLevel,k)
 

    local tvk = Instance.new("UIGridLayout",cac)
    tvk.CellPadding = UDim2.new(.005,0,.005,0)
    tvk.CellSize =  UDim2.new(0,70,0,70)
    tvk.FillDirectionMaxCells = 100
    tvk.FillDirection = Enum.FillDirection.Horizontal

    local ccc = tvk:Clone()
    ccc.Parent = cac2
    for k,v in pairs(v) do 
        if Items[v.ItemName.Text] and Items[v.ItemName.Text].Mastery then 
            if v.ItemLine2.Text~="Accessory" then 
                bucac = v.ItemName:Clone()
                bucac.BackgroundTransparency = 1
                bucac.TextSize = 10
                bucac.TextXAlignment  = 2
                bucac.TextYAlignment  = 2
                bucac.ZIndex  = 5
                bucac.Text = Items[v.ItemName.Text].Mastery
                bucac.Size = UDim2.new(.5,0,.5,0)
                bucac.Position = UDim2.new(.5,0,.5,0)
                bucac.Parent = v
            end
            v.Parent = cac
        elseif v.ItemLine2.Text == "Blox Fruit" then 
            v.Parent = cac2
        end
    end
    cac.AutomaticSize = 2
    cac2.AutomaticSize = 2
end

local MeleeG = Instance.new("Frame",Right)
MeleeG.BackgroundTransparency = 1
MeleeG.Size = UDim2.new(1,0,0,0) 
MeleeG.LayoutOrder = table.find(RaityLevel,k)
MeleeG.AutomaticSize=2
MeleeG.LayoutOrder = 100
local tvk = Instance.new("UIGridLayout",MeleeG)
tvk.CellPadding = UDim2.new(.005,0,.005,0)
tvk.CellSize =  UDim2.new(0,70,0,70)
tvk.FillDirectionMaxCells = 100
tvk.FillDirection = Enum.FillDirection.Horizontal
local ListHuhu = {
    ["Superhuman"] = Vector2.new(3,2),
    ["DeathStep"] = Vector2.new(4,3),
    ["ElectricClaw"] = Vector2.new(2,0),
    ["SharkmanKarate"] = Vector2.new(0,0),
    ["DragonTalon"] = Vector2.new(1,5),
    ["Godhuman"] = "rbxassetid://10338473987"
}
local nguu = {}
function GetNext() end
local Listcaiditconmemayskidconcaca = {}
local buda

for k,v in pairs(ListHuhu) do
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buy"..k,true) == 1 then 
        local huhu = Instance.new("ImageLabel",MeleeG)
        if type(v)=="string" then 
            huhu.Image = v
        else
            huhu.Image = "rbxassetid://9945562382"
            huhu.ImageRectSize = Vector2.new(100,100)
            huhu.ImageRectOffset = v*100
        end 
        Listcaiditconmemayskidconcaca[k] = huhu
        table.insert(nguu,k)
    end
end
buda = 1
function TimKiemItemNehuhu(item)
    for k,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do 
        if v.Name:gsub(" ","") == item then 
            return v
        end
    end
end
spawn(function() 
    local a = #nguu
    local bucu = 0
    while bucu < a do 
        for k,v in pairs(Listcaiditconmemayskidconcaca) do 
            if not v:FindFirstChild("Ditme") then 
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buy"..k) 
                wait(.1)
                local v2 = TimKiemItemNehuhu(k)
                if v2 then 
                    v2:WaitForChild("Level")
                    local Ditme = bucac:Clone()
                    Ditme.Name = "Ditme"
                    Ditme.BackgroundTransparency = 1
                    Ditme.TextSize = 10
                    Ditme.TextXAlignment  = 2
                    Ditme.TextYAlignment  = 2
                    Ditme.ZIndex  = 5
                    Ditme.Text = v2.Level.Value
                    Ditme.Size = UDim2.new(.5,0,.5,0)
                    Ditme.Position = UDim2.new(.5,0,.5,0)
                    Ditme.Parent = v
                    bucu=bucu+1
                end
            end
        end
        wait()
    end

end)
game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = true
repeat wait() until game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.TopContainer.Frame:FindFirstChild("Z")
local rac = game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler:Clone()
rac.LayoutOrder = 101
game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = false

rac.Parent = Right
rac.Size = UDim2.new(1,0,0.3,0)
function formatNumber(v)
    return tostring(v):reverse():gsub("%d%d%d", "%1,"):reverse():gsub("^,", "")
end
local thieunang = game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone()
thieunang.Parent = game:GetService("Players").LocalPlayer.PlayerGui.BubbleChat
thieunang.Position = UDim2.new(0,6,0.85799,0)
local n = formatNumber(game.Players.LocalPlayer.Data.Fragments.Value)
thieunang.Text = "ƒ"..n
print("Done")
pcall(function() 
    game:GetService("Players").LocalPlayer.PlayerGui.Main.MenuButton.Visible = false
  -- game:GetService("Players").LocalPlayer.PlayerGui.Main.MenuButton:Destroy()
end)
pcall(function() 
    game:GetService("Players").LocalPlayer.PlayerGui.Main.HP.Visible = false
    --game:GetService("Players").LocalPlayer.PlayerGui.Main.HP:Destroy()
end)
pcall(function() 
    game:GetService("Players").LocalPlayer.PlayerGui.Main.Energy.Visible = false
    --game:GetService("Players").LocalPlayer.PlayerGui.Main.Energy:Destroy()
end)
for k,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main:GetChildren()) do 
    if v:IsA("ImageButton") then 
        v.Visible = false
    end
end
pcall(function() 
    game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass:Destroy()
end)
