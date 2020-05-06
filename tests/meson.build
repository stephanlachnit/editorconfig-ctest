# test PEP 8 conformance
flake8 = find_program(
  'flake8',
  required : false,
)
if flake8.found()
  test(
    'test PEP 8 conformance',
    flake8,
    args : ['--ignore=E501', exe_file],
  )
endif

# test editorconfig conformance
editorconfig_ctest = find_program(
  'editorconfig-ctest',
  exe_file,
  required : false,
)
if editorconfig_ctest.found()
  test(
    'test editorconfig conformance',
    editorconfig_ctest,
    args : ['--dir', meson.source_root()],
  )
endif

# test editorconfig-ctest
if editorconfig_ctest.found()
  test(
    'trim trailing whitespace true test',
    editorconfig_ctest,
    args : ['--file', files('trim_trailing_whitespace_true_test')]
  )
  test(
    'trim trailing whitespace false test',
    editorconfig_ctest,
    args : ['--file', files('trim_trailing_whitespace_false_test')]
  )
  test(
    'insert final newline true test',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_true_test')]
  )
  test(
    'insert final newline false test',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_false_test')]
  )
endif
