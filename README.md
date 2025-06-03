# 🖌️ Fluent UI (Customized by ZSOFT HUB)
> Enhanced and extended Fluent UI for advanced Roblox interface development.
> discord: https://discord.gg/DNbasfkB9b

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
# 🖌️ Fluent UI (Customized by ZSOFT HUB)
> Enhanced Fluent UI Framework for Roblox, extended with multi-selection dropdowns.

---

## ✨ Key Features

- ✅ Multi-selection support in Dropdowns (`Multi = true`)
- ✅ Clean integration with Fluent’s existing Tab and Section system
- ✅ Full Roblox UI compatibility and modern design
- ✅ Callback returns selected items in `{ [item] = true }` format
- ✅ Custom styling preserved from Fluent UI core

---

## 🚀 Example Usage

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

-- ✅ Multi Dropdown: Select Fruits
Tabs.Main:AddDropdown("FruitDropdown", {
    Title = "🍉 Select Multiple Fruits",
    Description = "You can select more than one fruit",
    Values = { "Apple", "Banana", "Grape", "Mango", "Cherry" },
    Default = { "Banana", "Cherry" },
    Multi = true,
    Callback = function(value)
        local selectedList = {}

        for fruit, isSelected in pairs(value) do
            -- ✅ Validate key
            if typeof(fruit) == "string" and isSelected then
                table.insert(selectedList, fruit)
            end
        end

        table.sort(selectedList) -- Optional for sorting alphabetically
        print("✅ Selected fruits:", table.concat(selectedList, ", "))
    end
})

