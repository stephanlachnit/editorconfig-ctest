project(
  'editorconfig-ctest',
  license : 'BSD-2-Clause',
  version : '1',
)

# files
exe_file = files('editorconfig-ctest')
man_file = files('editorconfig-ctest.1')

# folders
bindir = get_option('bindir')
mandir = get_option('mandir')

# install executable
install_data(
  exe_file,
  install_dir : bindir,
)

# install man page
install_man(
  man_file,
  install_dir : mandir,
)

# tests
subdir('tests')
