# Maintainer: Florian Walch <florian+aur@fwalch.com>
# Contributor: Patrice Peterson <runiq at archlinux dot us>
# Contributor: lucc <l-m-h@web.de>
# Contributor: wenLiangcan <boxeed at gmail dot com>
# Contributor: astiam <astiamm at gmail dot com>

pkgbase=python-neovim
pkgname=(python2-neovim python-neovim)
pkgver=0.1.8
pkgrel=1
arch=('any')
license=('Apache')
url='https://github.com/neovim/python-client'
makedepends=('python2-setuptools' 'python-setuptools')
source=("$pkgname-$pkgver.tar.gz::https://github.com/neovim/python-client/archive/${pkgver}.tar.gz")
sha256sums=('d6cf0365e831c49cd428954a2b5c4dd00797e6b370ac84bfc0c5963b0695b86d')

build_python2-neovim() {
  cd "${srcdir}/python-client-${pkgver}"
  python2 setup.py build
}

package_python2-neovim() {
  pkgdesc='Adds support for Python 2 plugins to Neovim.'
  depends=('neovim' 'python2' 'python2-msgpack' 'python2-greenlet'
           'python2-trollius')
  optdepends=('python2-cairo: for experimental GUI (pynvim)'
              'python2-click: for experimental GUI (pynvim)'
              'python2-gobject: for experimental GUI (pynvim)')

  cd "${srcdir}/python-client-${pkgver}"
  python2 setup.py install --prefix=/usr --root="${pkgdir}"
}

build_python-neovim() {
  cd "${srcdir}/python-client-${pkgver}"
  python setup.py build
}

package_python-neovim() {
  pkgdesc='Adds support for Python 3 plugins to Neovim.'
  depends=('neovim' 'python' 'python-msgpack' 'python-greenlet')
  provides=("python3-neovim=${pkgver}")
  conflicts=('python3-neovim')

  cd "${srcdir}/python-client-${pkgver}"
  python setup.py install --prefix=/usr --root="${pkgdir}"
}

# vim:set sw=2 sts=2 et:
