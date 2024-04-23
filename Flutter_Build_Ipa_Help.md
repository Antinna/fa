```bash
Run flutter build ipa -h
Build an iOS archive bundle and IPA for distribution (macOS host only).
Global options:
-h, --help                  Print this usage information.
-v, --verbose               Noisy logging, including all shell commands executed.
                            If used with "--help", shows hidden options. If used with "flutter doctor", shows additional diagnostic information. (Use "-vv" to force verbose logging in those cases.)
-d, --device-id             Target device id or name (prefixes allowed).
    --version               Reports the version of this tool.
    --enable-analytics      Enable telemetry reporting each time a flutter or dart command runs.
    --disable-analytics     Disable telemetry reporting each time a flutter or dart command runs, until it is re-enabled.
    --suppress-analytics    Suppress analytics reporting for the current CLI invocation.
Usage: flutter build ipa [arguments]
-h, --help                                                   Print this usage information.
    --[no-]tree-shake-icons                                  Tree shake icon fonts so that only glyphs used by the application remain.
                                                             (defaults to on)
    --split-debug-info=<v1.2.3/>                             In a release build, this flag reduces application size by storing Dart program symbols in a separate file on the host rather than in the application. The value of the flag should be a directory where program symbol files can be stored for later use. These symbol files contain the information needed to symbolize Dart stack traces. For an app built with this flag, the "flutter symbolize" command with the right program symbol file is required to obtain a human readable stack trace.
                                                             This flag cannot be combined with "--analyze-size".
    --debug                                                  Build a debug version of your app.
    --profile                                                Build a version of your app specialized for performance profiling.
    --release                                                Build a release version of your app (default mode).
-t, --target=<path>                                          The main entry-point file of the application, as run on the device.
                                                             If the "--target" option is omitted, but a file name is provided on the command line, then that is used instead.
                                                             (defaults to "lib/main.dart")
    --flavor                                                 Build a custom app flavor as defined by platform-specific build setup.
                                                             Supports the use of product flavors in Android Gradle scripts, and the use of custom Xcode schemes.
    --[no-]pub                                               Whether to run "flutter pub get" before executing this command.
                                                             (defaults to on)
    --build-number                                           An identifier used as an internal version number.
                                                             Each build must have a unique identifier to differentiate it from previous builds.
                                                             It is used to determine whether one build is more recent than another, with higher numbers indicating more recent build.
                                                             On Android it is used as "versionCode".
                                                             On Xcode builds it is used as "CFBundleVersion".
                                                             On Windows it is used as the build suffix for the product and file versions.
    --build-name=<x.y.z>                                     A "x.y.z" string used as the version number shown to users.
                                                             For each new version of your app, you will provide a version number to differentiate it from previous versions.
                                                             On Android it is used as "versionName".
                                                             On Xcode builds it is used as "CFBundleShortVersionString".
                                                             On Windows it is used as the major, minor, and patch parts of the product and file versions.
    --[no-]obfuscate                                         In a release build, this flag removes identifiers and replaces them with randomized values for the purposes of source code obfuscation. This flag must always be combined with "--split-debug-info" option, the mapping between the values and the original identifiers is stored in the symbol map created in the specified directory. For an app built with this flag, the "flutter symbolize" command with the right program symbol file is required to obtain a human readable stack trace.
                                                             
                                                             Because all identifiers are renamed, methods like Object.runtimeType, Type.toString, Enum.toString, Stacktrace.toString, Symbol.toString (for constant symbols or those generated by runtime system) will return obfuscated results. Any code or tests that rely on exact names will break.
    --dart-define=<foo=bar>                                  Additional key-value pairs that will be available as constants from the String.fromEnvironment, bool.fromEnvironment, and int.fromEnvironment constructors.
                                                             Multiple defines can be passed by repeating "--dart-define" multiple times.
    --dart-define-from-file=<use-define-config.json|.env>    The path of a .json or .env file containing key-value pairs that will be available as environment variables.
                                                             These can be accessed using the String.fromEnvironment, bool.fromEnvironment, and int.fromEnvironment constructors.
                                                             Multiple defines can be passed by repeating "--dart-define-from-file" multiple times.
                                                             Entries from "--dart-define" with identical keys take precedence over entries from these files.
    --[no-]analyze-size                                      Whether to produce additional profile information for artifact output size. This flag is only supported on "--release" builds. When building for Android, a single ABI must be specified at a time with the "--target-platform" flag. When building for iOS, only the symbols from the arm64 architecture are used to analyze code size.
                                                             By default, the intermediate output files will be placed in a transient directory in the build directory. This can be overridden with the "--code-size-directory" option.
                                                             This flag cannot be combined with "--split-debug-info".
    --code-size-directory                                    The location to write code size analysis files. If this is not specified, files are written to a temporary directory under the build directory.
    --[no-]codesign                                          Codesign the application bundle (only available on device builds).
                                                             (defaults to on)
    --export-method                                          Specify how the IPA will be distributed.
          [ad-hoc]                                           Test on designated devices that do not need to be registered with the Apple developer account. Requires a distribution certificate.
          [app-store] (default)                              Upload to the App Store.
          [development]                                      Test only on development devices registered with the Apple developer account.
          [enterprise]                                       Distribute an app registered with the Apple Developer Enterprise Program.
    --export-options-plist=<ExportOptions.plist>             Export an IPA with these options. See "xcodebuild -h" for available exportOptionsPlist keys.
Run "flutter help" to see global options.
```
