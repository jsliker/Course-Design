CC=gcc
AFLAGS=-Wall -g
LDFLAGS= -lmysqlclient
OBJS= add.cgi del.cgi mod.cgi sel.cgi selsc.cgi selc.cgi modc.cgi addc.cgi addsc.cgi delc.cgi recovery.cgi

all:$(OBJS)

$(OBJS):%.cgi:%.c
	$(CC) $(AFLAGS) $< cgic.c -o $@ $(LDFLAGS)

.PHONY:clean
clean:
	rm ./*.cgi

install:
	cp *.cgi /usr/lib/cgi-bin/sx/

	cp head.html /usr/lib/cgi-bin/sx/

	sudo cp -r public/ index.html teacher.html /var/www/html/
