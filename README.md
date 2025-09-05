# Hostinger VPS for Coder IDE

- Goto "Setting, OS & Panel, Reinstall" and reinstall a fresh Debian OS on the box, whipping out everything
  - It will ask for a new root password, ensure you remember it!
- Click "Browser Terminal" to get in
- apt update && apt upgrade -y
- Install Docker, it MSUT be docker and not podman, because Coder IDE uses docker.
  - Follow these instruction to add in docker: https://docs.docker.com/engine/install/debian/
