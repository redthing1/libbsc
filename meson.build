project('bsc', ['c', 'cpp'],
  version : '0.1',
  default_options : [
    'warning_level=3',
    'cpp_std=c++17'
  ],
)

# depend on libbsc
libbsc_proj = subproject('libbsc')
libbsc_dep = libbsc_proj.get_variable('libbsc_dep')

bsc_sources = [
  'bsc.cpp'
]

bsc_link_args = [
  '-static',
  '-static-libstdc++',
]

# on macos/darwin, don't static link
if target_machine.system() == 'darwin'
  bsc_link_args = []
endif

bsc_exe_name = 'bsc' + '_' + target_machine.system() + '_' + target_machine.cpu()

bsc_exe = executable(
  bsc_exe_name,
  bsc_sources,
  dependencies : [libbsc_dep],
  link_args: bsc_link_args,
)
