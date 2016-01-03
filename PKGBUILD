#Maintainer: burntcookie90 <aur at vishnurajeevan dot com>

_gitname=i3lock-fancy
pkgname=i3lock-fancy-git
pkgver=r32.9165a99
pkgrel=1
license=('MIT')
url="https://github.com/meskarune/i3lock-fancy"
arch=('i686' 'x86_64')
provides=("i3lock-fancy")
depends=('imagemagick' 'i3lock-color-git' 'scrot' 'ttf-liberation')
makedepends=('git')
source=("git+https://github.com/meskarune/$_gitname.git")
md5sums=('SKIP')

pkgver() {
  cd "$_gitname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    patch -N ${srcdir}/${_gitname}/lock ../package.patch
}
package() {
    cd "${srcdir}/$_gitname"
    install -Dm755 lock ${pkgdir}/usr/bin/i3lock-fancy
    install -Dm644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    install -Dm644 lock.png ${pkgdir}/usr/share/${pkgname}/lock.png
    install -Dm644 lockdark.png ${pkgdir}/usr/share/${pkgname}/lockdark.png
}
