# ASUS FAN

A simple GUI that works with asusctl to control fan curves. It uses a graph to streamline the approach.

# PREREQUISITES

Before installing, ensure your system has the following:

asusctl (The underlying driver for Asus hardware)

# QUICK INSTALL

If you have downloaded the pre-compiled Asus_Fan binary, run this command from the folder where it was downloaded:

```
tar -xvzf Asus_Fan.tar.gz && \
sudo mv ./Asus_Fan /usr/bin/asus-fan && \
sudo chmod +x /usr/bin/asus-fan && \
echo -e "[Desktop Entry]\nType=Application\nName=Asus Fan\nComment=Graph-based Fan Curve Management\nExec=/usr/bin/asus-fan\nIcon=fan\nTerminal=false\nCategories=Settings;HardwareSettings;" > ~/.local/share/applications/asus-fan.desktop && \
update-desktop-database ~/.local/share/applications/
```

# MANUAL BUILD

If you prefer to build from source, ensure you have your compiler and GTK3 headers configured:
Bash

```
# 1. Extract the files
tar -xvzf Asus_Fan.tar.gz && \

# 2. Compile fresh from the extracted source
g++ -O3 Asus_Fan.cpp -o asus-fan $(pkg-config --cflags --libs gtk+-3.0) -lpthread && \

# 3. Move and setup the system environment
sudo mv ./asus-fan /usr/bin/asus-fan && \
sudo chmod +x /usr/bin/asus-fan && \
echo -e "[Desktop Entry]\nType=Application\nName=Asus Fan\nComment=Graph-based Fan Curve Management\nExec=/usr/bin/asus-fan\nIcon=fan\nTerminal=false\nCategories=Settings;HardwareSettings;" > ~/.local/share/applications/asus-fan.desktop && \
update-desktop-database ~/.local/share/applications/
```

USAGE

Launcher: Search for Asus Fan in your application menu.

Terminal: Simply type asus-fan.

Note: The application pulls its icon from GitHub to ensure portability across different systems. Ensure curl is installed for the icon to load correctly.
