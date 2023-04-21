# Maintainer: Gregory Land
# Contributor: Fabian Bornschein <fabiscafe-cat-mailbox-dog-com>

pkgname=supergfxctl
pkgver=5.1.0
subpkg=RC5
pkgrel=2
pkgdesc="A utility for Linux graphics switching on Intel/AMD iGPU + nVidia dGPU laptops"
arch=('x86_64')
url="https://gitlab.com/asus-linux/supergfxctl"
license=('MPL2')
depends=('gcc-libs' 'systemd')
makedepends=('rust')
provides=('supergfxctl')
conflicts=('supergfxctl-git'
           'optimus-manager')
source=("https://gitlab.com/asus-linux/supergfxctl/-/archive/$pkgver-$subpkg/supergfxctl-$pkgver-$subpkg.tar.gz")
sha512sums=('4ddad0b913c311be435f61d90ad3968c671de3a874cbb271a71f58f0a54d9ea37447d535cb6f1aca84a7a761e4869dfb3a1a6f4e4840062dbc48be5c67837e48')
_gitdir=${pkgname%"-git"}

build() {
	cd "$pkgname-$pkgver-$subpkg"
	make build
}

package() {
	cd "$pkgname-$pkgver-$subpkg"
	make DESTDIR="$pkgdir-$subpkg" install
}

