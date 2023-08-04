AUTOMAKEVERSION ?= $(shell automake --version | sed -n '1{s/.* //;p}' | grep -oE '[0-9]+\.[0-9]+')
BISONVERSION ?= 2.3
FLEXVERSION ?= 2.5.39

all: install

install: buildtools bison flex

bison:
	cd $(shell mktemp -d) && curl http://ftp.gnu.org/gnu/bison/bison-$(BISONVERSION).tar.gz -O && tar -xvzf bison-$(BISONVERSION).tar.gz && cd bison-$(BISONVERSION) && ln -sf /usr/share/automake-$(AUTOMAKEVERSION)/config.guess ./build-aux/config.guess && ./configure --prefix=/usr/local/bison --with-libiconv-prefix=/usr/local/libiconv/ && make all install

flex:
	cd $(shell mktemp -d) && curl -L http://prdownloads.sourceforge.net/flex/flex-$(FLEXVERSION).tar.gz?download -o flex-$(FLEXVERSION).tar.gz && tar -xvzf flex-$(FLEXVERSION).tar.gz && cd flex-$(FLEXVERSION) && ./configure --prefix=/usr/local/flex && make all install

buildtools: linux-buildtools pg-buildtools

linux-buildtools:
	dnf install -y --nogpgcheck curl vim epel-release dos2unix bc rpmdevtools rpm-build
	dnf --enablerepo=powertools install -y perl-IPC-Run hdf5-devel
	dnf groupinstall -y "Development Tools"

pg-buildtools:
	dnf install -y postgresql$(PGVERSION)-devel postgresql$(PGVERSION)-libs libpq5-devel
