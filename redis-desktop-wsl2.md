# Redis desktop manager on windows - kind of ... (via wsl2)
- Install and update windows subsystem for linux
- Fix for snapd for installing redis desktop from snapd
 
    ```bash
    sudo apt-get update && sudo apt-get install -yqq daemonize dbus-user-session fontconfig
    sudo daemonize /usr/bin/unshare --fork --pid --mount-proc /lib/systemd/systemd --system-unit=basic.target
    exec sudo nsenter -t $(pidof systemd) -a su - $LOGNAME

    snap version
    ```
- Install redis desktop manager via snap
 
    ```bash
    sudo snap install redis-desktop-manager
    ```

# SOURCES:
 - https://github.com/microsoft/WSL/issues/5126
 - https://snapcraft.io/redis-desktop-manager
 - https://devblogs.microsoft.com/commandline/the-initial-preview-of-gui-app-support-is-now-available-for-the-windows-subsystem-for-linux-2/
 - https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033
