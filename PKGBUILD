# Maintainer : Mathias Rav <m@git.strova.dk>

_pkgname="vim-compiledb-path"
pkgname="vim-compiledb-path-git"
_pkgver=0.0.1
pkgver=v0.0.1.g589fa99
pkgrel=1
pkgdesc='Add C++ include directories from compile_commands.json to Vim include path'
arch=(any)
url='https://github.com/martong/vim-compiledb-path'
license=(custom)
depends=(vim python2)
makedepends=(git)
conflicts=()
source=(git://github.com/martong/vim-compiledb-path
        patch)
md5sums=('SKIP'
         '296648abd2c85c23e23b36e4a9c67135')

pkgver() {
	cd $_pkgname
	echo -n v$_pkgver.g
	git rev-parse --short @
}

prepare() {
	cd ${srcdir}/$_pkgname
	patch -p1 <../nodebug.patch
}

package() {
	cd ${srcdir}/$_pkgname

	# creating directories
	install -d -m 755 ${pkgdir}/usr/share/vim/vimfiles/doc
	install -d -m 755 ${pkgdir}/usr/share/vim/vimfiles/plugin

	# copying files
	install -D -m 644 plugin/compiledb-path.vim ${pkgdir}/usr/share/vim/vimfiles/plugin
	install -D -m 644 doc/compiledb-path.txt ${pkgdir}/usr/share/vim/vimfiles/doc
}
