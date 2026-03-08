<div align="center">

```
 ██████╗ ██╗   ██╗ █████╗ ███╗   ██╗████████╗ ██████╗ ███╗   ███╗
██╔═══██╗██║   ██║██╔══██╗████╗  ██║╚══██╔══╝██╔═══██╗████╗ ████║
██║   ██║██║   ██║███████║██╔██╗ ██║   ██║   ██║   ██║██╔████╔██║
██║▄▄ ██║██║   ██║██╔══██║██║╚██╗██║   ██║   ██║   ██║██║╚██╔╝██║
╚██████╔╝╚██████╔╝██║  ██║██║ ╚████║   ██║   ╚██████╔╝██║ ╚═╝ ██║
 ╚══▀▀═╝  ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═══╝   ╚═╝    ╚═════╝ ╚═╝     ╚═╝
```

### **Quantom.gg Library** `v1.0.0`

UI Library para **Severe** — construída inteiramente na Drawing API

[![Severe](https://img.shields.io/badge/Executor-Severe-4BDCC8?style=for-the-badge)](https://v-severe.gitbook.io/landing)
[![Lua](https://img.shields.io/badge/Language-Luau-blue?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)]()

---

</div>

## Sobre

**Quantom.gg Library** é uma UI library completa para o executor [Severe](https://v-severe.gitbook.io/landing), desenhada pixel a pixel usando a Drawing API nativa. Tema escuro com accents em teal, inspirada em interfaces modernas de alto nível.

## Elementos

| Elemento | Descrição |
|:---|:---|
| **Window** | Janela draggable com titlebar e accent line |
| **Tab** | Sistema de abas com underline animado |
| **Section** | Painéis com layout two-column (left/right) |
| **Toggle** | Checkbox com display de keybind |
| **Slider** | Drag interativo com min/max/decimais |
| **Dropdown** | Lista expansível com hover e seleção |
| **Keybind** | Click-to-listen, Escape para desvincular |
| **Separator** | Linha divisória sutil |
| **Label** | Texto estático com cor e tamanho customizável |

## Instalação

Coloca `QuantomLib.lua` em `C:\v2\workspace` e carrega no teu script:

```lua
local QuantomLib = loadfile("QuantomLib.lua")()
```

## Uso

### Criar Window

```lua
local Window = QuantomLib.new({
    title = "Quantom.gg",
    x = 200,
    y = 150,
    width = 620,
    height = 420,
})
```

### Adicionar Tabs

```lua
local Main = Window:Tab("Main")
local Settings = Window:Tab("Settings")
```

### Criar Sections

```lua
local Left = Main:Section({name = "Options", side = "left"})
local Right = Main:Section({name = "Config", side = "right"})
```

### Toggle

```lua
Left:Toggle({
    name = "Enabled",
    default = false,
    keybind = "Unbound",
    callback = function(value) end,
})
```

### Slider

```lua
Left:Slider({
    name = "Speed",
    min = 0,
    max = 100,
    default = 50,
    decimals = 0,
    callback = function(value) end,
})
```

### Dropdown

```lua
Left:Dropdown({
    name = "Mode",
    options = {"A", "B", "C"},
    default = "A",
    callback = function(value) end,
})
```

### Keybind

```lua
Left:Keybind({
    name = "Toggle Key",
    default = "Unbound",
    callback = function(key) end,
})
```

### Separator e Label

```lua
Left:Separator()
Left:Label({text = "quantom.gg", color = Color3.fromRGB(75, 220, 200), size = 13})
```

## Controle da Window

```lua
Window:Toggle()    -- mostrar/esconder
Window:Destroy()   -- remover tudo
```

## Temas Customizados

Sobrescreve qualquer cor do tema padrão:

```lua
QuantomLib:SetTheme({
    accent = Color3.fromRGB(255, 100, 100),
    slider_fill = Color3.fromRGB(255, 100, 100),
    toggle_on = Color3.fromRGB(255, 100, 100),
    tab_text_active = Color3.fromRGB(255, 100, 100),
})
```

### Cores disponíveis

| Key | Default | Uso |
|:---|:---|:---|
| `bg` | `(15, 17, 22)` | Fundo da window |
| `titlebar` | `(20, 22, 28)` | Barra de título |
| `accent` | `(75, 220, 200)` | Cor principal |
| `accent_dark` | `(45, 140, 130)` | Accent secundário |
| `text` | `(180, 185, 195)` | Texto principal |
| `text_dim` | `(100, 105, 115)` | Texto secundário |
| `section_bg` | `(22, 25, 32)` | Fundo das sections |
| `section_border` | `(35, 38, 48)` | Bordas |
| `toggle_on` | `(75, 220, 200)` | Toggle ativo |
| `toggle_off` | `(40, 44, 55)` | Toggle inativo |
| `slider_bg` | `(35, 38, 48)` | Fundo do slider |
| `slider_fill` | `(75, 220, 200)` | Fill do slider |
| `dropdown_bg` | `(28, 31, 40)` | Fundo dropdown |
| `dropdown_item` | `(32, 35, 44)` | Item do dropdown |
| `dropdown_hover` | `(38, 42, 52)` | Hover do dropdown |
| `tab_text` | `(120, 125, 135)` | Texto de tab inativa |
| `tab_text_active` | `(75, 220, 200)` | Texto de tab ativa |

## Requisitos

- [Severe](https://v-severe.gitbook.io/landing) executor
- Drawing API

## Estrutura

```
QuantomLib/
├── QuantomLib.lua   — library
├── example.lua      — exemplo de uso
└── README.md        — documentação
```

---

<div align="center">

**quantom.gg** — made by **@hortalex**

</div>
