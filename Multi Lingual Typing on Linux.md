2:58 in the morning 16.09.2024
I have successfully made it, now my arch linux setup has multi lingual typing support that doesn't break like IBUS, FCITX5 is the best, it took a while to configure
result:

xin chào bạn có khỏe không
ето как ги пиша тия неща
hello world how are you today

i have successfully made it
успях баце, страшен съм
đã làm đc rồi, tôi thực sự có lúc rất giỏi.

So here is the procedure:
Install from the arch repository (not AUR)
```
sudo pacman -S fcitx5 fcitx5-bamboo
```
and and install the GUI tool
```
sudo pacman -S fcitx5-configtool (for KDE)
```
one last configuration is for Xwayland thing:
```
kate /etc/environment
```
after opening with Kate or your favorite editor then append this:
```
XMODIFIERS=@im=fcitx
```
choose your languages, in my case, Bulgarian, Vietnamese (from bamboo, set it to telex) and English

But here is the thing right:
Obsidian is an electron app, vscode is also, but on vscode, I opened it and I can still type in Vietnamese there, but in obsidian I can't
so in the documentation it says to run an app with specific arguments:
```
--enable-features=UseOzonePlatform --ozone-platform=wayland --enable-wayland-ime
```
https://fcitx-im.org/wiki/Using_Fcitx_5_on_Wayland#KDE_Plasma

So I tried starting obsidian using the terminal while also adding those arguments up there so the final command will be like this (after opening the terminal):
```
obsidian --enable-features=UseOzonePlatform --ozone-platform=wayland --enable-wayland-ime
```
and everything worked, typing was as expected on all 3 languages
But here is the thing: now I can only start the application with those arguments ONLY using the terminal? That is a bit inconvenient, well here is the solution:
Find the application in the app drawer, right click and click "edit application"
it will show a window that will say "properties for obsidian.desktop"
go to the "Application" tab and find the "Arguments" section
Paste the entire shit there:
```
--enable-features=UseOzonePlatform --ozone-platform=wayland --enable-wayland-ime
```
and then apply/OK and close that window.

Voila, now every time you open Obsidian, you will open it with those arguments, no need to use the terminal.
VERY FUCKING COOL.
now of course typing with all languages work and we GUCCI.
enjoy.