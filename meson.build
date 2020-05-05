project(
  'editorconfig-ctest',
  license : 'BSD-2-Clause',
  version : '0',
)

# folder configuration
bindir = get_option('bindir')
bin_file = files('editorconfig-ctest')

# install binary
install_data(
  bin_file,
  install_dir : bindir,
)

# test PEP 8 conformance
flake8 = find_program(
  'flake8',
  required : false,
)
if flake8.found()
  test(
    'test PEP 8 conformance',
    flake8,
  )
endif

# test editorconfig conformance
editorconfig_ctest = find_program(
  'editorconfig-ctest',
  required : false,
)
if editorconfig_ctest.found()
  test(
    'test editorconfig conformance',
    editorconfig_ctest,
    args : [bin_file],
    workdir : meson.source_root(),  # todo: add cmdline option to specify the workdir
  )
endif
