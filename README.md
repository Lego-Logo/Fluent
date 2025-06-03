# 🖌️ Fluent UI (Customized by ZSOFT HUB)
> Enhanced and extended Fluent UI for advanced Roblox interface development  
> 🎮 Discord: [Join Here](https://discord.gg/DNbasfkB9b)

---

## ✨ Key Features (Custom)

- ✅ **Multi-selection Dropdown** support (`Multi = true`)
- ✅ Fully integrated with Fluent's `Tab` and `Section` system
- ✅ Callback returns selection as a table: `{ Apple = true, Banana = true }`
- ✅ Compatible with both single and multi-select
- ✅ Clean animations, font, and layout matching original Fluent UI
- ✅ Easily extendable with `Set`, `Get`, and dynamic value updates

---

## 🚀 Quick Start

```lua
-- ✅ Load Fluent UI from ZSOFT HUB GitHub
local Fluent = loadstring(game:HttpGet("https://raw.githubusercontent.com/Lego-Logo/Fluent/main/main.lua"))()

-- ✅ Create Fluent Window
local Window = Fluent:CreateWindow({
    Title = "Custom Fluent UI",
    SubTitle = "Powered by ZSOFT",
    TabWidth = 140,
    Size = UDim2.fromOffset(520, 400),
    Acrylic = true,
    Theme = "Dark"
})

-- ✅ Add Main Tab
local Tabs = {
    Main = Window:AddTab({ Title = "Main Menu", Icon = "list" })
}

-- ✅ Multi Dropdown Example
Tabs.Main:AddDropdown("FruitDropdown", {
    Title = "🍉 Select Multiple Fruits",
    Description = "You can select more than one fruit",
    Values = { "Apple", "Banana", "Grape", "Mango", "Cherry" },
    Default = { "Banana", "Cherry" },
    Multi = true,
    Callback = function(value)
        local selectedList = {}
        for fruit, isSelected in pairs(value) do
            if typeof(fruit) == "string" and isSelected then
                table.insert(selectedList, fruit)
            end
        end
        table.sort(selectedList)
        print("✅ Selected fruits:", table.concat(selectedList, ", "))
    end
})
