# Maintainer: Jesse R. Adams <jesse at techno-geeks dot org>
pkgname=mdocml
pkgver=1.12.3
pkgrel=4
pkgdesc="mandoc is a suite of tools compiling mdoc, the roff macro language of choice for BSD manual pages, and man, the predominant historical language for UNIX manuals."
arch=('i686 x86_64')
url="http://mdocml.bsd.lv/"
license=('ICL')
options=(strip !emptydirs staticlibs)
source=("LICENSE"
        "http://mdocml.bsd.lv/snapshots/${pkgname}-${pkgver}.tar.gz")
md5sums=('58e5774b92a4ac14a2604427594047b2'
         '5e805fc6b261b8374ce21d191721bf80')

build() {
  cd ${srcdir}/$pkgname-$pkgver
  make DBBIN=
}

package() {
  cd ${srcdir}/$pkgname-$pkgver
  make DESTDIR=${pkgdir} DBBIN= MANDIR=/usr/share/man PREFIX=/usr install
  mv ${pkgdir}/usr/bin/preconv ${pkgdir}/usr/bin/preconv-mdocml
  mv ${pkgdir}/usr/share/man/man7/man.7 ${pkgdir}/usr/share/man/man7/man-mdocml.7
  mv ${pkgdir}/usr/share/man/man7/mdoc.7 ${pkgdir}/usr/share/man/man7/mdoc-mdocml.7
  rm -rf "${pkgdir}/usr/share/examples"
}

# vim:set ts=2 sw=2 et:
