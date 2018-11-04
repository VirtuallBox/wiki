---
title: Рекомендации
category: Конфигурирование системы
order: 2
permalink:
post_video: 
post_photo_path: 
comments: true
edit: true
---

### Установка ядра Linux-zen [Kernels](https://wiki.archlinux.org/index.php/Kernels){:target="_blank"}.

Если у вас nvidia карта, драйвер также нужно заменить `sudo pacman -S nvidia-390xx-dkms`.
```bash
sudo pacman -S linux-zen linux-zen-headers
sudo mkinitcpio -p linux-zen
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

---

### Убиваем тиринг на свободных дровах nvidia (nouveau).

Как установить свободные видео драйвера см. [здесь](https://wiki.archlinux.org/index.php/Nouveau){:target="_blank"}.

В **xfce** данную проблему решает compton `pacman -S compton`, с флагами. Добавить в автостарт данную команду.
```bash
compton -b --paint-on-overlay --unredir-if-possible --backend xr_glx_hybrid --vsync drm --glx-swap-method -1 --glx-no-stencil
```