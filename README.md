# mcp

On a Fedora Workstation, we'll use a toolbox to isolate our playground.
```
# Create a Fedora toolbox and enter it
toolbox create
toolbox enter
```
Use the unofficial port of [claude-desktop-fedora.](https://github.com/bsneed/claude-desktop-fedora). Thank you to the maintainer of that project!!

NOTE: I had to manually install nodejs, sqlite3, nss, atk, at-spi2-atk and gtk3 into the toolbox. This may not be required if you are running directly in your Fedora Workstation environment, and not in a toolbox, as the default Workstation includes these.
```
# In the toolbox, install sqlite3, nodejs and a few other packages
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



