
default:	build

clean:
	rm -rf Makefile objs

build:
	$(MAKE) -f objs/Makefile
	$(MAKE) -f objs/Makefile manpage

install:
	$(MAKE) -f objs/Makefile install

upgrade:
	run/sbin/nginx -t

	kill -USR2 `cat run/logs/nginx.pid`
	sleep 1
	test -f run/logs/nginx.pid.oldbin

	kill -QUIT `cat run/logs/nginx.pid.oldbin`
