# Maintainer: jfperini <@jfperini>
# Contributor: jfperini <@jfperini>

pkgname=flattr-icons-kde-kaosx-git
pkgver=0.9.7+r279.f42ce47
pkgrel=1
pkgdesc="Flattr is an icon theme for Linux desktops, the set is inspired by the latest flat design trend."
url="https://github.com/KaOSx/flattr-icons-kde"
arch=('any')
license=('CC BY-NC-SA 4.0')
depends=('librsvg')
makedepends=('git')
conflicts=('flattr-icons','flattr-icon-theme','flattr-icon-theme-git')
provides=('flattr-icon-theme')
source=("$pkgname"::'git+https://github.com/KaOSx/flattr-icons-kde.git')
# Because the sources are not static, skip Git checksum:
md5sums=('SKIP')

pkgver() {
  
    cd "$srcdir/$pkgname"
  
    # Use the tag of the last commit
    printf "0.9.7+r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {

    cd "$srcdir/$pkgname"
  
    msg2 "  -> Installing icons..."
    install -dm755 "$pkgdir/usr/share/icons/Flattr"
  
    rm -rf {.git,.gitignore,CONTRIBUTORS,COPYING,CREDITS,LICENSE.txt,README.md}
    cp -r . "$pkgdir/usr/share/icons/Flattr/"
    
}
