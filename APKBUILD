# Contributor: NiLuJe <niluje@unknown.nowhere>
# Maintainer: NiLuJe <niluje@unknown.nowhere>
pkgname=kobo-fbink
pkgver=1.25.528
pkgrel=1
pkgdesc="FrameBuffer eInker for Kobo"
url="https://github.com/NiLuJe/FBInk.git"
arch="armhf"
license="GPL3+"
makedepends="linux-headers"
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

cleanup () {
	cd $startdir
	if [ -e "/home/${USER}/packages/${USER}/armhf/$pkgname-$pkgver-r$pkgrel.apk" ]; then
		cp "/home/${USER}/packages/${USER}/armhf/$pkgname-$pkgver-r$pkgrel.apk" .
	fi
}

sha512sums="
02ac41a111048f1d0aac3612c1e15b35858c0c46044efa617b31743ffec227880a5724902b415c2aeaf31548f37869dba18cdb92b638c229ee110469f8c41f88  fbink
5b13badb89a590febfe096c5eeace9650d9e5904423311150215ac79f02b0981f6867aff25fd4d9796565b3a825b0230395b6cf535fad67ae474c698cf489db5  libfbink.so.1.0.0
5b13badb89a590febfe096c5eeace9650d9e5904423311150215ac79f02b0981f6867aff25fd4d9796565b3a825b0230395b6cf535fad67ae474c698cf489db5  libfbink.so.1
5b13badb89a590febfe096c5eeace9650d9e5904423311150215ac79f02b0981f6867aff25fd4d9796565b3a825b0230395b6cf535fad67ae474c698cf489db5  libfbink.so
0dce6a74b7cf9a0365e1f5b5d7297163c88ef7e498c5fbed0ef19b14ff4a5f3b6e35accf2b89d6f68501ca5ee3d810350f7a643045b4962261e39461a6187f4b  fbink.h
"
