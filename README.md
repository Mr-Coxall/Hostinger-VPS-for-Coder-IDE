# Hostinger VPS for Coder IDE

- Goto "Setting, OS & Panel, Reinstall" and reinstall a fresh Debian OS on the box, whipping out everything
  - It will ask for a new root password, ensure you remember it!
- Goto "Security Firewall", and all SSH on 2222 (Hostinger standard) and then block everything else (drop any)
  - do not forget to click "sync" or the firewall will not be updated! 
- Click "Browser Terminal" to get in
- update system
```bash
apt update && apt upgrade -y
```
- Install Cloudflare Tunnel, to securely access all docker apps
  - once active you can just quiet on the 1st screen, you can add ther rest later
  - confirm cloudflared is visible
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
- install portainer, use included docker-compose.yml
  - start it up
  ```bash
  docker compose up -d
  ```
  - temporarily add in firewall rule to Hostinger to all 9443, so you can get portainer started up
  - "accept, TCP, 9443, Anywhere" and then sync
  - use ip address to get in
  ```bash
  https://xxx.xxx.xxx.xxx:9443
  ```
  - do portainer inital setup
- install coder, using the docker-compose.yml
  - first get the "docker group id", you will need this later
  ```bash
  getent group docker | cut -d: -f3
  ```
-   

   
