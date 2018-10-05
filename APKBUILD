# Contributor: Tero Hilpinen <tero.hilpinen@symbio.com>
# Maintainer: Tero Hilpinen <tero.hilpinen@symbio.com>

pkgname=x2goclient
pkgver=4.1.2.1
pkgrel=0
pkgdesc="Client for x2go"
depends="libatomic cups-libs mesa-gl qt5-qtbase qt5-qtsvg qt5-qttools qt5-qtx11extras libssh libx11 libxpm nx-libs openldap"
makedepends_build="bash qt5-qtbase-dev qt5-qtsvg-dev qt5-qttools-dev mesa-dev qt5-qtx11extras-dev libssh-dev libx11-dev libxpm-dev nx-libs-dev openldap-dev cups-dev"
makedepends_host=""
makedepends="$makedepends_build $makedepends_host"
source="https://code.x2go.org/releases/source/x2goclient/x2goclient-${pkgver}.tar.gz 0001-qt5.patch"
url="https://wiki.x2go.org"
arch="x86_64"
license=AGPL3
options="!check"
#subpackages="${pkgname}-doc ${pkgname}-dbg"

builddir="$srcdir/${pkgname}-${pkgver}"

prepare() {
	default_prepare || return 1
}

build() {
	cd "$builddir"
	export PREFIX=/usr
	make build_client || return 1
	make build_man || return 1
}

package() {
	cd "$builddir"
	export PREFIX=/usr
	make DESTDIR="$pkgdir" install_client || return 1
	make DESTDIR="$pkgdir" install_man || return 1
}

sha512sums="0dc4ef0b154c582e62d8e1c5fd0284510fd8c7ddac1d8f49638ca68244ac24f9220c9089e93a105cfa8978d1e2af9a4379deeb934d58741f51ee473ab041d369  x2goclient-4.1.2.1.tar.gz
c0bf138e1cbfd7e5bdc212158786db06ec44f29f72e316adcabb47c1175928d6468d0b271f8b653dac507d68e5d8bf6ae96e7a688ece6de6c8c92234ac3d450f  0001-qt5.patch"
