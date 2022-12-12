pkgname=holoiso-main
pkgver="snapshot$(date +%Y%m%d.%H%M)"
pkgdesc="HoloISO OS Image version 4 (Beta)"
pkgrel="1"
install=holo.install
depends=('archlinux-keyring' 'ark' 'cheese' 'cups' 'curl' 'dolphin' 'ffmpegthumbs' 'gamescope' 'git' 'glxinfo' 'go' 'gwenview' 'hunspell' 'hunspell-en_us' 'holo-wireplumber' 'jupiter-hw-support' 'kdegraphics-thumbnailers' 'konsole' 'kwrite' 'lib32-pipewire' 'lib32-pipewire-jack' 'lib32-pipewire-v4l2' 'libva' 'lib32-libva' 'libva-utils' 'libva-mesa-driver' 'libva-intel-driver' 'lib32-libva-mesa-driver' 'lib32-libva-intel-driver' 'lib32-vulkan-radeon' 'lib32-vulkan-intel' 'mangohud' 'mesa' 'lib32-mesa' 'holoiso-updateclient' 'noto-fonts-cjk' 'pipewire' 'pipewire-alsa' 'pipewire-jack' 'wireplumber' 'pipewire-pulse' 'pipewire-v4l2' 'plasma-meta' 'plasma-nm' 'print-manager' 'rz608-fix-git' 'spectacle' 'steam-jupiter-stable' 'steamdeck-kde-presets' 'tar' 'ufw' 'vlc' 'vulkan-intel' 'vulkan-radeon' 'wget' 'zsh' 'xbindkeys' 'steam-im-modules' 'systemd-swap' 'ttf-twemoji-default' 'ttf-hack' 'ttf-dejavu' 'pkgconf' 'pavucontrol' 'partitionmanager' 'gamemode' 'lib32-gamemode' 'cpupower' 'bluez-plugins' 'bluez-utils' 'xf86-video-amdgpu' 'xf86-video-intel')
arch=("x86_64")

