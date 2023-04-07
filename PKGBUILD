# Maintainer: Chris Down <chris@chrisdown.name>

pkgname=clipmenu-spmenu
_gitname=clipmenu-spmenu
pkgver=6.2.0.r21.g87c4102
pkgrel=1
pkgdesc='Clipboard management using dmenu'
url='http://github.com/speediegq/clipmenu-spmenu'
arch=('any')
license=('Public Domain')
depends=(spmenu xsel clipnotify)
provides=(clipmenu)
conflicts=(clipmenu)
makedepends=(git)

source=(git+https://github.com/speediegq/clipmenu-spmenu.git)
md5sums=('SKIP')

pkgver() {
    cd "${srcdir?}/$_gitname"
    git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
    install -D -m755 \
        "${srcdir?}/$_gitname/clipmenu" \
        "${pkgdir?}/usr/bin/clipmenu"
    install -D -m755 \
        "${srcdir?}/$_gitname/clipmenud" \
        "${pkgdir?}/usr/bin/clipmenud"
    install -D -m755 \
        "${srcdir?}/$_gitname/clipdel" \
        "${pkgdir?}/usr/bin/clipdel"
    install -D -m755 \
        "${srcdir?}/$_gitname/clipctl" \
        "${pkgdir?}/usr/bin/clipctl"
    install -D -m644 \
        "${srcdir?}/$_gitname/init/clipmenud.service" \
        "${pkgdir?}/usr/lib/systemd/user/clipmenud.service"
}
