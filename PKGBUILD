# Maintainer: Chaiwat Suttipongsakul <cwt@bashell.com>

pkgbase=linux-cwt-6.6-bianbu-k1
_variant=cwt
pkgver=2.0.2
epoch=5 #Based on cwt image version
pkgrel=2
_tag=v${pkgver}
_desc='Linux 6.6.x (-cwt) for SpacemiT K1/M1 RISC-V Board'
_srcname=linux-6.6-$_tag
url="https://gitee.com/bianbu-linux/linux-6.6"
arch=(riscv64)
license=('GPL2')
makedepends=(bc libelf pahole cpio perl tar xz gcc)
options=('!strip')
source=("${_srcname}.tar.gz::${url}/repository/archive/${_tag}.tar.gz"
  'linux-01-enable_pxa_pwm_on_spacemit.patch'
  'linux-02-add_DMA_BUF_ns_import_to_amvx.patch'
  'linux-03-set_40_and_55_degree_C_trips_to_active.patch'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.36-37.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.37-38.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.38-39.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.39-40.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.40-41.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.41-42.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.42-43.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.43-44.xz'
  'config'
  'linux.preset'
  '90-linux.hook')

b2sums=('b58787917ae05970b91e40510bf160fd67bc062a87ee781247db4a2d8b4f6e52b7574373e50b52dc7156b99a615a316803720a0890ebd54a2604f7158e267f7e'
        '68e98b2f1c26f188eb00f9b2fd9a99ce8652997447245ce54cd9fa7a6a83321b6af05d0f95758966adbe0ece2ba8acbb54b2f76ebff41fb89db1059455df0263'
        'd263dd25901c7fc67047053d912d05e5e01f25c79affd60bd86bc3864063d705b474a3a4b293e0588001e0fa0d654ef3f107ff65680794463268518591e560a7'
        'cc5b4df2bd64da09df05b9fe369fa65e5b181dc2c96e277b80a6ab3a95531564e4b6ee7a91c38df3cfdc525931b7046be4060fe1c2d05f75d07c36788478f773'
        '9ead007697740845ec078eca08185253e09fa814d5d604bb8ea4e3513a648ce9426d52df9a1dda2b1579ad695103defac8b6d1817372121b34fe935843b74551'
        'acc675cadd969d7673fa291ed24f1f89ac795444b3a037887f5c4dad701e3098f620306b7cfe611271e70f6058623b92b88f43042c33936e5b555c0319d345f5'
        '48988d33bfa157efd1efdcd5bc5f5493b0e07a67e6635e8d7b6cd9f2720746280354eff5235d631a39528225fae204848866e4fffd2c5d807c4b89eba031e759'
        '63b09ab4e02374417efaa75c3981286a23864f4f68f82fe96b4e147a90b2e3b031acee2813bb4b772b4a8de7d6e0a7ff0dc6c40b924f3715a7d78ef1cb71bfd5'
        'a11fb16f90a5fce6e8ec902c56ae274d3fbe32003805c2b4f2a8838f70446bc911ef0522fedf06210e69565f62a54c56010fb15817a4ed99fd979124a51cac4d'
        'bb1576008debbb53ac9eae2f8947039eebde4c217ed63cb6177159104293b02a4571768cbf463af91dd7ad48365626c2cfdea77dcf904e40baff31a2180ce038'
        'b148688413b5d140b534e14e6310ba3aea79e42c07bd0ff040317f0e0f7f74c049e85763b875d1c58699681f727b54b928daa5f9e1f6292a54133660c2c73209'
        '7b9fd25bf45b7d9915fcb0eecfd0f5a60273ad62914ace2f3c41c34f7d6401e50ba9d212763970c17ae430805a116dd33d22d7e829b297bc58b401e73aa2f5a4'
        'ca1ea3c3554d8c1b6cf407158c83d92bbe7f661ef9252e3c9f38599569a808a3fbb9381fa6780680c4e73f8fcb93ca4bb62613b27264636cdb247f0819f5561f'
        '7519034f4562335cfc3f6d7c527a284e1250a38ea4101ad4189c8071e7f03606a626878456732ee8577b52deefa67b0300341b13735d98b6743e60eedd2c1490'
        'aff8d0e66c9b4f38be425867d7e5f295044aeff0cfb5481c26595d57e5d390853953256671099261ecba4657fa2d040940015c0361feed030b4d4c9a1035e0f4')

prepare() {
  cd $_srcname

  local src
  for src in $(ls ../linux-*.patch); do
    echo "Applying patch $src..."
    patch -Np1 < "../$src"
  done

  for src in $(ls ../patch-*.xz); do
    echo "Applying patch $src..."
    xzcat "../$src" | patch -Np1 -F3
  done

  echo "Setting version..."
  echo "-${_variant}${epoch}" >localversion.10-variant
  echo "-${_tag}" >localversion.20-pkgver
  echo "-$pkgrel" >localversion.30-pkgrel

  echo "Setting config..."
  cp ../config .config

  unset CFLAGS
  CCACHE=$(which ccache 2>/dev/null)
  if [ "$CCACHE" != "" ]; then
    gcc="${CCACHE} gcc"
  else
    gcc="gcc"
  fi

  make -j $(nproc) ARCH=riscv CC="${CROSS_COMPILE:-}${gcc}" olddefconfig
  cp .config ../../config.new

  make -j $(nproc) ARCH=riscv CC="${CROSS_COMPILE:-}${gcc}" -s kernelrelease >version
  echo "Prepared $pkgbase version $(<version)"
}

