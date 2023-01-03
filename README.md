<p align="center">
<img src="https://github.com/luanemanuel/focus_on_it/blob/master/assets/focus_on_it.png?raw=true" width="350" alt="Flutter Focus On It Package"/>
</p>

<p align="center">
	<a href="https://pub.dev/packages/focus_on_it"><img src="https://img.shields.io/pub/v/focus_on_it.svg" alt="Pub.dev Badge"></a>
	<a href="https://github.com/luanemanuel/focus_on_it/actions"><img src="https://github.com/luanemanuel/focus_on_it/workflows/test/badge.svg" alt="GitHub Build Badge"></a>
	<a href="https://github.com/tenhobi/effective_dart"><img src="https://img.shields.io/badge/style-effective_dart-40c4ff.svg" alt="Effective Dart Badge"></a>
	<a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-purple.svg" alt="MIT License Badge"></a>
	<a href="https://github.com/luanemanuel/focus_on_it/"><img src="https://img.shields.io/badge/platform-flutter-ff69b4.svg" alt="Flutter Platform Badge"></a>
</p>

A continuation of the [Focus Detector](https://pub.dev/packages/focus_detector) project which is not maintained anymore.

Get notified when a widget is focused or unfocused.

---

## About

Similar to `onResume()`/`onPause()` on Android and `viewDidAppear()`/`viewDidDisappear()` on iOS, Focus On It gives you the ability to know when a widget is focused or unfocused and let you do something about it.

Focus On It invoke callbacks when something happen to the widget focus. You can use it to get more control over your app and manage the events you might want, like:

- Pause a video when the user is not looking at it.
- Stop a camera preview when the user is not looking at it and start it again when the user is looking at it.
- Turn off a resource intensive feature when the user is not looking at it and turn it on again when the user is looking at it.
- Sync data with API when user open a screen.
- And much more!

## Events

Focus On It offers 6 events to help you manage your app:

- `onFocus`: Equivalent to `onResume()` on Android and `viewDidAppear()` on iOS. Triggered when the widget is focused after route transition or the widget resumed from a paused state.
- `onUnfocus`: Equivalent to `onPause()` on Android and `viewDidDisappear()` on iOS. Triggered when the widget is unfocused after route transition or the widget paused from a focused state.
- `onForegroundGained`: Triggered when the app is resumed from a paused state.
- `onForegroundLost`: Triggered when the app is paused from a resumed state.
- `onVisibilityGained`: Triggered when the widget is visible after route transition.
- `onVisibilityLost`: Triggered when the widget is no longer visible after route transition.

## Usage

```dart
@override
Widget build(BuildContext context) =>
    FocusOnIt(
      onFocus: () {
        /// Equivalent to `onPause()` on Android and `viewDidDisappear()` on iOS. 
        /// Triggered when the widget is unfocused after route transition or the widget paused from a focused state.
        logger.i('Focus Gained.');
      },
      onUnfocus: () {
        /// Equivalent to `onResume()` on Android and `viewDidAppear()` on iOS. 
        /// Triggered when the widget is focused after route transition or the widget resumed from a paused state.
        logger.i('Focus Lost.');
      },
      onForegroundGained: () {
        /// Triggered when the app is resumed from a paused state.
        logger.i('Foreground Gained.');
      },
      onForegroundLost: () {
        /// Triggered when the app is paused from a resumed state.
        logger.i('Foreground Lost.');
      },
      onVisibilityGained: () {
        /// Triggered when the widget is visible after route transition.
        logger.i('Visibility Gained.');
      },
      onVisibilityLost: () {
        /// Triggered when the widget is no longer visible after route transition.
        logger.i('Visibility Lost.');
      },
      child: const Placeholder(),
    );
```

## Example

- [Focus On It Example](https://github.com/luanemanuel/focus_on_it/blob/develop/test/focus_on_it_test.dart)

## Maintainers

- [Luan Emanuel](https://github.com/luanemanuel)
- [Lucas Claros](https://github.com/lucasclaros)

