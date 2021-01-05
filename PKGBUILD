pkgname=apcups-hibernate
pkgver=1
pkgrel=1
pkgdesc="APC UPS Hibernation Controls"
arch=("any")

source=("hibernate" "ups-kill")
noextract=("hibernate" "ups-kill")
md5sums=('SKIP' 'SKIP')

depends=("apcupsd" "systemd")

license=('custom')

package() {
	install -d -m755 "${pkgdir}/usr/bin/"
	install -m755 "${srcdir}/hibernate" "${pkgdir}/usr/bin/hibernate"


	install -d -m755 "${pkgdir}/etc/apcupsd/"
	ln -s "/usr/bin/hibernate" "${pkgdir}/etc/apcupsd/doshutdown"

	install -d -m755 "${pkgdir}/usr/lib/systemd/system-sleep/"
	install -m755 "${srcdir}/ups-kill" "${pkgdir}/usr/lib/systemd/system-sleep/ups-kill"

}
