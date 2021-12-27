pkgname=libgpredict-git
pkgver=20150512
pkgrel=1
pkgdesc="This is an attempt at taking the prediction code used in Gpredict as shared lib."
arch=('i686' 'x86_64')
url="https://github.com/cubehub/libgpredict"
license=('GPL')
depends=()
makedepends=('make' 'git' 'cmake')
#_gitroot=https://github.com/phirsch/gqrx
#_gitroot=https://github.com/mathisschmieder/gqrx
_gitroot=git://github.com/cubehub/libgpredict.git
_gitname=libgpredict
conflicts=('libgpredict')
provides=('libgpredict')
source=("$_gitname::$_gitroot")
md5sums=('SKIP')
sha256sums=('SKIP')

pkgver() {
  cd "$_gitname"
  # disable $HOME to prevent git to use user's configuration
  HOME=/dev/null git log -1 --format="%cd" --date=short | tr -d '-'
}

build() {
	cd "$_gitname"
	cmake .
	make -j$(nproc)
}

package() {
	cd "$_gitname"
    make DESTDIR=$pkgdir install
}

# Install order: rtl-sdr-git, libuhd, gnuradio-git, gr-osmosdr-git, gqrx-git

