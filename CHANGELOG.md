
## 3.3.0
- `s_packages` dependency upgraded
- Improved overlay bootstrap resolution to prefer the nearest overlay context before falling back to the root overlay.
- Fixed popup positioning for framed/scaled layouts (notably web) by keeping overlays in the same coordinate space as the caller.

## 3.2.1
- `s_packages` package dependency upgraded

## 3.2.0
- `s_packages` dependency upgraded to ^1.3.0
- `PopOverlay.dismissAllPops` added with optional `includeInvisible` and `except` parameters
- `PopOverlay.replacePop` for atomically replacing an overlay with a new one
- Added query helpers: `isVisibleById`, `getVisiblePops`, `getInvisiblePops`, `visibleCount`, `invisibleCount`
- Added `shouldDismissOnEscapeKey` flag on `PopOverlayContent` to opt out of Escape key dismissal per overlay
- Added `onMadeVisible` callback on `PopOverlayContent` (counterpart to `onMadeInvisible`)
- Added `onDragStart` and `onDragEnd` callbacks on `PopOverlayContent`
- Added `dragBounds` on `PopOverlayContent` to constrain dragging within a `Rect`
- **`FrameDesign` additions**:
  - `subtitle` property for secondary text below the title
  - `titleBarColor` and `bottomBarColor` for per-popup color customization
  - `headerTrailingWidgets` for extra action widgets in the header

## 3.1.2
- **`pop_overlay` animation improvements**:
  - Added smooth fade-in animations to all popup types; fixes flash issue in `FrameDesign` popups by smoothly animating appearance during auto dynamic dimension calculation time
  - Extended animation durations for smoother transitions: blur background (400ms → 600ms), barrier fade (0.4-0.5s → 0.8-1.0s), and animated size (300ms → 500ms)
  - Added `borderRadius` support to example demos for better visual consistency
  - Optimized popup entrance animations with `Curves.fastEaseInToSlowEaseOut` for more natural motion

## 3.1.1
- `s_packages` upgraded: Replaced `pop_overlay`'s use of `MediaQuery.of(context).size` with `Size(100.w, 100.h)` for better responsive sizing using the `sizer` package throughout the overlay system
Improved cross-platform compatibility and responsive behavior


## 3.1.0
- `s_packages` upgraded: `PopOverlay.addPop(...)` upgraded to allow pops to pop from a given `offsetToPopFrom` offset param, to a `popPositionOffset` param, with a given or default `popPositionAnimationCurve` and `popPositionAnimationDuration`.


## 3.0.2
- fixed pub.dev's Documentation analysis issue

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
