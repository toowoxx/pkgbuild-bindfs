pkgname=bindfs
pkgver=1.15.1
pkgrel=1
pkgdesc="FUSE filesystem that mirrors a directory to another directory, like 'mount --bind'"
arch=('x86_64')
url="https://bindfs.org"
license=('GPLv2')
depends=('fuse')
source=("https://bindfs.org/downloads/${pkgname}-${pkgver}.tar.gz")
sha256sums=('04dd3584a6cdf9af4344d403c62185ca9fab31ce3ae5a25d0101bc10936c68ab')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	./autogen.sh
	./configure --prefix=/usr
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="$pkgdir" install
}
