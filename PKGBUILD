# Maintainer: Pierre Kuhner <archlinux@pierrekuhner.fr>

_pkgname=ovh-ttyrec
pkgbase=ovh-ttyrec-bin
pkgname=ovh-ttyrec-bin
pkgver=1.1.6.7
pkgrel=1
pkgdesc='Enhanced (but compatible) version of the classic ttyrec'
arch=('x86_64')
url='https://github.com/ovh/ovh-ttyrec'
license=('BSD')
provides=('ttyrec')
conflicts=('ttyrec')
source=(
	"${_pkgname}_${pkgver}_amd64.deb::https://github.com/ovh/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_${pkgver}_amd64.deb"
	"LICENSE::https://raw.githubusercontent.com/ovh/${_pkgname}/v${pkgver}/LICENSE"
)
sha256sums=(
	'93e3a8e795c3e0942724d23bdb574509c12b603ae16bd1a9be81ef9ed62e7483'
	'7e989e04eb9099e3be5b613a63f79744d275e26dea1392ce199e80ce3824960a'
)
noextract=("${_pkgname}_${pkgver}_amd64.deb")

prepare() {
	mkdir -p "${_pkgname}"
	bsdtar -xf "${_pkgname}_${pkgver}_amd64.deb" -C "${_pkgname}"
}

package() {
	tar -xf "${_pkgname}/data.tar.xz" -C "${_pkgname}"
	mkdir -p "$pkgdir/usr/bin"
	cp -r "$srcdir/${_pkgname}/usr/bin" "$pkgdir/usr/"

	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
