# Maintainer: Florian Bruhin (The Compiler) <archlinux.org@the-compiler.org>
# Contributor: Thorsten Toepper <atsutane@freethoughts.de>

pkgname=newsbeuter-duncan
pkgver=1874.56c8c2c
pkgrel=1
pkgdesc='A RSS feed reader for the text console with special Podcast support.'
url='http://www.newsbeuter.org'
arch=('i686' 'x86_64')
license=('MIT')
depends=('sqlite3' 'curl' 'libxml2' 'stfl' 'json-c')
optdepends=('ruby')
makedepends=('git' 'swig' 'asciidoc' 'docbook-xsl' 'pkgconfig')
options=('docs' '!libtool')
conflicts=('newsbeuter')
source=('git://github.com/Duncanla/newsbeuter.git#branch=duncan')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/newsbeuter"
  echo $(git rev-list --count makepkg).$(git rev-parse --short makepkg)
}

build() {
  cd "$srcdir/newsbeuter"
  ./config.sh
  make
  make doc
}

package() {
  cd "$srcdir/newsbeuter"

  make prefix=/usr "DESTDIR=${pkgdir}" install
  install -Dm644 LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

}

# vim:set ts=2 sw=2 et:

