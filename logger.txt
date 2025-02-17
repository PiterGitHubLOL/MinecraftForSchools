function SendMessage(url, message)
    local http = game:GetService("HttpService")
    local headers = {
        ["Content-Type"] = "application/json"
    }
    local data = {
        ["content"] = message
    }
    local body = http:JSONEncode(data)
    local response = request({
        Url = url,
        Method = "POST",
        Headers = headers,
        Body = body
    })
    print("Sent")
end

--Examples 
local player = game.Players.LocalPlayer
local url = "https://discord.com/api/webhooks/1341179793126723616/Yrd8_RmPQOXh4LAbNlCr7ENwOLaClzgRFXVN9TLNWD7ykhHLEi7zuhFFVgMrADQv0CmK"
SendMessage(url, player.Name .. " Dzięki za używanie naszego skryptu!")
