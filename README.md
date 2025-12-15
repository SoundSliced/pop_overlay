# pop_overlay

A flexible and feature-rich Flutter package for displaying customizable pop-up notifications, alerts, and overlay UI elements. Perfect for building modern UIs with animated overlays, draggable popups, and background blur effects.

## Demo

![Demo](https://raw.githubusercontent.com/christophechanteur/pop_overlay/main/example/assets/example.gif)

## Features

- ✨ **Multiple Overlays**: Display multiple popups simultaneously with automatic stacking and priority management
- 🎨 **Customizable Animations**: Smooth entrance and exit animations with full animation control
- 🌫️ **Background Blur Effects**: Optional blur overlay with configurable intensity
- 🎯 **Tap-to-Dismiss**: Background tap dismissal with configurable behavior
- 🖱️ **Draggable Popups**: Make popups draggable with position tracking using state management
- 📋 **Framed Design**: Pre-built UI Frame system for consistent popup styling
- ⌨️ **Keyboard Support**: Escape key listener for keyboard-based dismissal
- ⚡ **Performance Optimized**: Efficient rendering with smart animation controls
- 🎛️ **Full Customization**: Control colors, sizes, animations, and more
- 📱 **Responsive**: Adapts to different screen sizes and orientations

## Installation

Add this to your package's `pubspec.yaml` file:

```yaml
dependencies:
  pop_overlay: ^1.0.0
```

Then run:

```bash
flutter pub get
```

## Usage

### Basic Pop-up

```dart
import 'package:pop_overlay/pop_overlay.dart';

// Create and show a simple popup
PopOverlay.addPop(
  PopOverlayContent(
    id: 'my_popup',
    widget: Container(
      padding: const EdgeInsets.all(16),
      child: const Text('Hello, Pop Overlay!'),
    ),
  ),
);

// Remove the popup
PopOverlay.removePop('my_popup');
```

### Pop-up with Customization

```dart
PopOverlay.addPop(
  PopOverlayContent(
    id: 'custom_popup',
    widget: MyCustomWidget(),
    barrierDismissible: true,
    barrierColor: Colors.black.withValues(alpha: 0.5),
    animationDuration: const Duration(milliseconds: 300),
  ),
);
```

### Draggable Pop-up

```dart
PopOverlay.addPop(
  PopOverlayContent(
    id: 'draggable_popup',
    widget: MyContentWidget(),
    isDraggeable: true,
  ),
);
```

### Pop-up with Framed Design

```dart
final template = FrameDesign(
  title: 'Settings',
  showCloseButton: true,
  titlePrefixIcon: Icons.settings,
  onSuccess: () => PopOverlay.removePop('settings_popup'),
);

PopOverlay.addPop(
  PopOverlayContent(
    id: 'settings_popup',
    widget: MySettingsWidget(),
    frameDesign: template,
    isDraggeable: true,
  ),
);
```

## API Reference

### PopOverlay

Main static class for managing popups.

- `addPop(PopOverlayContent content)` - Add a popup to the overlay
- `removePop(String id)` - Remove a popup by ID
- `removeAllPops()` - Remove all active popups
- `getPop(String id)` - Get a popup by ID

### PopOverlayContent

Configuration class for individual popups.

**Parameters:**
- `id` (String) - Unique identifier for the popup
- `widget` (Widget) - Content widget to display
- `isDraggeable` (bool) - Enable drag functionality (default: false)
- `frameDesign` (FrameDesign?) - Optional Frame design template
- `barrierDismissible` (bool) - Allow dismissal by tapping outside (default: true)
- `barrierColor` (Color) - Background overlay color
- `animationDuration` (Duration) - Animation duration for entrance/exit
- `positionController` (Injected<Offset>) - Position tracker for draggable popups

### FrameDesign

Pre-built Frame template for consistent popup UI.

**Parameters:**
- `title` (String?) - Popup title
- `showCloseButton` (bool) - Show close button (default: true)
- `titlePrefixIcon` (IconData?) - Icon before title
- `onSuccess` (VoidCallback?) - Success button callback



### Advanced Features

The gif above demonstrates:
- Multiple stacked popups
- Smooth animations
- Draggable functionality
- Design template styling

## Performance Optimizations

The package includes several performance optimizations:

- **Smart Animation Control**: Animations are disabled during drag operations for smooth performance
- **Efficient State Management**: Custom drag state controller prevents unnecessary rebuilds
- **Lazy Rendering**: Overlays are only rendered when needed
- **Minimal Dependencies**: Lightweight package with carefully selected dependencies

## Dependencies

- `flutter_animate`: Advanced animation effects
- `s_future_button`: Button with async support
- `states_rebuilder_extended`: State management
- `s_widgets`: Utility widgets
- `sizer`: Responsive sizing

See `pubspec.yaml` for the complete list.

## Examples

Complete working examples are available in the `example/` directory:

- Basic pop-up notification
- Draggable popup with Frame Design template
- Multiple popups with priorities
- Customized animations and styling

Run the example:

```bash
cd example
flutter run
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

If you encounter any issues or have feature requests, please file an issue on the GitHub repository.

---

Made with ❤️ by Christophe Chanteur
