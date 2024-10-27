# Ubuntu

⚡ Building a linuxcnc version for ubuntu ⚡

## License

[![License:Apache2.0](https://img.shields.io/badge/License-Apache2.0-yellow.svg)](https://opensource.org/licenses/Apache2.0)

## Compile device requirements

Must be: D-Robotics RDK X5

## Compile environment

Must be: Ubuntu 22.04.5 (Python 3.10.12)

## Linuxcnc version

Must be: [Linuxcnc 2.9.3](https://github.com/LinuxCNC/linuxcnc/tree/v2.9.3)

## Start compiling

1、Ensure that the ubuntu system is at the latest version.

```shell
sudo apt update && sudo apt upgrade
```

2、Install the necessary dependencies for compilation in ubuntu.

```shell
sudo apt install -y dpkg-dev build-essential libudev-dev libmodbus-dev libgtk-3-dev libgtk2.0-dev yapps2 intltool bwidget tclx libeditreadline-dev libxmu-dev libxmu-headers asciidoc dh-python imagemagick netcat-openbsd po4a python3-xlib xvfb
```

3、Download linuxcnc 2.9.3 source code to ubuntu system.

```shell
git clone -b v2.9.3 --depth 1 git@github.com:LinuxCNC/linuxcnc.git
cd linuxcnc
# or
wget https://github.com/LinuxCNC/linuxcnc/archive/refs/tags/v2.9.3.tar.gz
tar -xzf v2.9.3.tar.gz
cd linuxcnc-2.9.3
```

4、Compile and build DEB installation files.

```shell
./debian/configure no-docs uspace
dpkg-buildpackage -b -uc -j8
```

## Install

Compile the generated deb file in the higher-level directory and install it directly using the following script.

```shell
sudo apt install libespeak1 libespeak-ng1 libpcaudio0 libsonic0 python3-pyqt5.sip libqscintilla2-qt5-15 libgtksourceview-3.0-1 gir1.2-gtksource-3.0 mesa-utils-bin
```

```shell
sudo apt install mesa-utils python3-opengl python3-configobj libgtksourceview-3.0-dev tclreadline python3-pyqt5 python3-pyqt5.qsci python3-pyqt5.qtsvg python3-pyqt5.qtopengl python3-espeak python3-dbus.mainloop.pyqt5 python3-pyqt5.qtwebengine espeak-ng espeak pyqt5-dev-tools gstreamer1.0-tools python3-poppler-qt5
```

```shell
sudo dpkg -i ../linuxcnc*.deb
```

> If there are dependency issues, you can execute `sudo apt -- fix broken install`

## Install armcnc

Follow the instructions of [armcnc](https://github.com/armcnc/armcnc) to complete the subsequent installation operations

## Thank

[D-Robotics](https://github.com/d-robotics)

[Linuxcnc](https://github.com/LinuxCNC/linuxcnc)

[EtherCAT](https://download.opensuse.org/repositories/science:/EtherLab/Debian_12/arm64/)

[Ubuntu](https://github.com/ubuntu)