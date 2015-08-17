# Contributor: Andrew Fyfe <andrew@neptune-one.net>
# Maintainer: Jonas Heinrich <onny@project-insanity.org>

pkgname='sgml-common'
pkgver='0.6.3'
pkgrel='3'
pkgdesc='Tools for maintaining centralized SGML catalogs.'
arch=('i686' 'x86_64')
url='http://www.docbook.org/xml/'
license=('custom')
install='sgml-common.install'
source=("ftp://sources.redhat.com/pub/docbook-tools/new-trials/SOURCES/sgml-common-${pkgver}.tgz"
        'sgml-common-0.6.3-manpage-1.patch')
sha512sums=('3c4a55f555596b2a6bf6af66c497679226e7b40625ac16832150488311cba7f9fc523435eea5837262a5517f5c09c4c0e07fe4a2cf02184d4027609c26e4bc0c'
			'c584ff6e66e1d58456c07849bf96fedd3f1df0b93430f6301c4d4ab9906821dea0cbac82eada19197540b5e31f13febd04fadda5b6e2ba4b0b6ee8f0328292f7')

prepare() {
	cd "${srcdir}/sgml-common-${pkgver}"
	patch -Np1 -i ../sgml-common-0.6.3-manpage-1.patch
}

build() {
	cd "${srcdir}/sgml-common-${pkgver}"
	autoreconf -f -i
	./configure --prefix=/usr --sysconfdir=/etc
	make
}
package(){
	cd "${srcdir}/sgml-common-${pkgver}"
	make DESTDIR="$pkgdir" install
}

# vim:set syntax=sh ts=4 sw=4 noet:
