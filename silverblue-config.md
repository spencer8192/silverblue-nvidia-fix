# Initial setup for NVIDIA drivers
```
sudo dnf install mirrors.rpmfusion.org(rpm -E %fedora).noarch.rpm mirrors.rpmfusion.org(rpm -E %fedora).noarch.rpm
rpm-ostree install akmod-nvidia xorg-x11-drv-nvidia-cuda
sudo rpm-ostree kargs   --append=rd.driver.blacklist=nouveau   --append=modprobe.blacklist=nouveau   --append=nvidia-drm.modeset=1  --append=nvidia.NVreg_PreserveVideoMemoryAllocations=1
```

```
sudo systemctl enable nvidia-suspend.service
sudo systemctl enable nvidia-resume.service
sudo systemctl enable nvidia-hibernate.service
```

