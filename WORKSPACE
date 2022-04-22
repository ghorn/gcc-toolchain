workspace(name = "bazel_gcc_toolchain")

load("//toolchain:repositories.bzl", "gcc_toolchain_dependencies")

gcc_toolchain_dependencies()

load("//:internal.bzl", "internal_dependencies")

internal_dependencies()

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

load("@aspect_bazel_lib//lib:repositories.bzl", "aspect_bazel_lib_dependencies")

aspect_bazel_lib_dependencies()

load("//toolchain:defs.bzl", "gcc_register_toolchain")

flags = [
    "-Wall",
    "-Wextra",
    "-Werror",
    "-fdiagnostics-color=always",
]

gcc_register_toolchain(
    name = "gcc_toolchain",
    url = "https://toolchains.bootlin.com/downloads/releases/toolchains/x86-64/tarballs/x86-64--glibc--stable-2021.11-5.tar.bz2",
    sha256 = "6fe812add925493ea0841365f1fb7ca17fd9224bab61a731063f7f12f3a621b0",
    strip_prefix = "x86-64--glibc--stable-2021.11-5",
    target_arch = "x86_64",
    hardcode_sysroot_ld_linux = True,
    hardcode_sysroot_rpath = True,
    extra_cflags = flags,
    extra_cxxflags = flags,
)

gcc_register_toolchain(
    name = "gcc_toolchain_aarch64",
    url = "https://toolchains.bootlin.com/downloads/releases/toolchains/aarch64/tarballs/aarch64--glibc--stable-2021.11-1.tar.bz2",
    sha256 = "dec070196608124fa14c3f192364c5b5b057d7f34651ad58ebb8fc87959c97f7",
    strip_prefix = "aarch64--glibc--stable-2021.11-1",
    target_arch = "aarch64",
    extra_cflags = flags,
    extra_cxxflags = flags,
)

gcc_register_toolchain(
    name = "gcc_toolchain_armv7",
    url = "https://toolchains.bootlin.com/downloads/releases/toolchains/armv7-eabihf/tarballs/armv7-eabihf--glibc--stable-2021.11-1.tar.bz2",
    sha256 = "6d10f356811429f1bddc23a174932c35127ab6c6f3b738b768f0c29c3bf92f10",
    strip_prefix = "armv7-eabihf--glibc--stable-2021.11-1",
    target_arch = "armv7",
    binary_prefix = "arm",
    platform_directory = "arm-buildroot-linux-gnueabihf",
    extra_cflags = flags,
    extra_cxxflags = flags,
)
