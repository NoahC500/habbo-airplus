# Maintainer: NoahC500
pkgname=habbo-airplus
pkgver=r226.3ce6a9d
pkgrel=1
pkgdesc="Enhanced version of Habbo AIR Client"
arch=('x86_64')
url="https://github.com/LilithRainbows/HabboAirPlus"
license=('UNKNOWN')
source=(
	"https://github.com/LilithRainbows/HabboAirPlus/releases/download/latest/HabboAirPlus_Linux_x64.zip"
	"git+https://github.com/LilithRainbows/HabboAirPlus.git"
	"habbo-airplus.desktop"
)
sha256sums=("SKIP" "SKIP" "SKIP")

pkgver() {
	cd "$srcdir/HabboAirPlus"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package() {
	cd "$srcdir/HabboAirPlus_Linux_x64"
	mkdir -p "$pkgdir/usr/bin/habbo-airplus/"
	chmod 0755 "./Habbo"
	cp ./* "$pkgdir/usr/bin/habbo-airplus" -r

	cd ../
	mkdir -p "$pkgdir/usr/share/applications/"
	install -m 0755 "./habbo-airplus.desktop" "$pkgdir/usr/share/applications/"
}
