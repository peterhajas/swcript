# `swcript`

`swcript` is a simple way to turn a Swift Cocoa app directory into a script.

To use it, just run:

    $ swcript ~/src/MyApp ~/Desktop/MyApp.swift

to combine all the files in `~/src/MyApp` into one script in `~/Desktop/`. Note that the resulting script does not have to end in `.swift` - `swcript` will automatically add the `#!` syntax to direct the shell to the `swift` binary.

There is a minify option (`-m` or `--minify`). It doesn't work yet.

It has a few assumptions:

 - The app must have no external dependencies (NIBs, assets, `.plist` files, etc.)
 - The app must not have any Objective-C components (bridging headers or separate components written in Objective-C) and must be 100% Swift

See `license.md` for the license.
