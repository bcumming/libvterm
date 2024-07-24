project('libvterm', 'c',
  version: '0.3.3',
  default_options: ['c_std=c99', 'warning_level=1'])

# Source files
sources = files(
  'src/encoding.c',
  'src/keyboard.c',
  'src/mouse.c',
  'src/parser.c',
  'src/pen.c',
  'src/screen.c',
  'src/state.c',
  'src/unicode.c',
  'src/vterm.c',
)

headers = files(
  'include/vterm.h',
  'include/vterm_keycodes.h',
)
install_headers(headers)

libvterm = library(
  'vterm',
  sources,
  include_directories: include_directories('include'),
  install: true,
  version: '0.3.3' # Version info
)

unterm = executable(
  'unterm',
  'bin/unterm.c',
  link_with: libvterm,
  install: true
)

vterm_ctrl = executable(
  'vterm-ctrl',
  'bin/vterm-ctrl.c',
  link_with: libvterm,
  install: true
)

vterm_dump = executable(
  'vterm-dump',
  'bin/vterm-dump.c',
  link_with: libvterm,
  install: true
)

pkgconfig = import('pkgconfig')
pkgconfig.generate(libvterm)
