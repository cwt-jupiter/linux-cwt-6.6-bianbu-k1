# Maintainer: Chaiwat Suttipongsakul <cwt@bashell.com>

pkgbase=linux-cwt-6.6-bianbu-k1
_variant=cwt
pkgver=2.1
epoch=6 #Based on cwt image version
pkgrel=1
_tag=k1-bl-v${pkgver}-release
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
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.63-64.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.64-65.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.65-66.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.66-67.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.67-68.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.68-69.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.69-70.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.70-71.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.71-72.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.72-73.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.73-74.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.74-75.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.75-76.xz'
  'https://cdn.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.6.76-77.xz'
  'config'
  'linux.preset'
  '90-linux.hook')

b2sums=('8bddab145eec572e98bfc6f9fc608a40da9d8591b0708a2bed979cbe64ccd02d53220eeb9d92d724631fe11013f4ddbc45f87c106f2d9a90e85fe69183d217dd'
        '68e98b2f1c26f188eb00f9b2fd9a99ce8652997447245ce54cd9fa7a6a83321b6af05d0f95758966adbe0ece2ba8acbb54b2f76ebff41fb89db1059455df0263'
        'd263dd25901c7fc67047053d912d05e5e01f25c79affd60bd86bc3864063d705b474a3a4b293e0588001e0fa0d654ef3f107ff65680794463268518591e560a7'
        'cc5b4df2bd64da09df05b9fe369fa65e5b181dc2c96e277b80a6ab3a95531564e4b6ee7a91c38df3cfdc525931b7046be4060fe1c2d05f75d07c36788478f773'
        'fbac780711077fcf254ca6f46903ff5c958b0fd119130f3660b53283791a7a9e40060077cfe1a9a0436f1e649e61159e0352afe44a43c9d6b17c262a80e8738f'
        '5aa7ed4a8f289fe844f53f1178c0147749ab4a7471010291f4aa75cfdd7ce1361487f56d08c6f7612bda57a7a90fcd9516c4bccc79d831c0ef92e401ff5f4bab'
        '1363c98dc5ab59e87dc6c713cca4fbee5588f80e87544dfe2e6f916fcfd6c71706553f6de0be762154a3e92230d8671940fed941e031e03c867b86d2236318dc'
        '4b005211271cf3c2c1ca640ee0305d468c22300afdb1deeef1afe8678b3f0d536855a9336e260f55f7e4b4da70e83309496b227c837e5f0263e663231c5f6e49'
        '128eb85c748b04002936ebf47e02a3bca53706493739e6369727abe216c90949e1127af35f05d9216547685e1e5f59d70a116951790b046e50e6ec21cb996474'
        '2815d71964ee11b7f84b8d7280ea0d408c6e9b507670c23a3ea906a423754aa350e4ae3501123bdfd25e34d664c25829015e731c0e480700e5a6de4cb2be1442'
        '9f5fd93610caf92f6e39e34cec79782648645aeada191723d63ae5c97f5dd97f28af1b672f097a126338b79c39c861ec7e1a731edd88bea3cbd458bb09466dae'
        'b4196fb0e864cce22cbd1e2e5da3675d0e9f70a63c5f773e9dfa95052efbba77a1fc10dbb28dc27b5c88f98336d4604db7580f9ba33892011e2a663f8afd7bff'
        'c56245c69a361c082b07e74a2cc1d86590d2b2b058a5a670279cfe54f1689bef2c6fa9b3ff6d2128fc573fa0a4bbf143db37216f81a19b08c11003a70254c0ee'
        '41d7640ccbee16bf5a6b05fc465372a34f41d8f98add3ba74a217455bb1f5c14819a7f83655c91be54e3b161dbc646f55d9c13ca764bf686d8add66c4fa4db37'
        'be2307f42a9fd0a36b86d2cb0b9cf3f7520954479b7db7d4287bf41bf34811f7e140b6a74ce49fe355e72d7401e07d052d3362dab418c0f0d787c0decdf8a992'
        '195dde44b44b153741c7d8d115924bf3cb96ed22d84f46c018c24000bf8ad6e6b8895715fd0f4e789db58a7795a5bfdad23230755b7e9b3207adcfbb62bcc37c'
        '891484c39a68cb393e97655805a300c4a4680ee0ca63ed369e8c4ac67f22c717924deed96a69cdd7b07199aa57ca6ab8bbfdd214e107ceac42649475ef7af6d3'
        '3e869f7cb0a813bd5155f75fd20b68638654bdf3cad70c67603d9ac3f39171a69bfa1baa9703989d931f68f39d3721784dab2c5c3a67b50d0074df2239e03fd9'
        '665bc1e1a3d38c8bcf1c6e67a9a312ef6c148e2a7135bc6b50e340b289a922903b857ebfcbeea9b7904bc386c57a7413428bf4de8f8716ad4f6c62c4dc2a5128'
        'ec011f2f5402070f7140c764bee3fe8ccb999d5099faeca2f80fed9feb7ec5a8551dc57cbdd0f2aaf7a6516c879e2af32126a523b9ba66b70b2a67bcd8122075'
        '3352363e263150f090850b7334a7c94c225ecc11b7d447246ab42c07cc591346fca355e477016db27148f407a3d812f258c983fd513e67ee69b8deda9d060c1a')

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
  echo "-v${pkgver}" >localversion.20-pkgver
  echo "-${pkgrel}" >localversion.30-pkgrel

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
