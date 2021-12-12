# Maintainer: NeedleNardleNoo (conrad@conradhaupt.co.za)
pkgname=systemd-charging-threshold
pkgver=1.1
pkgrel=3
pkgdesc="Systemd service that manages laptop charging threshold stored in /sys."
arch=('i686' 'x86_64' 'arm' 'armv7h' 'armv6h' 'aarch64')
# url="https://github.com/Jguer/yay"
license=('MIT')
depends=(
    'systemd'
    'linux>=5.4'
    'git'
)
source=("charging-threshold"
        "charging-threshold.path"
        "charging-threshold.service")
sha256sums=('6442bc26a7c562f5afe6467dab36365c709909f6a81afcecfc0c25cff0f1bab0'
        'be8264ea5186ae8d2fbe63ded04a35c0161fb3a707e7064241d8bc9196b0a980'
        '6fbfe5a6fbfceafe5a13fc84aecf0b8326b6d595f414c124d60eb373abca6e4d')

package() {
    install -v -D -m644 "${srcdir}/charging-threshold.service" "${pkgdir}/etc/systemd/system/charging-threshold.service"
    install -v -D -m644 "${srcdir}/charging-threshold.path" "${pkgdir}/etc/systemd/system/charging-threshold.path"
    install -v -D -m644 "${srcdir}/charging-threshold" "${pkgdir}/etc/charging-threshold"
    mkdir -p "${pkgdir}/usr/lib/systemd/system/multi-user.target.wants/"
    ln -s "${pkgdir}/etc/systemd/system/charging-threshold.path" "${pkgdir}/usr/lib/systemd/system/multi-user.target.wants/charging-threshold.path"
}