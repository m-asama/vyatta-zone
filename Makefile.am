cfgdir            = $(datadir)/vyatta-cfg/templates
opdir		  = $(datadir)/vyatta-op/templates
share_perl5dir	  = $(datarootdir)/perl5/Vyatta
bin_sudo_usersdir = $(bindir)/sudo-users

curverdir = $(sysconfdir)/config-migrate/current
curver_DATA = cfg-version/zone-policy@1

bin_SCRIPTS = scripts/vyatta-show-zone.pl

sbin_SCRIPTS  = scripts/vyatta-zone.pl

share_perl5_DATA  = lib/Vyatta/Zone.pm

cpiop = find  . ! -regex '\(.*~\|.*\.bak\|.*\.swp\|.*\#.*\#\)' -print0 | \
  cpio -0pd

install-exec-hook:
	mkdir -p $(DESTDIR)$(cfgdir)
	cd templates-cfg; $(cpiop) $(DESTDIR)$(cfgdir)
	cd templates-op; $(cpiop) $(DESTDIR)$(opdir)
