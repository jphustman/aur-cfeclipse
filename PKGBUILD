# Maintainer: Jeremey Hustman <jeremeyhustman at gmail daught com>

_name="cfeclipse"
_gitname="cfeclipse"
pkgname="$_name"
pkgver=20140515.2248
pkgrel=1
pkgdesc="ColdFusion plugin for eclipse IDE - git branch"
arch=('any')
url="http://$_name.org"
license=("MIT")
depends=('eclipse')
makedepends=('git')
provides=("$_name")
conflicts=("$_name")
source=("${pkgname}::git+https://github.com/$_gitname/${_gitname}.git#branch=develop")
md5sums=('SKIP')

pkgver() {
	cd "$_gitname"
	echo "$(git log -1 --format="%cd" --date=short | sed 's|-||g').$(git rev-list --count master)"
	# Git, tags available
	# git describe --long | sed 's/.........$//;s/-/./g'
}

package() {
	cd "${srcdir}/${pkgname}"
	local dest="${pkgdir}/usr/share/eclipse/dropins/cfeclipse/eclipse/plugins"
	install -d "${dest}"
}
