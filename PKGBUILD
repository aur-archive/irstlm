# Maintainer: Filip Graliński <filipg@amu.edu.pl>
pkgname=irstlm
pkgver=5.80.03
pkgrel=8
pkgdesc='A tool for the estimation, representation, and computation of statistical language models'
arch=('i686' 'x86_64')
url='http://hlt.fbk.eu/en/irstlm'
license=('LGPL')
depends=('bash' 'perl')
makedepends=('automake>=1.10' 'autoconf>=2.59')
source=("http://downloads.sourceforge.net/project/irstlm/irstlm/$pkgname-5.80/$pkgname-$pkgver.tgz")
options=('staticlibs')
md5sums=('0e6c4359d77a75737c5ca439e8a801d4')

build(){
  cd "$srcdir/$pkgname-$pkgver"
  sed -i 's|AM_CONFIG_HEADER|AC_CONFIG_HEADERS|' configure.in
  sh regenerate-makefiles.sh
  ./configure --prefix=/opt/irstlm
  make
}

package(){
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
  chmod a+rx ${pkgdir}/opt/irstlm/bin/* ${pkgdir}/opt/irstlm/lib/*
}
