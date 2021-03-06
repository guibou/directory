Changelog for the [`directory`][1] package
==========================================

## 1.2.4.0 (September 2015)

  * Work around lack of `#const_str` when cross-compiling
    ([haskell-cafe](F7D))

  * Add `findExecutablesInDirectories`
    ([#33](https://github.com/haskell/directory/pull/33))

  * Add `exeExtension`

[F7D]: https://mail.haskell.org/pipermail/haskell-cafe/2015-August/120892.html

## 1.2.3.1 (August 2015)

  * Restore support for Safe Haskell with base < 4.8
    ([#30](https://github.com/haskell/directory/issues/30))

## 1.2.3.0 (July 2015)

  * Add support for XDG Base Directory Specification
    ([#6](https://github.com/haskell/directory/issues/6))

  * Implement `setModificationTime` counterpart to `getModificationTime`
    ([#13](https://github.com/haskell/directory/issues/13))

  * Implement `getAccessTime` and `setAccessTime`

  * Fix `canonicalizePath` so that it always returns a reasonable result even
    if the path is inaccessible and will not throw exceptions unless the
    current directory cannot be obtained
    ([#23](https://github.com/haskell/directory/issues/23))

  * Corrected the trailing slash behavior of `makeAbsolute`
    so that `makeAbsolute "" == makeAbsolute "."`

  * Deprecate use of `HsDirectory.h` and `HsDirectoryConfig.h`

  * Implement `withCurrentDirectory`

## 1.2.2.1 (Apr 2015)

  * Fix dependency problem on NixOS when building with tests
    ([#24](https://github.com/haskell/directory/issues/24))

## 1.2.2.0 (Mar 2015)

  * Bundled with GHC 7.10.1

  * Make `getModificationTime` support sub-second resolution on Windows

  * Fix silent failure in `createDirectoryIfMissing`

  * Replace `throw` by better defined `throwIO`s

  * Avoid stack overflow in `getDirectoryContents`
    ([#17](https://github.com/haskell/directory/pull/17))

  * Expose `findExecutables`
    ([#14](https://github.com/haskell/directory/issues/14))

  * `removeDirectoryRecursive` no longer follows symlinks under any
    circumstances
    ([#15](https://github.com/haskell/directory/issues/15))

  * Allow trailing path separators in `getPermissions` on Windows
    ([#9](https://github.com/haskell/directory/issues/9))

  * `renameFile` now always throws the correct error type
    (`InappropriateType`) when the destination is a directory, as long as the
    filesystem is not being modified concurrently
    ([#8](https://github.com/haskell/directory/pull/8))

  * Add `makeAbsolute`, which should be preferred over `canonicalizePath`
    unless one requires symbolic links to be resolved

## 1.2.1.0 (Mar 2014)

  * Bundled with GHC 7.8.1

  * Add support for sub-second precision in `getModificationTime` when
    linked against `unix>=2.6.0.0`

  * Fix `createDirectoryIfMissing _ "."` in `C:\` on Windows

  * Remove support for NHC98 compiler

  * Update package to `cabal-version >= 1.10` format

  * Enhance Haddock documentation for `doesDirectoryExist` and
    `canonicalizePath`

  * Fix `findExecutable` to check that file permissions indicate executable

  * New convenience functions `findFiles` and `findFilesWith`

[1]: https://hackage.haskell.org/package/directory
