# Maintainer: Andrey Vihrov <andrey.vihrov at gmail.com>

pkgname=sbupdate-git
pkgver=0.r113.4e6d106
pkgrel=1
pkgdesc="Generate single file kernel images for EFI normal Boot - not secure!"
arch=('any')
url="https://github.com/drakenson/sbupdate"
license=('GPL3')
install=notsbupdate.install
depends=('bash>=4.4' 'systemd' 'binutils')
makedepends=('git')
conflicts=('sbupdate')
provides=('sbupdate')
backup=('etc/notsbupdate.conf')
source=("git+https://github.com/drakenson/sbupdate.git")
sha256sums=('SKIP')

pkgver() {
  cd notsbupdate
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd notsbupdate
  make DESTDIR="${pkgdir}" DOCDIR="/usr/share/doc/${pkgname}" install
}

# vim:set ts=2 sw=2 et: