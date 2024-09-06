# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2024-09-06
### Changed
 -  Remove usage of Node core lib util module ([#1](https://github.com/Gandi/counterpart/pull/1)).
 -  Remove usage of `except` helper package ([#1](https://github.com/Gandi/counterpart/pull/2)).
 - **BREAKING** Replace usage of Node `EventEmitter` with native `EventTarget` ([#1](https://github.com/Gandi/counterpart/pull/3)).
   This make the package able to run server of client side without requiring polyfills. 
   This change the signature of event listener callbacks.
   They now receive a single `CustomEvent` object as argument, instead of unlimited 
   parameters. So for instance:
   ```
   // Before
   instance.onLocaleChange((locale, previous) => {})
   ```
   ```
   // After
   instance.onLocaleChange((event) => {
     // event.detail.locale
     // event.detail.previous
   })
   ```


[unreleased]: https://github.com/gandi/counterpart/compare/0.18.6...HEAD
[1.0.0]: https://github.com/gandi/counterpart/releases/tags/1.0.0
