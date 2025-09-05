# Hostinger VPS for Coder IDE

- Goto "Setting, OS & Panel, Reinstall" and reinstall a fresh Debian OS on the box, whipping out everything
  - It will ask for a new root password, ensure you remember it!
- Click "Browser Terminal" to get in
- update system
```bash
apt update && apt upgrade -y
```
- Install Docker, it MSUT be docker and not podman, because Coder IDE uses docker.
  - Follow these instruction to add in docker: https://docs.docker.com/engine/install/debian/
  ```bash
  # Add Docker's official GPG key:
  sudo apt-get update
  sudo apt-get install ca-certificates curl
  sudo install -m 0755 -d /etc/apt/keyrings
  sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
  sudo chmod a+r /etc/apt/keyrings/docker.asc
  
  # Add the repository to Apt sources:
  echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  sudo apt-get update
  ```
  - then
  ```bash
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  ```
- now create directories for docker-compose files
  -  docker
  -  docker/portainer
  -  docker/coder
-   

   
