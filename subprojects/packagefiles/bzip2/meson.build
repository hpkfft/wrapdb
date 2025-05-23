project(
  'bzip2',
  'c',
  version: '1.0.8',
  meson_version: '>=1.0.0',
)

libbz2_lib = static_library(
  'bz2',
  'blocksort.c',
  'huffman.c',
  'crctable.c',
  'randtable.c',
  'compress.c',
  'decompress.c',
  'bzlib.c',
  pic: true,
  install: true,
)

bzip2_exe = executable(
  'bzip2',
  'bzip2.c',
  link_with: libbz2_lib,
)

if meson.can_run_host_binaries()
  python = find_program(
    'python3',
    native: true,
    version: ['>=3.5', '<4'],
  )
  _testargs = [files('test.py')]
  test(
    'compress sample1',
    python,
    args: [
      _testargs,
      files('sample1.ref'),
      files('sample1.bz2'),
      '--',
      bzip2_exe,
      '-1',
    ],
  )
  test(
    'compress sample2',
    python,
    args: [
      _testargs,
      files('sample2.ref'),
      files('sample2.bz2'),
      '--',
      bzip2_exe,
      '-2',
    ],
  )
  test(
    'compress sample3',
    python,
    args: [
      _testargs,
      files('sample3.ref'),
      files('sample3.bz2'),
      '--',
      bzip2_exe,
      '-3',
    ],
  )
  test(
    'decompress sample1',
    python,
    args: [
      _testargs,
      files('sample1.bz2'),
      files('sample1.ref'),
      '--',
      bzip2_exe,
      '-d',
    ],
  )
  test(
    'decompress sample2',
    python,
    args: [
      _testargs,
      files('sample2.bz2'),
      files('sample2.ref'),
      '--',
      bzip2_exe,
      '-d',
    ],
  )
  test(
    'decompress sample3',
    python,
    args: [
      _testargs,
      files('sample3.bz2'),
      files('sample3.ref'),
      '--',
      bzip2_exe,
      '-ds',
    ],
  )
endif

install_headers('bzlib.h')

bzip2_dep = declare_dependency(
  link_with: libbz2_lib,
  include_directories: include_directories('.'),
)
meson.override_dependency('bzip2', bzip2_dep)