package() {
    holoiso_codename="Beta ($(echo $RANDOM | md5sum | head -c 10; echo;))"
    cp -r "${srcdir}/new_steamos_dirs/etc" "${pkgdir}"
    cp -r "${srcdir}/new_steamos_dirs/usr" "${pkgdir}"
    cp -r "${srcdir}/steamos-customizations/etc" "${pkgdir}"
    cp -r "${srcdir}/steamos-customizations/usr" "${pkgdir}"
    chmod -R 644 "${pkgdir}/etc"
    chmod -R 644 "${pkgdir}/usr"
    chmod -R +x "${pkgdir}/usr/bin"
    chmod -R 644 "${pkgdir}/etc/flatpak"
    chmod -R 755 "${pkgdir}/usr/lib"
    chmod -R 755 "${pkgdir}/etc/systemd"
    chmod -R +x "${pkgdir}/usr/share"
    mkdir -p "${pkgdir}/usr/bin"
    mkdir -p "${pkgdir}/etc"
    mkdir -p "${pkgdir}/etc/systemd/logind.conf.d"
    mkdir -p "${pkgdir}/etc/udev"    
    mkdir -p "${pkgdir}/etc/udev/rules.d"    
    mkdir -p "${pkgdir}/usr/lib/systemd/system"
    mkdir -p "${pkgdir}/etc/skel/Desktop" 
    mkdir -p "${pkgdir}/etc/xdg/autostart"
    mkdir -p "${pkgdir}/usr/bin/steamos-polkit-helpers"
    mkdir -p "${pkgdir}/etc/pacman.d"
    cp "${srcdir}/holomirror" "${pkgdir}/etc/pacman.d/holo_mirrorlist"
    cp "${srcdir}/99-oxpgamepad.rules" "${pkgdir}/etc/udev/rules.d/99-oxpgamepad.rules" 
    cp "${srcdir}/holoiso-reboot-tracker.service" "${pkgdir}/usr/lib/systemd/system/holoiso-reboot-tracker.service"       
    cp "${srcdir}/steamos-session-select" "${pkgdir}/usr/bin/steamos-session-select"
    cp "${srcdir}/holoiso-gamescope-power" "${pkgdir}/usr/bin/holoiso-gamescope-power"
    cp "${srcdir}/holoiso-reboot-tracker" "${pkgdir}/usr/bin/holoiso-reboot-tracker"
    cp "${srcdir}/holoiso-desktop-orientation" "${pkgdir}/usr/bin/holoiso-desktop-orientation"
    cp "${srcdir}/steamos-select-branch" "${pkgdir}/usr/bin/steamos-select-branch"
    cp "${srcdir}/jupiter-controller-update" "${pkgdir}/usr/bin/jupiter-controller-update"
    cp "${srcdir}/jupiter-biosupdate" "${pkgdir}/usr/bin/jupiter-biosupdate"
    cp "${srcdir}/holoiso-disable-sessions" "${pkgdir}/usr/bin/holoiso-disable-sessions"  
    cp "${srcdir}/holoiso-enable-sessions" "${pkgdir}/usr/bin/holoiso-enable-sessions"
    cp "${srcdir}/steamos-priv-write" "${pkgdir}/usr/bin/steamos-polkit-helpers/steamos-priv-write"      
    cp "${srcdir}/recoveryinit" "${pkgdir}/usr/bin/recoveryinit"      
    cp "${srcdir}/osinfo" "${srcdir}/osinfo_tmp"
    cp "${srcdir}/pacman.conf" "${pkgdir}/etc/pacman.conf"
    cp "${srcdir}/beta_pacman.conf" "${pkgdir}/etc/beta_pacman.conf"
    cp "${srcdir}/steamos-gamemode.desktop" "${pkgdir}/etc/skel/Desktop/steamos-gamemode.desktop"
    cp "${srcdir}/desktopshortcuts.desktop" "${pkgdir}/etc/xdg/autostart/desktopshortcuts.desktop"
    cp "${srcdir}/screenorientation.desktop" "${pkgdir}/etc/xdg/autostart/screenorientation.desktop"
    cp "${srcdir}/holoiso-firstboot-config" "${pkgdir}/usr/bin/holoiso-firstboot-config"
    cp "${srcdir}/holoiso-grub-update" "${pkgdir}/usr/bin/holoiso-grub-update"
    sed -i "s/snapshotver/snapshot$(date +%Y%m%d.%H%M)_preview/g" osinfo_tmp
    sed -i "s/versionver/4/g" osinfo_tmp
    sed -i "s/buildver/${holoiso_codename}/g" osinfo_tmp
    cp "${srcdir}/osinfo_tmp" "${pkgdir}/etc/os-release"
    rm "${srcdir}/osinfo_tmp"
    cp "${srcdir}/holoiso-branch" "${pkgdir}/etc/holoiso-branch"
    cp -r "${srcdir}/logind.conf.d/" "${pkgdir}/etc/systemd/"
    chmod +x "${pkgdir}/usr/bin/steamos-session-select"
    chmod +x "${pkgdir}/usr/bin/jupiter-controller-update" 
    chmod +x "${pkgdir}/usr/bin/jupiter-biosupdate"   
    chmod +x "${pkgdir}/usr/bin/recoveryinit"  
    chmod +x "${pkgdir}/usr/bin/holoiso-reboot-tracker" 
    chmod +x "${pkgdir}/usr/bin/holoiso-gamescope-power"
    chmod +x "${pkgdir}/usr/bin/holoiso-disable-sessions"
    chmod +x "${pkgdir}/usr/bin/steamos-select-branch"
    chmod +x "${pkgdir}/usr/bin/holoiso-enable-sessions"
    chmod +x "${pkgdir}/etc/skel/Desktop/steamos-gamemode.desktop"
    chmod +x "${pkgdir}/etc/xdg/autostart/desktopshortcuts.desktop"
    chmod +x "${pkgdir}/etc/xdg/autostart/screenorientation.desktop"
    chmod +x "${pkgdir}/usr/bin/holoiso-firstboot-config"
    chmod +x "${pkgdir}/usr/bin/steamos-polkit-helpers/steamos-priv-write"
    chmod 0644 "${pkgdir}/usr/lib/systemd/system/holoiso-reboot-tracker.service"
    chmod +x "${pkgdir}/usr/bin/holoiso-desktop-orientation"
    chmod +x "${pkgdir}/usr/bin/holoiso-grub-update"
    echo "Release output:"
    cat "${pkgdir}/etc/os-release"
}

