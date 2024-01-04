
# Antivius evation using shellter
shellter supports only 32bit so we nedd to enable 32 bit install archetechture
and install a wine that allow linux to exicute exe files
```
root@kali:~# dpkg --add-architecture i386
root@kali:~# apt update && apt install wine32
root@kali:~# shellter
