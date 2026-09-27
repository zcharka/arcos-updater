# Maintainer: Petexy <https://github.com/Petexy>

pkgname=arcos-updater
pkgver=1.0.0
pkgrel=1
pkgdesc='An updater for Arch-based distros. One button updates system packages and Flatpaks at once'
url='https://github.com/zcharka'
arch=('x86_64')
license=('GPL-3.0')
depends=(
  'python-gobject'
  'gtk4'
  'libadwaita'
  'arc-center'
  'wget'
)
install="${pkgname}.install"

package() {
    cd "${srcdir}"

    find usr -type f | while IFS= read -r _file; do
        case "${_file}" in
            usr/bin/*)
                install -Dm755 "${_file}" "${pkgdir}/${_file}"
                ;;
            usr/share/icons/archlinux-logo-text.svg)
                install -Dm644 "${_file}" "${pkgdir}/usr/share/pixmaps/archlinux-logo-text-postinstall.svg"
                ;;
            usr/share/icons/archlinux-logo-text-dark.svg)
                install -Dm644 "${_file}" "${pkgdir}/usr/share/pixmaps/archlinux-logo-text-postinstall.svg"
                ;;
            *)
                install -Dm644 "${_file}" "${pkgdir}/${_file}"
                ;;
        esac
    done
}
