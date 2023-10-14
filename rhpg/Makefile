all: install

install: rhpg

rhpg:
	dnf install -y curl epel-release coreutils-single grep
	dnf -y module enable postgresql:${PGVERSION}
	dnf install -y postgresql-server
	dnf -y install --enablerepo=powertools hdf5
