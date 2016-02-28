pkgname=pixiewps-git
_pkgname=pixiewps
pkgver=r26.08a78c3
pkgrel=1
pkgdesc="Offline bruteforce of the WPS pin exploiting the low or non-existing entropy of some APs"
arch=('armv7h')
url="https://github.com/wiire/pixiewps"
license=('GPL')
depends=('openssl')
makedepends=('git')
conflicts=('pixiewps')
provides=('pixiewps')
source=(git+https://github.com/wiire/pixiewps.git)
md5sums=('SKIP')

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$_pkgname"/src/
	make
}

package() {
	cd "$_pkgname"/src
	make PREFIX="$pkgdir/usr" install
}
