INSTALL ?= install
SHELLCHECK ?= shellcheck

.PHONY: all check install

all:

check:
	$(SHELLCHECK) notsbupdate

install:
	$(INSTALL) -D -m 0755 -t "$(DESTDIR)/usr/bin" notsbupdate
	$(INSTALL) -D -m 0644 -t "$(DESTDIR)/etc" notsbupdate.conf
	$(INSTALL) -D -m 0644 -t "$(DESTDIR)/usr/share/libalpm/hooks" \
      $(addprefix hooks/,95-notsbupdate.hook 50-notsbupdate-remove.hook 50-fwupd-sign.hook)
	$(INSTALL) -D -m 0644 -t \
      "$(DESTDIR)$(or $(DOCDIR),/usr/share/doc/notsbupdate)" README.md
