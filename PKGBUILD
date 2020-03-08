## $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=ssu-sysinfo-git
pkgver=1.2.1.r0.g3a4fa10
pkgrel=1
pkgdesc="Tools and libraries for getting ssu information without D-Bus IPC"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/ssu-sysinfo"
license=('GPL')
makedepends=('git' 'check')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/ssu-sysinfo.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/${pkgname%-git}"
    util/verify_version.sh
    unset LD_AS_NEEDED
	make
}

package() {
	cd "$srcdir/${pkgname%-git}"
	make DESTDIR="$pkgdir/" install
}
