## 3.0.1
- dependent on `s_packages` version ^1.1.2

## 3.0.0
- package no longer holds the source code for it, but exports/exposes the `s_packages` package instead, which will hold this package's latest source code.
- The only future changes to this package will be made via `s_packages` package dependency upgrades, in order to bring the new fixes or changes to this package 

## 2.0.0

* **Breaking change**: PopOverlay now self-installs its activator into the root overlay.
	- removed static public method `PopOverlay.activator`.
* Added internal bootstrapper to ensure activation when `PopOverlay.addPop(...)` is called.

## 1.0.4

* updated dependencies

## 1.0.3

* updated pubspec.yaml - to specify all supported platforms

## 1.0.2

* README updated

## 1.0.1

* README and demo.gif updated

## 1.0.0

* Initial release of pop_overlay package
* Flexible pop-up overlay system with automatic stacking
* Support for multiple overlays with customizable animations
* Background blur effects and tap-to-dismiss functionality
* Priority-based display ordering
* Draggable pop-up support with position tracking
* Framed Design system for consistent UI styling
* Escape key listener for keyboard dismissal
* Performance optimizations for smooth animations
* Full customization of overlay appearance and behavior
