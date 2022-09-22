if game.PlaceId == 10714365287 then

    local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
    local Window = OrionLib:MakeWindow({Name = "Taha My Pet", HidePremium = false, IntroEnabled = false,IntroText = "WLC TO Taha Gay Hub", SaveConfig = true, ConfigFolder = "OrionTest"})

--Value
_G.autoTab = true
_G.autoHatch = true
_G.selectEgg = "Star1"
_G.equipbest = true



--Functions

function autoTab()
    while _G.autoTab == true do
        game:GetService("ReplicatedStorage").Knit.Services.ClickerService.RF.PlayerClick:InvokeServer()
        wait(.0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
     end
    end


function autoHatch()
    while _G.autoHatch == true do
local args = {
    [1] = _G.selectEgg,
    [2] = 1,
    [3] = {}
}

    game:GetService("ReplicatedStorage").Knit.Services.StarEggService.RF.OpenEggs:InvokeServer(unpack(args))
    wait(.000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
end
end

function equipbest()
    game:GetService("ReplicatedStorage").Knit.Services.PetInventoryService.RF.EquipBest:InvokeServer()
end

--Tabs
local FarmTab = Window:MakeTab({
	Name = "Auto Farm",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local MiscTab = Window:MakeTab({
	Name = "Misc",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local CreaditsTab = Window:MakeTab({
	Name = "Credit",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})


--Toggles
FarmTab:AddToggle({
	Name = "Fast Click",
	Default = false,
	Callback = function(Value)
		_G.autoTab = Value
        autoTab()
	end    
})

MiscTab:AddLabel("Lazm Tkon Jnb Bida To Work")
MiscTab:AddToggle({
	Name = "Auto Open Star",
	Default = false,
	Callback = function(Value)
        _G.autoHatch = Value
        autoHatch()
	end    
})

MiscTab:AddButton({
	Name = "Equip Best",
	Callback = function()
            equipbest()
  	end    
})

--Dropdowns

MiscTab:AddDropdown({
	Name = "Select Star Egg",
	Default = "Star1",
	Options = {"Star1", "Star2", "Star3", "Star4", "Star5", "Star6", "Star7", "Star8", "Star9", "Star10"},
	Callback = function(Value)
		_G.selectEgg = Value
        print(_G.selectEgg)
	end 
})

--Lables

CreaditsTab:AddLabel("By Xoova Sub To Xoova In YT :)")









end
OrionLib:Init()
