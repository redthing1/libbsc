project('libbsc', ['c', 'cpp'],
  version : '0.1',
  default_options : [
    'warning_level=3',
    'cpp_std=c++17'
  ],
)

# link libstdc++ statically
libbsc_lflags = [
  '-static-libstdc++',
]

libbsc_sources = [
  'libbsc/adler32/adler32.cpp',
  'libbsc/bwt/libsais/libsais.c',
  'libbsc/coder/coder.cpp',
  'libbsc/coder/qlfc/qlfc.cpp',
  'libbsc/coder/qlfc/qlfc_model.cpp',
  'libbsc/filters/detectors.cpp',
  'libbsc/filters/preprocessing.cpp',
  'libbsc/libbsc/libbsc.cpp',
  'libbsc/lzp/lzp.cpp',
  'libbsc/platform/platform.cpp',
  'libbsc/st/st.cpp',
  'libbsc/bwt/bwt.cpp',
]
libbsc_include = include_directories('.')

libbsc_stlib = static_library('libbsc',
  libbsc_sources,
  include_directories: libbsc_include,
  c_args: ['-DBUILDING_libbsc'],
  gnu_symbol_visibility: 'default',
  link_args: libbsc_lflags,
)

# make this library usable as a meson subproject.
libbsc_dep = declare_dependency(
  include_directories: libbsc_include,
  link_with : libbsc_stlib,
)

libbsc_m03_include = include_directories('./libbsc_m03')

libbsc_m03_sources = [
  # hutucker/hu-tucker.c libsais/libsais.c libsais/libsais16.c
  'libbsc_m03/hutucker/hu-tucker.c',
  'libbsc_m03/libsais/libsais.c',
  'libbsc_m03/libsais/libsais16.c',
]

libbsc_m03_stlib = static_library('libbsc_m03',
  libbsc_m03_sources,
  include_directories: libbsc_m03_include,
  c_args: ['-DBUILDING_libbsc_m03'],
  gnu_symbol_visibility: 'default',
  link_args: libbsc_lflags,
)

libbsc_m03_dep = declare_dependency(
  include_directories: libbsc_m03_include,
  link_with : libbsc_m03_stlib,
)