build() {
  cd $_srcname
  unset CFLAGS
  CCACHE=$(which ccache 2>/dev/null)
  if [ "$CCACHE" != "" ]; then
    gcc="${CCACHE} gcc"
  else
    gcc="gcc"
  fi
  make -j $(nproc) ARCH=riscv CC="${CROSS_COMPILE:-}${gcc}" all
}

_package() {
  pkgdesc="The $_desc kernel and modules"
  depends=(coreutils kmod mkinitcpio)
  optdepends=('wireless-regdb: to set the correct wireless channels of your country'
    'linux-firmware: firmware images needed for some devices')
  provides=("linux=${pkgver}" "WIREGUARD-MODULE")
  conflicts=('linux')

  cd $_srcname
  local kernver="$(<version)"
  local modulesdir="$pkgdir/usr/lib/modules/$kernver"

  echo "Installing boot image..."
  install -Dm644 "arch/riscv/boot/Image.gz.itb" "$modulesdir/vmlinuz"
  install -Dm644 "arch/riscv/boot/Image.gz.itb" "$pkgdir/boot/vmlinuz"

  echo "Installing modules..."
  make -j $(nproc) ARCH=riscv INSTALL_MOD_PATH="$pkgdir/usr" INSTALL_MOD_STRIP=1 modules_install

  echo "Installing dtbs..."
  make -j $(nproc) ARCH=riscv INSTALL_DTBS_PATH="$pkgdir/usr/share/dtbs/$kernver" dtbs_install
  make -j $(nproc) ARCH=riscv INSTALL_DTBS_PATH="$pkgdir/boot/dtbs/" dtbs_install

  # remove build links
  rm "$modulesdir"/build

  install -Dm644 ../linux.preset "${pkgdir}/etc/mkinitcpio.d/linux.preset"
  install -Dm644 ../90-linux.hook "${pkgdir}/usr/share/libalpm/hooks/90-linux.hook"
}

_package-headers() {
  pkgdesc="Headers and scripts for building modules for the $_desc kernel"
  depends=(pahole)
  provides=("linux-headers=${pkgver}")
  conflicts=('linux-headers')

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing build files..."
  install -Dt "$builddir" -m644 .config Makefile Module.symvers System.map version
  install -Dt "$builddir/kernel" -m644 kernel/Makefile
  install -Dt "$builddir/arch/riscv" -m644 arch/riscv/Makefile
  cp -t "$builddir" -a scripts

  # required when DEBUG_INFO_BTF_MODULES is enabled
  cp --parents -r -t "$builddir/" tools/bpf/resolve_btfids

  echo "Installing VDSO files..."
  cp -a --parents -r -t "$builddir" arch/riscv/kernel/vdso/*
  cp -a --parents -r -t "$builddir" lib/vdso/*
  chmod -R g+w "$builddir/arch/riscv/kernel/vdso"

  echo "Installing certificate files..."
  install -Dt "$builddir/certs" -m640 certs/*.pem
  install -Dt "$builddir/certs" -m640 certs/*.x509

  echo "Installing headers..."
  cp -t "$builddir" -a include
  chmod -R g+w "$builddir/include/generated"
  cp -t "$builddir/arch/riscv" -a arch/riscv/include
  install -Dt "$builddir/arch/riscv/kernel" -m644 arch/riscv/kernel/asm-offsets.s

  install -Dt "$builddir/drivers/md" -m644 drivers/md/*.h
  install -Dt "$builddir/net/mac80211" -m644 net/mac80211/*.h

  # https://bugs.archlinux.org/task/13146
  install -Dt "$builddir/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # https://bugs.archlinux.org/task/20402
  install -Dt "$builddir/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "$builddir/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "$builddir/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  # https://bugs.archlinux.org/task/71392
  install -Dt "$builddir/drivers/iio/common/hid-sensors" -m644 drivers/iio/common/hid-sensors/*.h

  echo "Installing KConfig files..."
  find . -name 'Kconfig*' -exec install -Dm644 {} "$builddir/{}" \;

  echo "Removing unneeded architectures..."
  local arch
  for arch in "$builddir"/arch/*/; do
    [[ $arch = */riscv/ ]] && continue
    echo "Removing $(basename "$arch")"
    rm -r "$arch"
  done

  echo "Installing RAS from x86..."
  install -Dt "$builddir/arch/x86/ras"  -m644 arch/x86/ras/Kconfig

  echo "Removing documentation..."
  rm -r "$builddir/Documentation"

  echo "Removing broken symlinks..."
  find -L "$builddir" -type l -printf 'Removing %P\n' -delete

  echo "Removing loose objects..."
  find "$builddir" -type f -name '*.o' -printf 'Removing %P\n' -delete

  echo "Stripping build tools..."
  local file
  while read -rd '' file; do
    case "$(file -bi "$file")" in
    application/x-sharedlib\;*) # Libraries (.so)
      strip -v $STRIP_SHARED "$file" ;;
    application/x-archive\;*) # Libraries (.a)
      strip -v $STRIP_STATIC "$file" ;;
    application/x-executable\;*) # Binaries
      strip -v $STRIP_BINARIES "$file" ;;
    application/x-pie-executable\;*) # Relocatable binaries
      strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "$builddir" -type f -perm -u+x ! -name vmlinux -print0)

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/src"
  ln -sr "$builddir" "$pkgdir/usr/src/$pkgbase"
}

pkgname=("$pkgbase" "$pkgbase-headers")
for _p in "${pkgname[@]}"; do
  eval "package_$_p() {
    $(declare -f "_package${_p#$pkgbase}")
    _package${_p#$pkgbase}
  }"
done

# vim:set ts=8 sts=2 sw=2 et:
