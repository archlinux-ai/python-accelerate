# Maintainer: Daniel Bershatsky <bepshatsky@yandex.ru>
pkgname=python-accelerate
_pkgname=${pkgname#python-}
pkgver=0.20.3
pkgrel=1
pkgdesc='A simple way to train and use PyTorch models with multi-GPU, TPU, mixed-precision'
arch=('any')
url='https://github.com/hugginface/accelerate'
license=('Apache')
groups=('hugginface')
depends=(
    'python-numpy'
    'python-psutil'
    'python-pytorch'
    'python-yaml'
)
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
optdepends=()
source=("$_pkgname-$pkgver.tar.gz::https://github.com/huggingface/$_pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('2bbdf8c5fe6e6fb73c895d1a53f05bcd65d37b0271bc1af62c4b0eeeafea209e')

build() {
    cd $_pkgname-$pkgver
    python -m build -n -w
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir $pkgdir \
        $_pkgname-$pkgver/dist/$_pkgname-$pkgver-py3-*-*.whl
}
