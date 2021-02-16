<p align="center">
<img src="https://github.com/system76/pop-gtk-theme/raw/master/Pop_gtk-logo.png"/>
</p>

-------------------

A Snap that exports GTK+ and icon theme of Pop!_OS: [pop-gtk-theme](https://github.com/pop-os/gtk-theme), [pop-icon-theme](https://github.com/pop-os/icon-theme).

### Prerequisites for this snap:

```bash
# installs Pop!_OS gtk-theme and icon-theme
sudo apt install pop-gtk-theme pop-icon-theme
```

### Installation

```bash
# installs pop-themes
sudo snap install pop-themes
```
### After-Installation
To connect pop-themes to all apps which have available plugs to gtk-common-themes please run:

```bash
#For Pop!_OS GTK2 for GTK2-snaps (need to be done everytime you install a new GTK2-snap app)

for i in $(snap connections | grep gtk-common-themes:gtk-2-themes | awk '{print $2}'); do sudo snap connect $i pop-themes:gtk-2-themes; done
```

```bash
# For Pop!_OS GTK3 for GTK3-snaps (need to be done everytime you install a new GTK3-snap app)
for i in $(snap connections | grep gtk-common-themes:gtk-3-themes | awk '{print $2}'); do sudo snap connect $i pop-themes:gtk-3-themes; done
```

```bash
# For Pop!_OS icons for snaps (need to be done everytime you install a new snap app)
for i in $(snap connections | grep gtk-common-themes:icon-themes | awk '{print $2}'); do sudo snap connect $i pop-themes:icon-themes; done
```
