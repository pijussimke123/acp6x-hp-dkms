# Original maintainer: FT <worldoptimizer@gmail.com>
# Fork: Pijus <microbios75@gmail.com>
pkgname=acp6x-hp-dkms
pkgver=1.0
pkgrel=2
pkgdesc="Patched AMD Audio Driver for HP 255R G10"
arch=('x86_64')
url="https://github.com/pijussimke123/acp6x-hp-dkms"
license=('GPL')
depends=('dkms')
conflicts=('acp6x-hp-dkms-git')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('7afc8803bef4c532fdf47aca3195e980d132834ade085a30530e5d518e423817')

package() {
    cd "${pkgname}-${pkgver}"

    # 1. Install Source Code for DKMS
    install -d "${pkgdir}/usr/src/acp6x-hp-${pkgver}"
    cp -t "${pkgdir}/usr/src/acp6x-hp-${pkgver}/" \
        dkms.conf Makefile pci-acp6x.c acp6x-mach.c acp6x.h acp6x_chip_offset_byte.h

    # 2. Install Blacklist Configuration
    install -d "${pkgdir}/etc/modprobe.d"
    install -m 644 blacklist-acp6x-hp.conf "${pkgdir}/etc/modprobe.d/blacklist-acp6x-hp.conf"

    # 3. Install License
    install -d "${pkgdir}/usr/share/licenses/${pkgname}"
    install -m 644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
