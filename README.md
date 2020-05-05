# editorconfig-ctest
conformance test for editorconfig

editorconfig-ctest checks all files in the current working directory on conformance of the editorconfig. It is designed to be used in test suites and integrated into CI workflows. It exits with 0 if there all files are conform, and with 1 if one file doesn't conform.

This tool is inspired by [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker), but written in Python instead of Go. This has several advantages when it comes to distributing this tool, which is the main reason for this project. editorconfig-ctest only depends on the [editorconfig-python-core](https://github.com/editorconfig/editorconfig-core-py), and uses [Meson](https://mesonbuild.com/) for installation for testing integration.
