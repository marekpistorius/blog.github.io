---
layout: post
title:  "Fix klávesy scrollock"
date:   2015-11-06 22:45:22 +0000
categories: welcome update scrolllock klávesa
---
Jeden kratky fix, pro ty komu nefunguje scroll lock na PS/2 klavesnici (asi i usb ....).
Přikazem <strong>xmodmap</strong> zjitíme , či je mod3 prazdný ,


	$ xmodmap 
	xmodmap:  up to 4 keys per modifier, (keycodes in parentheses):
	
	shift       Shift_L (0x32),  Shift_R (0x3e)
	lock        Caps_Lock (0x42)
	control     Control_L (0x25),  Control_R (0x69)
	mod1        Alt_L (0x40),  Meta_L (0xcd)
	mod2        Num_Lock (0x4d)
	mod3      
	mod4        Super_L (0x85),  Super_R (0x86),  Super_L (0xce),  Hyper_L (0xcf)
	mod5        ISO_Level3_Shift (0x5c),  Mode_switch (0xcb)


pokud je tak zadáme xmodmap -e "add mod3 = Scroll_Lock", 
pokud pak funguje stačí přidat řadku 
	add mod3 = Scroll_Lock 
pomocí vašeho oblibeneho editor textu do /etc/X11/Xmodmap (na konec). 
např.
	sudo nano /etc/X11/Xmodmap 

Zdroj informace nalezen někde pomoci Google (nepomatuju se kde presně už...)

