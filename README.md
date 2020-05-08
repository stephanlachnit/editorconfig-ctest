# editorconfig-ctest
## conformance test for editorconfig
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/stephanlachnit/editorconfig-ctest.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/stephanlachnit/editorconfig-ctest/context:python)

editorconfig-ctest checks all files in the current working directory on conformance of the editorconfig. It is designed to be used in test suites and integrated into CI workflows. It exits with 0 if all files are conform, and with 1 if one or more files don't conform.

This tool is inspired by [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker) and [eclint](https://github.com/jedmao/eclint), but written in a single Python file. This has several advantages when it comes to distributing this tool, which is the main reason why I started this project. editorconfig-ctest only depends on the [editorconfig-python-core](https://github.com/editorconfig/editorconfig-core-py), and uses [Meson](https://mesonbuild.com/) for installation for testing integration (which is optional).

To ensure that everything is working as expected and no regressions will be made, I'm working on a fully featured test suite, meaning that every feature will be tested in both a normal test, and a test that is designed to fail.

## Properties

Currently the following [editorconfig properties](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties) are supported:
* `end_of_line` (full testing integration)
* `trim_trailing_whitespace` (full testing integration)
* `insert_final_newline` (full testing integration)
* `tab_width`, is used for `max_line_length` and will be for `indent_size`
* `max_line_length`

Planned but not fully supported yet:
* `charset`, currently only `utf-8` works
* `indent_style`, full testing integration, however `tab` can theoretically fail or give false positives (fix requires `block_comment`), it should work in most cases though
* `indent_size`
* `block_comment` with `block_comment_start`  and `block_comment_end`
* `quote_type`

## Features

Currently implemeted:
* Ignore file in a ingore file using regex syntax
* Automatically ignores non-readables files
* Man page and cmdline interface

Planned but not implemented yet:
* Ignore files in .gitignores
* Reverse ignores files
* Complete test suite with CI
* Github App
