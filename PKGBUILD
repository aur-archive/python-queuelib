# Maintainer: PyroDevil <p dot devil at gmail dot com>
pkgbase="python-queuelib"
pkgname=("python2-queuelib" "python-queuelib")
pkgver=1.2.2
pkgrel=3
pkgdesc="Collection of persistent (disk-based) queues."
arch=(any)
license=('BSD')
url="http://scrapy.org"
makedepends=('git')
optdepends=()
provides=()
conflicts=()
options=(!emptydirs)
source=("git+https://github.com/scrapy/queuelib.git#tag=v${pkgver}")
md5sums=('SKIP')

function _package {
  cd "${srcdir}/queuelib"
  "$1" setup.py install --root="${pkgdir}"
  
  # copying license information
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  # copying readme information
  install -D -m644 "README.rst" "${pkgdir}/usr/share/doc/${pkgname}/README.rst"
}

function package_python2-queuelib {
  depends=(python2 python2-setuptools)
  _package "python2"
}

function package_python-queuelib {
  depends=(python python-setuptools)
  _package "python3"
}
