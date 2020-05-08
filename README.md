# editorconfig-ctest
## conformance test for editorconfig
[![Build Status](https://travis-ci.com/stephanlachnit/editorconfig-ctest.svg?branch=master)](https://travis-ci.com/stephanlachnit/editorconfig-ctest)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/stephanlachnit/editorconfig-ctest.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/stephanlachnit/editorconfig-ctest/context:python)

editorconfig-ctest checks all files in the current working directory on conformance of the editorconfig. It is designed to be used in test suites and integrated into CI workflows. It exits with 0 if all files are conform, and with 1 if one or more files don't conform.

This tool is inspired by [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker) and [eclint](https://github.com/jedmao/eclint), but written in a single Python file. This has several advantages when it comes to distributing this tool, which is the main reason why I started this project. editorconfig-ctest only depends on the editorconfig-python-core, and uses Meson for installation and testing integration (optional).

To ensure that everything is working as expected and no regressions will be made, I'm working on a fully featured test suite, meaning that every feature will be tested in both a normal test, and a test that is designed to fail if possible.

## Properties

Currently the following [editorconfig properties](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties) are supported:
* `end_of_line`
* `trim_trailing_whitespace`
* `insert_final_newline`
* `tab_width` (used for `max_line_length` and `indent_size`)
* `max_line_length`

Planned but not fully supported yet:
* `charset`, currently only `utf-8` works
* `indent_style`, partially supported, `tab` can theoretically fail or give false positives (fix requires `block_comment`), it should work in most cases though
* `indent_size`
* `block_comment`, `block_comment_start`  and `block_comment_end`
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

## Installation

editorconfig-ctest doesn't require any installation, just download the file and run it. Make sure to install the [editorconfig-python-core](https://github.com/editorconfig/editorconfig-core-py).
However, if you wish to install it on your system, you can do so using [Meson](https://mesonbuild.com/):
```sh
meson builddir
meson install -C builddir
```

## Usage

See `editorconfig-ctest --help` or `man editorconfig-ctest` (if installed):
```
SYNOPSIS
    editorconfig-ctest [-d DIR] [-f FILE] [--exit-zero] [--verbose]

OPTIONS
    -h, --help
            show this help message and exit

    -d DIR, --dir DIR
            test directory

    -f FILE, --file FILE
            test file

    --exit-zero
            always exit with status code zero

    --verbose
            show verbose output

    --version
            show program's version number and exit

BEHAVIOUR
    If no directory or file is specified the current working directory will be testd.  Multiple folder and file calls are allowed, but there is no check if a file has already been tested or not.  If a file is specified, it will be tested, even if it is inside an ignore file.
```

## Development

editorconfig-ctest is currently only developed and maintained by myself. The project is licensed under the BSD-2-Clause, the same license as the editorconfig-python-core. Feel free to help by packaging it for distros or providing PRs.
