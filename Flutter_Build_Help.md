# Flutter Build Command and Their Respected Paths

----
`flutter build web --release`
> build\web

 `flutter build web --profile`
 > build\web



 ```bash
  flutter build web -h
Build a web application bundle.

Global options:
-h, --help                  Print this usage information.
-v, --verbose               Noisy logging, including all shell commands executed.
                            If used with "--help", shows hidden options. If used with "flutter doctor", shows additional
                            diagnostic information. (Use "-vv" to force verbose logging in those cases.)
-d, --device-id             Target device id or name (prefixes allowed).
    --version               Reports the version of this tool.
    --enable-analytics      Enable telemetry reporting each time a flutter or dart command runs.
    --disable-analytics     Disable telemetry reporting each time a flutter or dart command runs, until it is
                            re-enabled.
    --suppress-analytics    Suppress analytics reporting for the current CLI invocation.

Usage: flutter build web [arguments]
-h, --help                                                   Print this usage information.
    --[no-]tree-shake-icons                                  Tree shake icon fonts so that only glyphs used by the
                                                             application remain.
                                                             (defaults to on)
-t, --target=<path>                                          The main entry-point file of the application, as run on the
                                                             device.
                                                             If the "--target" option is omitted, but a file name is
                                                             provided on the command line, then that is used instead.
                                                             (defaults to "lib\main.dart")
-o, --output                                                 The absolute path to the directory where the repository is
                                                             generated. By default, this is
                                                             <current-directory>/build/<target-platform>.
                                                             Currently supported for subcommands: aar, web.
    --[no-]pub                                               Whether to run "flutter pub get" before executing this
                                                             command.
                                                             (defaults to on)
    --build-number                                           An identifier used as an internal version number.
                                                             Each build must have a unique identifier to differentiate
                                                             it from previous builds.
                                                             It is used to determine whether one build is more recent
                                                             than another, with higher numbers indicating more recent
                                                             build.
                                                             On Android it is used as "versionCode".
                                                             On Xcode builds it is used as "CFBundleVersion".
                                                             On Windows it is used as the build suffix for the product
                                                             and file versions.
    --build-name=<x.y.z>                                     A "x.y.z" string used as the version number shown to users.
                                                             For each new version of your app, you will provide a
                                                             version number to differentiate it from previous versions.
                                                             On Android it is used as "versionName".
                                                             On Xcode builds it is used as "CFBundleShortVersionString".
                                                             On Windows it is used as the major, minor, and patch parts
                                                             of the product and file versions.
    --profile                                                Build a version of your app specialized for performance
                                                             profiling.
    --release                                                Build a release version of your app (default mode).
    --dart-define=<foo=bar>                                  Additional key-value pairs that will be available as
                                                             constants from the String.fromEnvironment,
                                                             bool.fromEnvironment, and int.fromEnvironment constructors.
                                                             Multiple defines can be passed by repeating "--dart-define"
                                                             multiple times.
    --dart-define-from-file=<use-define-config.json|.env>    The path of a .json or .env file containing key-value pairs
                                                             that will be available as environment variables.
                                                             These can be accessed using the String.fromEnvironment,
                                                             bool.fromEnvironment, and int.fromEnvironment constructors.
                                                             Multiple defines can be passed by repeating
                                                             "--dart-define-from-file" multiple times.
                                                             Entries from "--dart-define" with identical keys take
                                                             precedence over entries from these files.
    --[no-]native-null-assertions                            Enables additional runtime null checks in web applications
                                                             to ensure the correct nullability of native (such as in
                                                             dart:html) and external (such as with JS interop) types.
                                                             This is enabled by default but only takes effect in sound
                                                             mode. To report an issue with a null assertion failure in
                                                             dart:html or the other dart web libraries, please file a
                                                             bug at:
                                                             https://github.com/dart-lang/sdk/issues/labels/web-librarie
                                                             s
                                                             (defaults to on)

Flutter web options
    --base-href                                              Overrides the href attribute of the <base> tag in
                                                             web/index.html. No change is done to web/index.html file if
                                                             this flag is not provided. The value has to start and end
                                                             with a slash "/". For more information:
                                                             https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b
                                                             ase
    --pwa-strategy                                           The caching strategy to be used by the PWA service worker.

          [none]                                             Generate a service worker with no body. This is useful for
                                                             local testing or in cases where the service worker caching
                                                             functionality is not desirable
          [offline-first] (default)                          Attempt to cache the application shell eagerly and then
                                                             lazily cache all subsequent assets as they are loaded. When
                                                             making a network request for an asset, the offline cache
                                                             will be preferred.

    --web-renderer                                           The renderer implementation to use when building for the
                                                             web.

          [auto] (default)                                   Use the HTML renderer on mobile devices, and CanvasKit on
                                                             desktop devices.
          [canvaskit]                                        Always use the CanvasKit renderer. This renderer uses WebGL
                                                             and WebAssembly to render graphics.
          [html]                                             Always use the HTML renderer. This renderer uses a
                                                             combination of HTML, CSS, SVG, 2D Canvas, and WebGL.
          [skwasm]                                           Always use the experimental skwasm renderer.

    --[no-]web-resources-cdn                                 Use Web static resources hosted on a CDN.
                                                             (defaults to on)

JavaScript compilation options
    --csp                                                    Disable dynamic generation of code in the generated output.
                                                             This is necessary to satisfy CSP restrictions (see
                                                             http://www.w3.org/TR/CSP/).
    --[no-]source-maps                                       Generate a sourcemap file. These can be used by browsers to
                                                             view and debug the original source code of a compiled and
                                                             minified Dart application.
    --dart2js-optimization                                   Sets the optimization level used for Dart compilation to
                                                             JavaScript. Valid values range from O1 to O4.
                                                             [O1, O2, O3, O4 (default)]
    --dump-info                                              Passes "--dump-info" to the Javascript compiler which
                                                             generates information about the generated code is a
                                                             .js.info.json file.
    --no-frequency-based-minification                        Disables the frequency based minifier. Useful for comparing
                                                             the output between builds.

```
----

