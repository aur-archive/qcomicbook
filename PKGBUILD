# Maintainer: kagan <juanynie AT gmail DOT com>
# Contributor: Valheru <valheru AT facticius DOT net>
# Contributor: jackoneill

pkgname=qcomicbook
pkgver=0.9.0
pkgrel=4
pkgdesc="QComicBook is a viewer for comic book archives"
url="http://qcomicbook.org/"
arch=('i686' 'x86_64')
license="GPL"
depends=('qt4' 'unrar' 'p7zip' 'tar' 'poppler-qt4')
optdepends=('unzip' 'unace')
makedepends=('cmake')
source=("http://qcomicbook.org/releases/$pkgname-$pkgver.tar.gz")
md5sums=('b209bfb081afd4c06eedb6bb08f957f0')

build() {
   cd "$srcdir/$pkgname-$pkgver"
   #rm -rf build-dir
   #mkdir -p build-dir
   #cd build-dir
   
   cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release \
	 -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake-qt4
   
   make
}

package() {
   cd "$srcdir/$pkgname-$pkgver"
   make DESTDIR="$pkgdir" install
}