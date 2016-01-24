# `swcript`

`swcript` is a simple way to turn a Swift Cocoa app directory into a script.

To use it, just run:

    $ swcript ~/src/MyApp ~/Desktop/MyApp.swift

to combine all the files in `~/src/MyApp` into one script in `~/Desktop/`. Note that the resulting script does not have to end in `.swift` - `swcript` will automatically add the `#!` syntax to direct the shell to the `swift` binary.

There is a minify option (`-m` or `--minify`). It doesn't work great yet - your mileage may vary.

It has a few requirements for apps:

 - The app must have no external dependencies (NIBs, assets, `.plist` files, etc.)
 - The app must not have any Objective-C components (bridging headers or separate components written in Objective-C) and must be 100% Swift
 - The app must not have line-comments using `//`. This is a bug in `swcript`

Once `swcript` has processed your app, make sure to edit the file again. `swcript` defines a function `run()` that you;ll need to run to make sure to launch your app. A great place for this is at the end of the script.

See `license.md` for the license.
