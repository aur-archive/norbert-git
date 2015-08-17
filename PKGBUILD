# Maintainer: Buce <dmbuce@gmail.com>

pkgname=norbert-git
pkgver=20130304
pkgrel=1
pkgdesc="A command line NBT editor."
arch=(any)
url="https://github.com/DMBuce/norbert"
license=('GPL2')
groups=()
depends=(python)
makedepends=('git')
provides=(norbert)
conflicts=(norbert)
replaces=(norbert)
backup=()
options=()
install=
source=()
noextract=()
md5sums=()

_gitroot='git://github.com/DMBuce/norbert.git'
_gitname='norbert'

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting build..."

  rm -rf "$srcdir/$_gitname-build"
  git clone "$srcdir/$_gitname" "$srcdir/$_gitname-build"
  cd "$srcdir/$_gitname-build"

  #
  # BUILD HERE
  #
}

package() {
  cd "$srcdir/$_gitname-build"
  install -D -m755 norbert.py "$pkgdir/usr/bin/norbert"
  #install -D -m755 vinbt "$pkgdir/usr/bin/vinbt"
}

# vim:set ts=2 sw=2 et:
