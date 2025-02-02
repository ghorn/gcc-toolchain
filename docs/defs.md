<!-- Generated with Stardoc: http://skydoc.bazel.build -->

This module provides the definitions for registering a GCC toolchain for C and C++.


<a id="gcc_toolchain"></a>

## gcc_toolchain

<pre>
gcc_toolchain(<a href="#gcc_toolchain-name">name</a>, <a href="#gcc_toolchain-binary_prefix">binary_prefix</a>, <a href="#gcc_toolchain-builtin_sysroot_path">builtin_sysroot_path</a>, <a href="#gcc_toolchain-extra_cflags">extra_cflags</a>, <a href="#gcc_toolchain-extra_cxxflags">extra_cxxflags</a>,
              <a href="#gcc_toolchain-extra_ldflags">extra_ldflags</a>, <a href="#gcc_toolchain-hardcode_sysroot_ld_linux">hardcode_sysroot_ld_linux</a>, <a href="#gcc_toolchain-hardcode_sysroot_rpath">hardcode_sysroot_rpath</a>, <a href="#gcc_toolchain-platform_directory">platform_directory</a>,
              <a href="#gcc_toolchain-repo_mapping">repo_mapping</a>, <a href="#gcc_toolchain-sha256">sha256</a>, <a href="#gcc_toolchain-strip_prefix">strip_prefix</a>, <a href="#gcc_toolchain-target_arch">target_arch</a>, <a href="#gcc_toolchain-url">url</a>, <a href="#gcc_toolchain-use_builtin_sysroot">use_builtin_sysroot</a>)
</pre>



**ATTRIBUTES**


| Name  | Description | Type | Mandatory | Default |
| :------------- | :------------- | :------------- | :------------- | :------------- |
| <a id="gcc_toolchain-name"></a>name |  A unique name for this repository.   | <a href="https://bazel.build/docs/build-ref.html#name">Name</a> | required |  |
| <a id="gcc_toolchain-binary_prefix"></a>binary_prefix |  An explicit prefix used by each binary in bin/. Defaults to <code>&lt;target_arch&gt;</code>.   | String | optional | "" |
| <a id="gcc_toolchain-builtin_sysroot_path"></a>builtin_sysroot_path |  An explicit sysroot path inside the tarball. Defaults to <code>&lt;platform_directory&gt;/sysroot</code>.   | String | optional | "" |
| <a id="gcc_toolchain-extra_cflags"></a>extra_cflags |  Extra flags for compiling C. {sysroot} is rendered to the sysroot path.   | List of strings | optional | [] |
| <a id="gcc_toolchain-extra_cxxflags"></a>extra_cxxflags |  Extra flags for compiling C++. {sysroot} is rendered to the sysroot path.   | List of strings | optional | [] |
| <a id="gcc_toolchain-extra_ldflags"></a>extra_ldflags |  Extra flags for linking. {sysroot} is rendered to the sysroot path.   | List of strings | optional | [] |
| <a id="gcc_toolchain-hardcode_sysroot_ld_linux"></a>hardcode_sysroot_ld_linux |  Whether the sysroot ld-linux.so should be hardcoded into the ELF binaries or not. This is useful when running tests so that the host ld-linux.so is overridden.   | Boolean | optional | False |
| <a id="gcc_toolchain-hardcode_sysroot_rpath"></a>hardcode_sysroot_rpath |  Whether the sysroot search paths should be hardcoded into the ELF binaries or not. This is useful when running tests so that libraries are searched on the sysroot first.   | Boolean | optional | False |
| <a id="gcc_toolchain-platform_directory"></a>platform_directory |  An explicit directory containing the target platform extra directories. Defaults to <code>&lt;target_arch&gt;-buildroot-linux-gnu</code>.   | String | optional | "" |
| <a id="gcc_toolchain-repo_mapping"></a>repo_mapping |  A dictionary from local repository name to global repository name. This allows controls over workspace dependency resolution for dependencies of this repository.&lt;p&gt;For example, an entry <code>"@foo": "@bar"</code> declares that, for any time this repository depends on <code>@foo</code> (such as a dependency on <code>@foo//some:target</code>, it should actually resolve that dependency within globally-declared <code>@bar</code> (<code>@bar//some:target</code>).   | <a href="https://bazel.build/docs/skylark/lib/dict.html">Dictionary: String -> String</a> | required |  |
| <a id="gcc_toolchain-sha256"></a>sha256 |  The SHA256 integrity hash for the interpreter tarball.   | String | required |  |
| <a id="gcc_toolchain-strip_prefix"></a>strip_prefix |  The prefix to strip from the extracted tarball.   | String | required |  |
| <a id="gcc_toolchain-target_arch"></a>target_arch |  The target architecture this toolchain produces. E.g. x86_64.   | String | required |  |
| <a id="gcc_toolchain-url"></a>url |  The URL of the interpreter tarball.   | String | required |  |
| <a id="gcc_toolchain-use_builtin_sysroot"></a>use_builtin_sysroot |  Whether the builtin sysroot is used or not.   | Boolean | optional | True |


<a id="gcc_register_toolchain"></a>

## gcc_register_toolchain

<pre>
gcc_register_toolchain(<a href="#gcc_register_toolchain-name">name</a>, <a href="#gcc_register_toolchain-kwargs">kwargs</a>)
</pre>

Declares a `gcc_toolchain` and calls `register_toolchain` for it.

**PARAMETERS**


| Name  | Description | Default Value |
| :------------- | :------------- | :------------- |
| <a id="gcc_register_toolchain-name"></a>name |  The name passed to <code>gcc_toolchain</code>.   |  none |
| <a id="gcc_register_toolchain-kwargs"></a>kwargs |  The extra arguments passed to <code>gcc_toolchain</code>. See <code>gcc_toolchain</code> for more info.   |  none |


