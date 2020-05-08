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
    'charset utf-8 test',
    editorconfig_ctest,
    args : ['--file', files('charset_utf_8_test')],
  )
  test(
    'end of line lf test',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_lf_test')],
  )
  test(
    'end of line lf test (fail)',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_lf_test_fail')],
    should_fail : true,
  )
  test(
    'end of line cr test',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_cr_test')],
  )
  test(
    'end of line cr test (fail)',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_cr_test_fail')],
    should_fail : true,
  )
  test(
    'end of line crlf test',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_crlf_test')],
  )
  test(
    'end of line crlf test (fail)',
    editorconfig_ctest,
    args : ['--file', files('end_of_line_crlf_test_fail')],
    should_fail : true,
  )
  test(
    'trim trailing whitespace true test',
    editorconfig_ctest,
    args : ['--file', files('trim_trailing_whitespace_true_test')],
  )
  test(
    'trim trailing whitespace true test (fail)',
    editorconfig_ctest,
    args : ['--file', files('trim_trailing_whitespace_true_test_fail')],
    should_fail : true,
  )
  test(
    'trim trailing whitespace false test',
    editorconfig_ctest,
    args : ['--file', files('trim_trailing_whitespace_false_test')],
  )
  # fail test doesn't make sense for false
  test(
    'insert final newline true test',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_true_test')],
  )
  test(
    'insert final newline true test (fail)',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_true_test_fail')],
    should_fail : true,
  )
  test(
    'insert final newline false test',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_false_test')],
  )
  test(
    'insert final newline false test (fail)',
    editorconfig_ctest,
    args : ['--file', files('insert_final_newline_false_test_fail')],
    should_fail : true,
  )
  test(
    'indent style space test',
    editorconfig_ctest,
    args : ['--file', files('indent_style_space_test')],
  )
  test(
    'indent style space test (fail)',
    editorconfig_ctest,
    args : ['--file', files('indent_style_space_test_fail')],
    should_fail : true,
  )
  test(
    'indent style tab test',
    editorconfig_ctest,
    args : ['--file', files('indent_style_tab_test')],
  )
  test(
    'indent style tab test (fail)',
    editorconfig_ctest,
    args : ['--file', files('indent_style_tab_test_fail')],
    should_fail : true,
  )
  test(
    'max line length without tabs test',
    editorconfig_ctest,
    args : ['--file', files('max_line_length_wo_tabs_test')],
  )
  test(
    'max line length without tabs test (fail)',
    editorconfig_ctest,
    args : ['--file', files('max_line_length_wo_tabs_test_fail')],
    should_fail : true,
  )
endif
