#!/bin/bash

# Based on the original packaging by Matthew Gamble <git@matthewgamble.net>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [ToDo]: Use variables for easier updating
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/colorpicker-keshavbhatt/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/colorpicker-keshavbhatt/discussions>

pkgname=colorpicker-keshavbhatt
pkgver=1.0.3
pkgrel=1
pkgdesc="A powerful screen ColorPicker/Chooser application for Linux Desktop"
arch=(
  "x86_64"
)
url="https://github.com/keshavbhatt/ColorPicker"
license=(
  "MIT"
)
depends=(
  "hicolor-icon-theme"
  "qt5-base"
)
conflicts=(
  "colorpicker"
  "color-picker"
)
source=(
  "${pkgname}-${pkgver}::https://github.com/keshavbhatt/ColorPicker/archive/refs/tags/1.0.3.tar.gz"
)
sha512sums=(
  "3bd200aba8dca9f53d6b2a65befec399d937e790c472b03f7dd57e4a366a1abf0f27f0792765f87052864cc0f5d416908de44a098e360b45dd8c2d651084fbbf"
)

build() {

  cd "ColorPicker-${pkgver}"

  mkdir build
  cd build

  qmake ../src
  make
}

package() {

  cd "ColorPicker-${pkgver}"

  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/colorpicker-keshavbhatt/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/colorpicker-keshavbhatt/README.md"

  cd build
  make INSTALL_ROOT="${pkgdir}" install
}
