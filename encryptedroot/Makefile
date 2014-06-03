diff:
	colordiff /usr/lib/initcpio/hooks/encrypt encrypt_hook

install:
	sudo install -D -m644 encrypt_hook /usr/lib/initcpio/hooks/encrypt
	sudo mkinitcpio -p linux
