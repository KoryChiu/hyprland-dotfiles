
如果你是 hyprland 小白，

第一次進入 Hyprland 桌面，啥都幹不了，別怕

叫出 termianl 快捷鍵 `win + q`

進 terminal 後，你知道的 就可以做任何事了

# 起手式

先安裝＆設定一些基本的 thing

```bash
sudo pacman -Syyu

# Install yay
sudo pacman -S --needed base-devel git
cd /tmp
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
yay -Syyu

# Install Base Tools
sudo pacman -S openssh neovim sync wl-clipboard cliphist imagemagick yazi tree btop pamixer notify-send-rs-bin brightnessctl pavucontrol unzip zip p7zip unrar deno luarocks jq

sudo ln -s /usr/sbin/nvim /usr/sbin/vi

# Install nftable, 安裝時如果詢問是否取代 iptables，請選 Y
sudo pacman -S nftables iptables-nft
sudo systemctl enable --now nftables

ssh-keygen -t ed25519

yay -S waybar wlogout swaylock fuzzel swww slurp grim swappy thunar thunar-archive-plugin

yay -S google-chrome docker docker-compose mtr tcpdump wireshark-qt freerdp remmina fastfetch  eza bat fzf curlie ripgrep visual-studio-code-bin rkhunter dmidecode

sudo systemctl enable --now docker.service
sudo usermod -aG docker $USER

sudo rkhunter --propupd

mkdir -p ~/Downloads
mkdir -p ~/Documents
```

# Install fish shell (如果你不喜歡就跳過)

```bash
sudo pacman -S fish fisher
chsh -s /bin/fish

# terminal logout & login

fisher install patrickf1/fzf.fish
fisher install jorgebucaran/autopair.fish
fisher install IlanCosman/tide
# 下面插件似乎不維護了，可以改用其他的
fisher install jethrokuan/z

yay -S zoxide
vi ~/.config/fish/config.fish
# 寫入下面
# zoxide init fish | source
```

# 設定中文環境

```bash
sudo vi /etc/locale.gen

# 找到並取消註釋（刪除 #）以下兩行：
#    en_US.UTF-8 UTF-8
#    zh_TW.UTF-8 UTF-8 (台灣正體)

sudo locale-gen

sudo nano /etc/locale.conf
# 設定為：LANG=en_US.UTF-8

yay -S ttf-jetbrains-mono-nerd adobe-source-han-sans-otc-fonts adobe-source-han-serif-otc-fonts noto-fonts-cjk ttf-font-awesome noto-fonts-emoji

yay -S fcitx5-im fcitx5-chewing fcitx5-chinese-addons fcitx5-configtool fcitx5-lua fcitx5-gtk fcitx5-qt fcitx5-nord

# 叫出 fcitx5-configtool GUI , 
# 將酷注音加入輸入法 (找 chewing)
# theme 選用 fcitx5-nord

sudo vi /etc/environment
# 寫入下面設定
GTK_IM_MODULE=wayland
QT_IM_MODULE=fcitx
QT_IM_MODULES="wayland;fcitx;ibus"
XMODIFIERS=@im=fcitx
SDL_IM_MODULE=fcitx
INPUT_METHOD=fcitx
GLFW_IM_MODULE=ibus
```

# 安裝 NVIDIA 專有驅動, 移除衝突的 Nouveau 驅動

```bash
sudo pacman -S nvidia-dkms nvidia-utils nvidia-settings lib32-nvidia-utils
sudo pacman -R xf86-video-nouveau vulkan-nouveau

sudo vi /boot/loader/entries/2025-12-12_23-23-49_linux.conf
# 在 options 那一行的最後面加入：nvidia_drm.modeset=1


```

# Install SDDM (開機登入畫面)

```bash
sudo pacman -S --needed sddm qt6-svg qt6-virtualkeyboard qt6-multimedia-ffmpeg
```

選一個你喜歡的 theme , 我是使用 SilentSDDM
https://github.com/uiriansan/SilentSDDM
```bash
cd /tmp/
git clone -b main --depth=1 https://github.com/uiriansan/SilentSDDM && cd SilentSDDM && ./install.sh
```

# CATO VPN

https://aur.archlinux.org/cgit/aur.git/tree/PKGBUILD?h=cato-client-bin

```
yay -S cato-client-bin
```


