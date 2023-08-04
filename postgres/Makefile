all: install

install: postgres

postgres:
	dnf install -y curl epel-release coreutils-single grep
	dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-8-x86_64/pgdg-redhat-repo-latest.noarch.rpm
	uname -m | grep -q aarch64 && curl https://download.postgresql.org/pub/repos/yum/RPM-GPG-KEY-PGDG-AARCH64-RHEL8 -o /etc/pki/rpm-gpg/RPM-GPG-KEY-PGDG || uname -m
	dnf -qy module disable postgresql
	dnf install -y postgresql$(PGVERSION)-server
