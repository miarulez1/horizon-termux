# Horizon for Termux (`aarch64-linux-android`)

Native Rust Minecraft: Java Edition 26.3 client (`horizon-official`) and resource preparer (`horizon-prepare`) patched for Termux (`bionic`) with Wayland/X11 windowing and Mesa Turnip / PanVK Vulkan support.
## DISCLAIMER: this fork is an atrocious piece of vibe coding, use at your own risk
## Install on Termux

1. Download the `horizon-termux-aarch64` artifact from **Actions** and extract the `.deb`:
   ```bash
   unzip horizon-termux-aarch64.zip
   pkg install ./horizon-termux_0.1.*_aarch64.deb
   ```
2. For Adreno GPUs, install the Mesa Turnip ICD (if not already installed):
   ```bash
   pkg install mesa-vulkan-icd-freedreno
   ```

## Prepare Minecraft 26.3 Resources & Launch

1. Using an existing Minecraft 26.3 installation (`versions/`, `libraries/`, `assets/`) and JDK 25 (`pkg install openjdk-25`):
   ```bash
   horizon-prepare --prepare --complete \
     --minecraft-dir /path/to/.minecraft \
     --output ~/horizon-resources
   ```
2. Launch Horizon inside your Termux Wayland/X11 session (e.g., Anland or Termux:X11):
   ```bash
   mkdir -p ~/horizon-game && cd ~/horizon-game
   horizon-official --resources ~/horizon-resources
   ```
