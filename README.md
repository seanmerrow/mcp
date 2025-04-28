# mcp

On a Fedora Workstation, we'll use a toolbox to isolate our playground.
```
# Create a Fedora toolbox and enter it
toolbox create
toolbox enter
```
The following steps follow those from the [claude-desktop-fedora.](https://github.com/bsneed/claude-desktop-fedora) project. Thank you to the creator/maintainer!!
```
# Install the following dependencies if they aren't already installed
sudo dnf install -y sqlite3 nodejs \
    nss atk at-spi2-atk gtk3

# Clone this repository
git clone https://github.com/bsneed/claude-desktop-fedora.git
cd claude-desktop-fedora

# Build the package
sudo ./build-fedora.sh

# Install the generated claude-desktop rpm (your version may be differnt)
sudo dnf install build/electron-app/x86_64/claude-desktop-0.9.2-1.fc41.x86_64.rpm
```
That's it. Now you should be able to start up claude-desktop in the toolbox.
```
claude-desktop
```



