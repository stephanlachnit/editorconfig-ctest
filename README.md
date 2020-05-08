# editorconfig-ctest
## conformance test for editorconfig
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/stephanlachnit/editorconfig-ctest.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/stephanlachnit/editorconfig-ctest/context:python)

editorconfig-ctest checks all files in the current working directory on conformance of the editorconfig. It is designed to be used in test suites and integrated into CI workflows. It exits with 0 if all files are conform, and with 1 if one or more files don't conform.

This tool is inspired by [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker) and [eclint](https://github.com/jedmao/eclint), but written in a single Python file. This has several advantages when it comes to distributing this tool, which is the main reason why I started this project. editorconfig-ctest only depends on the [editorconfig-python-core](https://github.com/editorconfig/editorconfig-core-py), and uses [Meson](https://mesonbuild.com/) for installation for testing integration (which is optional).

To ensure that everything is working as expected and no regressions will be made, I'm working on a fully featured test suite, meaning that every feature will be tested in both a normal test, and a test that is designed to fail.

## Properties

Currently the following [editorconfig properties](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties) are supported:
* `charset`, currently only `utf-8` is confirmed, but theoretically all charsets supported by Python should work
* `end_of_line`, currently only `lr` is confirmed, but theoretically all of them should work
* `trim_trailing_whitespace`, partial testing integration, but can currently fail if there is no final newline
* `insert_final_newline`, partial testing integration
* `indent_style`, currently only `space` confirmed, `tab` should work in most cases but can theoretically fail or give false positives (fix requires `block_comment`)
* `tab_width`, is used for `max_line_length`
* `max_line_length`, can currently fail if there is no final newline

Planned but not supported yet:
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
* Fail tests in test suite
