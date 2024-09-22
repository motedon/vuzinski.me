to check not used packages:
```
pacman -Qqd | pacman -Rsu --print -
```
shows every package?
```
pacman -Qtd
```
and then remove accordingly with
```
pacman -R "package name"
```

