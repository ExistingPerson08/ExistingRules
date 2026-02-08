pkgname=existing-rules-git
_gitname=ExistingRules
pkgver=20230613.r319.gf139cf4
pkgrel=1
groups=('Spacefin')
arch=('any')
license=('GPL')
pkgdesc='ExistingPerson08s opinionated ananicy-cpp rules'
url='https://github.com/ExistingPerson08/ExistingRules/'
depends=('ananicy-cpp')
makedepends=('git')
source=("git+https://github.com/ExistingPerson08/$_gitname")
sha256sums=('SKIP')
backup=(etc/ananicy.d/ananicy.conf)

pkgver() {
  cd $_gitname
  echo "$(git show --format='%cI' -q master | sed 's/T.*//g;s/-//g').r$(git rev-list --count HEAD).g$(git rev-parse --short HEAD)"
}

prepare() {
  cd $_gitname
  rm -f README.md
}

package() {
  cd $_gitname
  install -d "$pkgdir/etc/ananicy.d"
  cp -rf $srcdir/$_gitname/* "$pkgdir/etc/ananicy.d"
}
