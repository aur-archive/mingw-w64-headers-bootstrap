# Maintainer: rubenvb vanboxem <dottie> ruben <attie> gmail <dottie> com
pkgname=mingw-w64-headers-bootstrap
pkgver=3.0.0
pkgrel=1
pkgdesc="MinGW-w64 headers for Windows (bootstrap)"
arch=('any')
url="http://mingw-w64.sourceforge.net"
license=('custom')
groups=('mingw-w64-bootstrap' 'mingw-w64')
depends=()
makedepends=('mingw-w64-headers')
optdepends=()
provides=()
conflicts=('mingw-w64-winpthreads', 'mingw-w64-winpthreads-svn')
replaces=()
backup=()
options=('!strip' '!libtool' '!emptydirs')
source=()
md5sums=()

_targets="i686-w64-mingw32 x86_64-w64-mingw32"
_dummystring="/* Dummy header, which gets overriden, if winpthread library gets installed.  */"

build() {
  mkdir -p ${srcdir}/dummy/ && cd ${srcdir}/dummy
  
  echo "${_dummystring}" > pthread_signal.h
  echo "${_dummystring}" > pthread_time.h
  echo "${_dummystring}" > pthread_unistd.h
}

package() {
  for _target in ${_targets}; do
    install -Dm644 ${srcdir}/dummy/pthread_signal.h ${pkgdir}/usr/${_target}/include/pthread_signal.h
    install -Dm644 ${srcdir}/dummy/pthread_time.h ${pkgdir}/usr/${_target}/include/pthread_time.h
    install -Dm644 ${srcdir}/dummy/pthread_unistd.h ${pkgdir}/usr/${_target}/include/pthread_unistd.h
  done
}

