local ws = game.workspace
local es = game:GetService("EncodingService")
if workspace:WaitForChild("Logic", 5) then
    local foldername = "stealedCharacters"
    if not isfolder(foldername) then
        makefolder(foldername)
    end
    local counter = 0

    for i, ch in workspace.Logic:GetChildren() do
        local filename = string.format("%s//%d.txt", foldername, counter)
        local toEncode = ch:GetAttribute("Dict")
        local Encoded = base64.encode(toEncode)
        if not isfile(filename) then
            writefile(filename, Encoded)
        end
        counter = counter + 1
        wait(0.1)
    end
end

print("Finished OR logic is was not found here lmao (sad scene im stupid)")
