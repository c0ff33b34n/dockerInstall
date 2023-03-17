# dockerInstall

# Uninstall Old Docker Versions:
sudo apt-get remove docker docker-engine docker.io containerd runc

# Set up the repository:
sudo apt-get update

# Install the needed package:
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# Add Docker’s official GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# The following command to set up the Docker stable repository:
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker:
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

# Checking for Docker version:
docker version

# Oneliner: 
wget https://raw.githubusercontent.com/c0ff33b34n/dockerInstall/main/dockerInstall.sh; chmod +x dockerInstall.sh; sudo ./dockerInstall.sh
