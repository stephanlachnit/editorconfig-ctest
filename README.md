# editorconfig-ctest
conformance test for editorconfig<br />
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/stephanlachnit/editorconfig-ctest.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/stephanlachnit/editorconfig-ctest/context:python)

editorconfig-ctest checks all files in the current working directory on conformance of the editorconfig. It is designed to be used in test suites and integrated into CI workflows. It exits with 0 if there all files are conform, and with 1 if one file doesn't conform.

This tool is inspired by [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker) and [eclint](https://github.com/jedmao/eclint), but written in Python. This has several advantages when it comes to distributing this tool, which is the main reason for this project. editorconfig-ctest only depends on the [editorconfig-python-core](https://github.com/editorconfig/editorconfig-core-py), and uses [Meson](https://mesonbuild.com/) for installation for testing integration.
