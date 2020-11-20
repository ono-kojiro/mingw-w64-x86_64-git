_realname=git
pkgbase=mingw-w64-${_realname}
pkgname=("${MINGW_PACKAGE_PREFIX}-${_realname}")
pkgver=2.29.2.windows.2
pkgrel=1
pkgdesc="The fast distributed version control system"
arch=('any')
url='https://gitforwindows.org/'
license=('GPL3')
depends=('mingw-w64-x86_64-pcre2')
source=("https://github.com/git-for-windows/git/archive/v2.29.2.windows.2.tar.gz")
sha256sums=('5051f0a96ece055597ddf680561f7ecfdb106857f570bfa1e2f70bb874628b8a')

prepare() {
  cd $srcdir/${_realname}-${pkgver}
}

build() {
  cd $srcdir/${_realname}-${pkgver}
  
#  ./configure --prefix=${MINGW_PREFIX} \
#    --build=${MINGW_CHOST} \
#    --host=${MINGW_CHOST} \
#    --target=${MINGW_CHOST}

  make
}

package() {
  cd ${srcdir}/${_realname}-${pkgver}
  make install DESTDIR="${pkgdir}"

  # Licenses
  #install -Dm644 "${srcdir}/${_realname}-${pkgver}/README" "${pkgdir}${MINGW_PREFIX}/share/licenses/${_realname}/README"
  #install -Dm644 "${srcdir}/${_realname}-${pkgver}/COPYING" "${pkgdir}${MINGW_PREFIX}/share/licenses/${_realname}/COPYING"
}
