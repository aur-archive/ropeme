pkgname=ropeme

pkgver=1.0
pkgrel=1
pkgdesc="ROPEME - ROP Exploit Made Easy"
arch=('any')
url="http://www.vnsecurity.net/2010/08/ropeme-rop-exploit-made-easy/"
license=('GPL')
depends=(python2 'distorm')
source=(http://gexor.net/public/$pkgname-v$pkgver.tar.gz)
md5sums=('a57965ef00cb7d3ec8a557dcb526a994')

build(){
  cd "$srcdir/$pkgname-v$pkgver"
  python2 setup.py build
}

package() {
  cd "$srcdir/$pkgname-v$pkgver"
  python2 setup.py install --prefix=$pkgdir/usr

  # create symlink to /usr/bin
  install -dm755 "$pkgdir/usr/bin/"
  chmod +x "$pkgdir/usr/lib/python2.7/site-packages/ropeme/ropshell.py"
  ln -sf /usr/lib/python2.7/site-packages/${pkgname}/ropshell.py "$pkgdir/usr/bin/ropshell"

}
