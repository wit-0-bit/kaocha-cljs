# Unreleased

## Added

## Fixed

## Changed

# 1.1.118 (2022-02-21 / 63a9ef4)

## Changed

- General version bumps, so we don't pull in old versions of ClojureScript or
  Glögi.

# 1.0.113 (2021-09-07 / 2680b20)

## Changed

- Bump ClojureScript, Glogi, Transit, Matcher-combinators
- This version was accidentally released under the `lambdaisland` group ad
  1.0.107. The canonical version going forward is under `com.lambdaisland`.

# 1.0.93 (2021-04-21 / b6a7aa1)

## Fixed

- Clearly alert the user that ClojureScript versions before 1.10 aren't
  supported, rather than failing on whatever 1.10 functionality happens to be
  invoked first.
- Show the file/line of the deftest in case cljs.test is not able to provide a
  reasonable file/line number.

## Changed

- Bump com.lambdaisland/glogi to 1.0.112
- Release under com.lambdaisland/kaocha-cljs in line with Clojars policy
- Bump all dependencies

# 0.0-71 (2020-02-24 / 773860f)

## Fixed

- Depend on an actual version of Glogi, instead or "RELEASE"

# 0.0-68 (2019-12-25 / 71c2d86)

## Fixed

- Wait for websocket client namespace to load before attempting to connect. This
  should help in particular with reliability when running against a browser
  environment.

## Changed

- Pick a free port for websockets automatically instead of using a hard-coded port

# 0.0-59 (2019-09-12 / 9159233)

## Added

- Added support for matcher-combinators

## Changed

- When using the nodejs repl type, automatically set the CLJS compile target to :nodejs

# 0.0-51 (2019-09-11 / 4b6a751)

## Added

- Added compatibility with Figwheel REPL
- Make the CLJS-side logging configurable with `:closure-defines`

## Fixed

- Use the same compiler env for the load and run stages

## Changed

- isomorphic-ws is no longer needed on Node (ws still is)
- rework the websocket connection to be more reliable

# 0.0-40 (2019-07-02 / d0324dd)

## Changed

- Instead of using the ClojureScript PREPL we now use a queue based solution
  that bypasses the need for a Reader. This should hopefully lead to better
  reliability.

## Fixed

- Correctly pass custom compiler-options to the prepl

# 0.0-32 (2019-04-23 / 3d46a25)

## Fixed

- Honor `:kaocha.testable/wrap`, and thus `:kaocha.hooks/wrap-run`, which fixes
  support for output capturing. This work is funded by
  [Nextjournal](https://nextjournal.com/).

# 0.0-29 (2019-04-16 / 56f47ff)

## Added

- The `kaocha.type.cljs/*debug*` var can be set to see what kaocha-cljs is doing
  (use `:bindings {kaocha.type.cljs/*debug* true}` in `tests.edn`)
- Proper support `cljs.test/use-fixtures`. It still only supports the map
  version, i.e. `(use-fixtures :once {:before ... :after ...})`, but should run
  both `:once`, and `:each` fixtures, honoring uses of `async` in the fixture
  functions. This work is funded by [Nextjournal](https://nextjournal.com/).

## Fixed

- Improved error handling and cleanup, to prevent cases where Kaocha would fail
  to exit after an exception.

# 0.0-24 (2019-04-09 / 248e33c)

## Added

- Added support for `cljs.test/async`.
- Added initial support for `cljs.test/use-fixtures`. Currently both `:each` and `:once` fixtures are treated as `:each` fixtures, so they run before/after each test var.

## Fixed

## Changed

# 0.0-21 (2019-02-28 / 1be9c73)

## Fixed

- Add ClojureScript implicit options during analysis, fixes issues with CLJSJS,
  among others.

# 0.0-16 (2018-12-31 / 214b14e)

## Fixed

- Capture exception type and message so it can be reported

# 0.0-11 (2018-12-12 / 53fe73a)

## Added

- Initial implementation