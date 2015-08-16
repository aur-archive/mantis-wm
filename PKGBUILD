# Contributor: thorsten w. <p@thorsten-wissmann.de>
pkgname=mantis-wm
pkgver=20120603
pkgrel=1
pkgdesc="Lightweight window manager for X"
arch=('i686' 'x86_64')
url="http://github.com/andreas-volker/mantis-wm"
license=('MIT')
depends=( libx11 )
makedepends=( git )
provides=( )
backup=( )
source=( )
md5sums=( )
_gitroot="git://github.com/andreas-volker/mantis-wm.git"
_gitname="mantis-wm"

build() {
  cd $srcdir
  echo "Fetching source from GIT"
  if ! [ -d "$_gitname" ] ; then
    # if git dir does not exist yet
    # then clone git repo
    git clone "$_gitroot" || return 1
    cd "$_gitname"
  else
    # else pull sources
    cd "$_gitname" && git pull origin || return 1
  fi
  # compile
  make VERSION_SUFFIX="-git" || return 1
  make VERSION_SUFFIX="-git" \
       PREFIX=$pkgdir/usr \
       ETCDIR=$pkgdir/etc install || return 1
}

