# For fakeroot Do not delete it
DESTDIR =

VERSION = $(shell cat VERSION)
PACKAGE = myaptkey

KEY_ID = $(shell cat CURRENT_KEYID)
KEY_FILE = key.txt

RELEASE_FILES = \
	key.txt COPYING

FULLNAME = $(PACKAGE)-$(VERSION)
ORIG_ARCHIVE_FILE = release/$(FULLNAME).tar.bz2

DEB_BASENAME = $(PACKAGE)_$(VERSION)
# TODO -1 suffix
DEBNAME = $(DEB_BASENAME)-1_all.deb
DEBFILE = release/$(DEBNAME)
DEBFILES = $(DEB_BASENAME)*

RELEASE_APT_DIR = /var/www/localnet/debian/apt/


update:
	gpg --export --armour $(KEY_ID) > $(KEY_FILE)

scripts/sh-functions: $(KEY_FILE) scripts/sh-functions.template
	compose-file -o scripts/sh-functions scripts/sh-functions.template; \

$(KEY_FILE): update

archive: $(ORIG_ARCHIVE_FILE)

update-debian: scripts/sh-functions
	for template in debian/*.template; do \
		compose-file -o $${template%.template} $${template}; \
	done

deb: $(DEBFILE)

publish: deb
	sudo cp -p $(DEBFILE) $(RELEASE_APT_DIR)
	cd $(RELEASE_APT_DIR) && sudo ./publish

$(ORIG_ARCHIVE_FILE): VERSION
	rm -rf /tmp/$(FULLNAME)
	mkdir -p /tmp/$(FULLNAME)
	cp --parents $(RELEASE_FILES) /tmp/$(FULLNAME)
	tar cjvf ./release/$(FULLNAME).tar.bz2 -C /tmp $(FULLNAME);

# invoke with LANG=C to prepare passphrase prompt in Emacs `shell-command'
$(DEBFILE): archive update-debian $(ORIG_ARCHIVE_FILE)
	LANG=C dpkg-buildpackage
	cp ../$(DEBFILES) ./release/

