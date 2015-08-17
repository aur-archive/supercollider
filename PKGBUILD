# Maintainer : SpepS <dreamspepser at yahoo dot it>
# Contributor:  <farid at archlinux-br.org>

_name=SuperCollider
pkgname=supercollider
pkgver=3.5.2
pkgrel=1
pkgdesc="An environment and programming language for real time audio synthesis and algorithmic composition"
arch=('i686' 'x86_64')
url="http://supercollider.sourceforge.net/"
license=('GPL3')
depends=('jack' 'fftw' 'icu' 'cwiid' 'curl' 'qtwebkit')
makedepends=('cmake' 'ruby' 'vim' 'emacs')
optdepends=('emacs: emacs interface'
            'gedit: gedit interface'
            'vim: vim interface'
            'ruby: vim support')
install="$pkgname.install"
source=("http://download.sourceforge.net/project/$pkgname/Source/$pkgver/$_name-$pkgver-Source-linux.tar.bz2")
md5sums=('2bf4399ec9a7e37f155bafd018913bac')

build() {
  cd "$srcdir/$_name-Source"

  [ -d bld ] || mkdir bld && cd bld
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr \
           -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd "$srcdir/$_name-Source/bld"
  make DESTDIR="$pkgdir/" install
}
