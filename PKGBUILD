# Contributor: Arch Haskell Team <arch-haskell@haskell.org>
# Contributor: Lex Black <autumn-wind at web dot de>

_hkgname=twitter
pkgname=twitter
pkgver=0.1.1
pkgrel=4
pkgdesc="A Haskell-based CLI Twitter client"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-curl' 'haskell-directory' 'haskell-filepath' 'haskell-json' 'haskell-mtl' 'haskell-old-locale' 'haskell-readline' 'haskell-time' 'haskell-xml')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
md5sums=('35237080a5f386e8a60d67af4c1e064c')

build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}

package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}

