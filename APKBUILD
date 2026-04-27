# Contributor: NiLuJe <niluje@unknown.nowhere>
# Maintainer:  NiLuJe <niluje@unknown.nowhere>
pkgname=kobo-fbink
pkgver=1.25.528
pkgrel=0
pkgdesc="FrameBuffer eInker for Kobo"
url="https://github.com/NiLuJe/FBInk.git"
arch="armhf"
license="GPL3+"
depends=
provides="$pkgname-dev=$pkgver"
source="
	FBInk/Release/fbink
	FBInk/Release/libfbink.so.1.0.0
	FBInk/Release/libfbink.so.1
	FBInk/Release/libfbink.so
	FBInk/fbink.h
"
options="!check"

prepare () {
	cd "$startdir/FBInk"
	make shared KOBO=1
}

package () {
	mkdir -p "$pkgdir/usr/bin"
	mkdir -p "$pkgdir/usr/lib"
	mkdir -p "$pkgdir/usr/include"

	cp "$startdir/FBInk/Release/fbink" "$pkgdir/usr/bin/fbink"
	cp "$startdir/FBInk/Release/libfbink.so.1.0.0" "$pkgdir/usr/lib/libfbink.so.1.0.0"
	cp -P "$startdir/FBInk/Release/libfbink.so.1" "$pkgdir/usr/lib/libfbink.so.1"
	cp -P "$startdir/FBInk/Release/libfbink.so" "$pkgdir/usr/lib/libfbink.so"
	cp "$startdir/FBInk/fbink.h" "$pkgdir/usr/include/fbink.h"
}

sha512sums="4d4644b2c9ec42344439b51041267999e49623e7da526aa6d1c31ff7ae98a23462d4aaa6a0f7d63c8223f5f0f52216fa119e2839cd20278967b3be65d6882edd  fbink
10112af127f9d674358f4ceec88217e1f0cbaad5f0ee57c59d8f3c453b4b661c0f84f882fb933e9efa8876740f37561acd46a33d07c4b1550bf5c31b2bf85314  libfbink.so.1.0.0
10112af127f9d674358f4ceec88217e1f0cbaad5f0ee57c59d8f3c453b4b661c0f84f882fb933e9efa8876740f37561acd46a33d07c4b1550bf5c31b2bf85314  libfbink.so.1
10112af127f9d674358f4ceec88217e1f0cbaad5f0ee57c59d8f3c453b4b661c0f84f882fb933e9efa8876740f37561acd46a33d07c4b1550bf5c31b2bf85314  libfbink.so
0dce6a74b7cf9a0365e1f5b5d7297163c88ef7e498c5fbed0ef19b14ff4a5f3b6e35accf2b89d6f68501ca5ee3d810350f7a643045b4962261e39461a6187f4b  fbink.h"
