# This is the entry point for --crosstool_top.  Toolchains are found
# by lopping off the name of --crosstool_top and searching for
# 'cc-compiler-${CPU}' in this BUILD file, where CPU is the target CPU
# specified in --cpu.
#
# This file group should include
#   * all cc_toolchain targets supported
#   * all file groups that said cc_toolchain might refer to,
# including the default_grte_top setting in the CROSSTOOL
# protobuf.

package(default_visibility = ["//visibility:public"])


filegroup(
  name = 'toolchain',
  srcs = [
    ':cc-compiler-armeabi-v7a',
    '@linaro_linux_gcc_repo//:compiler_components',
    ':linaro_linux_all_files',
  ],
)

filegroup(
  name = 'linaro_linux_all_files',
  srcs = [
    '//tools/arm_compiler/linaro_linux_gcc:clang-symlinks',
    '//tools/arm_compiler/linaro_linux_gcc:tool-wrappers',
    '@linaro_linux_gcc_repo//:compiler_pieces',
  ],
)

filegroup(
  name = 'linaro_linux_linker_files',
  srcs = [
    '//tools/arm_compiler/linaro_linux_gcc:gcc',
    '//tools/arm_compiler/linaro_linux_gcc:ld',
    '//tools/arm_compiler/linaro_linux_gcc:ar',
    '//tools/arm_compiler/linaro_linux_gcc:clang-ld',
    '//tools/arm_compiler/linaro_linux_gcc:clang',
    '@linaro_linux_gcc_repo//:compiler_pieces',
  ],
)

filegroup(
  name = 'linaro_linux_compiler_files',
  srcs = [
    '//tools/arm_compiler/linaro_linux_gcc:gcc',
    '//tools/arm_compiler/linaro_linux_gcc:ld',
    '//tools/arm_compiler/linaro_linux_gcc:clang',
    '//tools/arm_compiler/linaro_linux_gcc:as',
  ],
)

cc_toolchain(
  name = 'cc-compiler-armeabi-v7a',
  all_files = ':linaro_linux_all_files',
  compiler_files = ':linaro_linux_compiler_files',
  cpu = 'armeabi-v7a',
  dwp_files = ':empty',
  dynamic_runtime_libs = [':empty'],
  linker_files = ':linaro_linux_linker_files',
  objcopy_files = '//tools/arm_compiler/linaro_linux_gcc:objcopy',
  static_runtime_libs = [':empty'],
  strip_files = '//tools/arm_compiler/linaro_linux_gcc:strip',
  supports_param_files = 1,
)



cc_toolchain(
    name = "cc-compiler-local",
    all_files = ":empty",
    compiler_files = ":empty",
    cpu = "local",
    dwp_files = ":empty",
    dynamic_runtime_libs = [":empty"],
    linker_files = ":empty",
    objcopy_files = ":empty",
    static_runtime_libs = [":empty"],
    strip_files = ":empty",
    supports_param_files = 1,
)