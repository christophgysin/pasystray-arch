# Maintainer: Christoph Gysin <christoph.gysin@gmail.com>
pkgname=pasystray
pkgver=0.5.2
pkgrel=1
pkgdesc="PulseAudio system tray (a replacement for padevchooser)"
arch=('i686' 'x86_64')
url="https://github.com/christophgysin/pasystray"
license=('LGPL')
groups=('multimedia')
depends=('libpulse' 'gtk3' 'libnotify' 'avahi' 'libx11' 'gnome-icon-theme')
makedepends=('pkg-config' )
optdepends=(
    'paman: Launch PulseAudio manager from tray icon'
    'pavucontrol: Launch PulseAudio mixer from tray icon'
    'pavumeter: Launch PulseAudio volume meter from tray icon'
    'paprefs: Launch PulseAudio preferences from tray icon'
)
source=("https://github.com/christophgysin/${pkgname}/archive/${pkgname}-${pkgver}.tar.gz")
md5sums=('0ea894a47a8ab10b830051e3bd89294d')

build() {
    cd $srcdir/$pkgname-$pkgname-$pkgver

    aclocal
    autoconf
    autoheader
    automake --add-missing
    ./configure \
        --prefix=/usr \
        --sysconfdir=/etc
    make
}

package() {
    cd $srcdir/$pkgname-$pkgname-$pkgver
    make DESTDIR="$pkgdir/" install
}
