# Maintainer: Jerome Leclanche <jerome@leclan.ch>

pkgname=foliate
pkgver=2.6.4
pkgrel=1
pkgdesc="A simple and modern GTK eBook reader"
arch=("x86_64")
groups=('modified')
url="https://johnfactotum.github.io/foliate/"
license=("GPL3")
depends=("gjs" "iso-codes" "webkit2gtk")
makedepends=("meson" "ninja" "gettext")
optdepends=(
	"dictd: Offline dictionary support"
	"espeak-ng: Text-to-speech support; also voice package needed"
	"festival: Text-to-speech support; also voice package needed"
	"gspell: Spell-checking support"
	"hyphen: Auto-hyphenation support"
	"tracker3"
)
source=("$pkgname-$pkgver.tar.gz"::"https://github.com/ttys3/foliate/archive/$pkgver.tar.gz")
sha256sums=("cd2b339f5ca468cf0aded145caf64823ddaf988d8161ba6331cb2c346f7348eb")


build() {
	cd "$srcdir/$pkgname-$pkgver"
	meson build --prefix=/usr
	ninja -C build
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	DESTDIR="$pkgdir" ninja -C build install
	ln -sv com.github.johnfactotum.Foliate "$pkgdir/usr/bin/foliate"
}
