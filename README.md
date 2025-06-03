# 🖌️ Fluent UI (Customized by ZSOFT HUB)
> Enhanced and extended Fluent UI for advanced Roblox interface development.

---

## ✨ Key Features (Customized)

- ✅ **Multi Dropdown Selection** support
- ✅ Fully integrated with Fluent's Tab system
- ✅ Callback returns table format: `{ Apple = true, Banana = true }`
- ✅ Compatible with both single and multi-select dropdowns
- ✅ Dynamic update of selected values with `Set`, `Get`, and `Callback`
- ✅ Uses original Fluent styling: font, stroke, layout, and animations

---

## 🚀 Quick Example Usage

```lua
local Fluent = loadstring(game:HttpGet("https://raw.githubusercontent.com/Lego-Logo/Fluent/main/main.lua"))()

local Window = Fluent:CreateWindow({
    Title = "Custom Fluent UI",
    SubTitle = "Powered by ZSOFT HUB",
    TabWidth = 140,
    Size = UDim2.fromOffset(520, 400),
    Acrylic = true,
    Theme = "Dark"
})

local Tabs = {
    Main = Window:AddTab({ Title = "Main Menu", Icon = "list" })
}

Tabs.Main:AddDropdown({
    Title = "🍇 Select Fruits",
    Description = "You can select more than one item",
    Values = { "Apple", "Banana", "Cherry", "Mango", "Grape" },
    Default = { "Banana", "Grape" },
    Multi = true,
    Callback = function(selected)
        local result = {}
        for fruit, enabled in pairs(selected) do
            if enabled then table.insert(result, fruit) end
        end
        print("✅ Selected Fruits:", table.concat(result, ", "))
    end
})
