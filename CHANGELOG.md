# v2.1.1
## 10/12/2022

1. [](#improved)
   * Added support for `_DASH_` string in env keys as `-` is invaild and will throw exception
   * Modify priority for `onPluginsInitialized` to `100` as dotenv should run before other plugins

# v2.1.0
## 10/11/2022

1. [](#new)
   * Refactored logic to use `Config::merge()` rather than individual `Config::join()` calls
   * Normalize data to better support `boolean`, `int`, `float`, and `null` types

# v2.0.1
## 10/10/2022

1. [](#bugfix)
   * Fix a malformed date in changelog breaking the parsing
   * Update README.md with original author Attribution

# v2.0.0
## 10/10/2022

1. [](#new)
    * Taken over from abandoned repo: https://github.com/Ralla/grav-plugin-dotenv
    * Updated to latest v5.4.1 of `vlucas/phpdotenv` library
    * Modified plugin to use new `Immutable` variable structure and `loadSafe()` to avoid missing env file

# v1.0.0
## 02/14/2019

1. [](#new)
    * Initial commit.
