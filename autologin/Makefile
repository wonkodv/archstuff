
install: autologin.conf
	sudo install -D -m644 autologin.conf /etc/systemd/system/getty@tty1.service.d/autologin.conf

autologin.conf: autologin-template
	sed s/USERNAME/$(USER)/ <$< >$@

