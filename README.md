
```bash
apt update
apt install -y \
    build-essential \
    git \
    subversion \
    cmake \
    libx11-dev \
    libxxf86vm-dev \
    libxcursor-dev \
    libxi-dev \
    libxrandr-dev \
    libxinerama-dev \
    libglew-dev
```


```bash
mkdir ~/blender-build
cd ~/blender-build
git clone https://github.com/blender/blender.git
```


```bash
mkdir ~/blender-build/lib
cd ~/blender-build/lib
svn checkout https://svn.blender.org/svnroot/bf-blender/trunk/lib/linux_centos7_x86_64
```


```bash
apt install -y python3
cd ~/blender-build/blender
make update
make
```


```bash
mkdir ~/release
cp -r ~/blender-build/build_linux ~/release/blender
cd ~/release
tar Jcf blender.tar.xz blender
```

```bash
cd ~/release
md5sum blender.tar.xz > blender.tar.xz.md5
```

