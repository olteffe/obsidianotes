**update manjaro and install Go**
```bash
sudo pacman -Syu
sudo pacman -S go
```

-S: синхронизировать пакеты вашей системы с пакетами в официальном репозитории
-y: скачать свежие базы пакетов с сервера
-u: обновить все установленные пакеты
Лучше не использовать: “sudo pacman -Syyu” или “sudo pacman -Syuu” 
***

**NumLock On in Manjaro**
System Settings → Hardware → Input Devices → Keyboard → "Enable NumLock on startup"

If you also want to enable NumLock in the display manager ─ i.e. in the login screen ─ then you must edit the file /etc/sddm.conf by opening up a terminal window and typing...
```bash
sudo nano /etc/sddm.conf
```
Look at the second configuration block of the file, and change the NumLock setting from "off" to "on", as you can see in the snippet below...

	[General]
	HaltCommand=/usr/bin/systemctl poweroff
	InputMethod=
	Numlock=on
	RebootCommand=/usr/bin/systemctl reboot
***
**Рисование на экране KDE**

Включение: Параметры системы-Эффекты-Рисование мышью
Использование: зажать win+shift и мышкой рисовать. win+shift+F11 стирает все. 
Дважды нажмите Meta + Ctrl + Shift. Первое нажатие на стрелку. Второй в хвосте/конце. Чтобы удалить все отметки рисования: Meta + Shift + F11 Рисование от руки: удерживайте Meta + Shift и затем нарисуйте.
***

