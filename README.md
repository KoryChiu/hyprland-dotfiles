# hyprland-dotfiles

本 dotfiles 基於 HP EliteBook 840 G8 Notebook PC，

為分享 Hyprland 平鋪式桌面使用，

請先下載 [ArchLinux image](https://mirror.twds.com.tw/archlinux/iso/latest/) ，使用 `archinstall` 安裝，

開機選用 `systemd-boot` , profile 選用 `hyprland` , 音效選用 `pipewire` 。 

安裝後，重開機進入 Hyprland ，請參照此[文件](hyprland-setup-arch.md)來打照 Hyprland 環境。

## 搭配 Hyprland 桌面的相關軟體列表

- shell : fish
- 程式選單 : fuzzel
- 終端 : kitty
- 檔案總管 : thunar and yazi
- 截圖 : grim + slurp
- 鎖屏 : swaylock
- 桌面通知 : swaync
- 工具列 : waybar
- 重開機選單 : wlogout
- 開機登入 : sddm

## 硬體資訊

- RAM: total: 64 GiB
- CPU: 11th Gen Intel Core i7-1165G7 bits: 64 type: MT MCP
- Graphics: Intel TigerLake-LP GT2 [Iris Xe Graphics] vendor: Hewlett-Packard
- Audio: Intel Tiger Lake-LP Smart Sound Audio vendor: Hewlett-Packard
- Network: Intel Wi-Fi 6 AX201
- Volume: total: 953.87 GiB , Samsung model: MZVL21T0HCLR-00BH1

## Dotfile List

```
dotfiles/
├── .config
│   ├── fish
│   │   └── config.fish
│   ├── fuzzel
│   │   └── fuzzel.ini
│   ├── hypr
│   │   ├── hyprland.conf
│   │   ├── media-binds.conf
│   │   └── xdg-portal-hyprland
│   ├── kitty
│   │   ├── kitty.conf
│   │   └── mocha.conf
│   ├── swaylock
│   │   ├── coffee-001.jpeg
│   │   ├── config
│   │   └── photo_6160951512201802500_x.jpg
│   ├── swaync
│   │   ├── config.json
│   │   └── style.css
│   ├── waybar
│   │   ├── config.jsonc
│   │   └── style.css
│   └── wlogout
│       ├── layout
│       └── style.css
└── etc
    ├── environment
    ├── locale.conf
    ├── nftables.conf
    └── sddm.conf
```

