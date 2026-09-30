# 👑 VRS Artelier - Roblox UI Library

UI Library resmi berbasis **Airflow UI Engine** (OuroFlow) dengan tema **Obsidian Dark & Clean Glassmorphism**, disesuaikan khusus untuk branding **VRS Artelier**.

---

## 🌟 Fitur Utama

- **100% Pure Lucide Icons & Zero Emojis**:
  - Menggunakan library resmi Lucide Icons (`crown`, `swords`, `shield`, `monitor`, `settings`, `refresh-cw`, `gift`, `package`, dll).
- **Official Airflow Engine**:
  - Smooth animation, glassmorphism backdrop shader/particles (Snow/Rain/Stars).
  - Built-in Theme Manager (`Obsidian`, `Dark`, `Midnight`, dll).
  - Built-in Config Manager (save/load profile otomatis di folder `VRS_Artelier`).
  - Home Page interaktif dengan Real-time Metrics (Players, Friends, Cross, Session, FPS, Ping).
- **Standalone Executor Ready**:
  - Script [**`Example.luau`**](file:///d:/Data%20Project%27s/Roblox%20Project/%5B%20UI%20%5D/Example.luau) dan [**`Example.lua`**](file:///d:/Data%20Project%27s/Roblox%20Project/%5B%20UI%20%5D/Example.lua) sudah all-in-one standalone.
  - Langsung copy-paste dan jalankan di Solara, Wave, Delta, Arceus X, Codex, Fluxus, Synapse, dll.

---

## 📁 Struktur File

```
[ UI ]/
├── Example.luau      # Script All-in-One VRS Artelier (Siap eksekusi langsung)
├── Example.lua       # Versi .lua identik untuk executor yang hanya support ekstensi .lua
├── Source.luau       # Core Airflow UI Engine resmi
├── AIRFLOW_DOCS.md   # Dokumentasi lengkap seluruh komponen Airflow UI
└── README.md         # Petunjuk & panduan penggunaan
```

---

## 🚀 Cara Menjalankan di Executor

### Opsi 1: Menjalankan Langsung via Loadstring (Paling Ringkas)
```lua
-- Menjalankan Full Hub langsung dari GitHub:
loadstring(game:HttpGet("https://raw.githubusercontent.com/vrsspace/VRSLIBv2/main/Example.luau"))()
```

Atau jika ingin membuat script sendiri menggunakan library ini:
```lua
local Airflow = loadstring(game:HttpGet("https://raw.githubusercontent.com/vrsspace/VRSLIBv2/main/Source.luau"))()

local Window = Airflow:CreateWindow({
    Name = "VRS Artelier",
    Icon = "crown",
    LoadingTitle = "VRS Artelier",
    LoadingSubtitle = "Artisan Suite",
    ToggleUIKeybind = "RightControl"
})
```

---

### Opsi 2: Copy-Paste All-in-One File
1. Buka file [**`Example.luau`**](file:///d:/Data%20Project%27s/Roblox%20Project/%5B%20UI%20%5D/Example.luau) atau [**`Example.lua`**](file:///d:/Data%20Project%27s/Roblox%20Project/%5B%20UI%20%5D/Example.lua).
2. Tekan **`Ctrl + A`** lalu **`Ctrl + C`** (Copy semua kode).
3. Buka Roblox Executor kamu (Solara / Wave / Delta / dll).
4. Paste kode ke executor dan klik **Execute**!

---

## 🎨 Mengganti Logo & Branding

Di bagian bawah file `Example.luau` (sebelum `Airflow:CreateWindow`), kamu bisa dengan mudah mengganti logo atau kustomisasi branding:

```lua
-- ====================================================================
-- [ VRS ARTELIER - BRANDING & LOGO CONFIGURATION ]
-- ====================================================================
-- OPSI 1: Menggunakan Lucide Icon nama: "crown", "gem", "shield-check", "swords", "flame", dll.
-- OPSI 2: Menggunakan Custom Roblox Decal / Asset ID: "rbxassetid://1234567890"
local VRS_LOGO = "crown"

local Window = Airflow:CreateWindow({
    Name = "VRS Artelier",
    Icon = VRS_LOGO,
    LoadingTitle = "VRS Artelier",
    LoadingSubtitle = "Artisan Suite • Project Slayers 2",
    ToggleUIKeybind = "RightControl",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = "VRS_Artelier",
        FileName = "default"
    },
    ToggleButton = {
        Platform = "Mobile",
        Icon = "crown"
    },
    Home = {
        Name = "Home",
        Title = "Welcome to VRS Artelier",
        Welcome = "Welcome back,",
        Tier = "VRS VIP",
        TierIcon = "crown",
        Stats = { "Players", "Friends", "Cross", "Session", "FPS", "Ping" },
        Discord = "https://discord.gg/vrsartelier",
        Website = "https://vrs-artelier.dev",
        -- ...
    }
})
```

---

## 📚 Komponen yang Tersedia (Airflow UI)

- `Window:CreateTab({ Name, Icon })`
- `Tab:AddLeftGroupbox({ Name, Icon })` / `Tab:AddRightGroupbox({ Name, Icon })`
- `Groupbox:CreateToggle({ Name, CurrentValue, Flag, Callback })`
- `Groupbox:CreateButton({ Name, Icon, Callback })`
- `Groupbox:CreateSlider({ Name, Range, Increment, Suffix, CurrentValue, Flag, Callback })`
- `Groupbox:CreateDropdown({ Name, Options, CurrentOption, Flag, Callback })`
- `Groupbox:CreateColorpicker({ Name, Default, Flag, Callback })`
- `Groupbox:CreateKeybind({ Name, CurrentKeybind, OnChanged })`
- `Tab:CreateConfigManager({ Name, Side })`
- `Tab:CreateThemeManager({ Name, Side })`
- `Airflow:Notify({ Title, Content, Icon, Type, Duration })`
- `Airflow:Confirm({ Title, Content, ConfirmText, Callback })`
