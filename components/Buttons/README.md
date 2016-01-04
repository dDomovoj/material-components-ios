# Buttons

A collection of material buttons, including a Flat button, a Raised button and a Floating button.

The Flat button does not have its own background color and does not raise when touched. A Flat
button should be used in most situations requiring a button.

The Raised button has its own background color, floats above its parent slightly, and raise briefly
when touched. A Raised button should be used when a Flat button would get lost among other UI
elements on the screen.

A Floating button is circular, floats a considerable amount above its parent, has its own background
color, and also raises briefly when touched. A Floating button should only be used for the main
action of a screen.

All buttons display animated ink splashes when the user interacts with the button.

For non-flat buttons, the background color is determined from the enabled, disabled-light, and
disabled-dark background color properties. Flat buttons have a transparent background.

When disabled, material buttons take on a specific semi-transparent appearance which depends on
whether the button is on a light background or a dark background. To ensure this works correctly,
the owner is responsible for setting (and updating, if necessary), the button's underlyingColor
property for all buttons.

The title color of the button should be set to have an accessible contrast ratio with the button's
background color. To ensure this works for Flat buttons, the caller is responsible for setting (and
updating, if necessary) the button's underlyingColor property for flat buttons.

All buttons set the exclusiveTouch property to YES by default, which prevents users from
simultaneously interacting with a button and other UI elements.

See http://www.google.com/design/spec/components/buttons.html#buttons-main-buttons.

## Requirements

- Xcode 7.0 or higher.
- iOS SDK version 7.0 or higher.

## Usage

### Create a Flat button

```objective-c
MDCButton* flatButton = [MDCFlatButton button];
[flatButton setTitle:@"Tap Me" forState:UIControlStateNormal];
[flatButton addTarget:self action:@selector(tap:) forControlEvents:UIControlEventTouchUpInside];
[self.view addSubView:flatButton];
```

```swift
var flatButton = MDCFlatButton.button()
flatButton.setTitle("Tap Me", forState: .Normal)
flatButton.addTarget(self, action: "tap:", forControlEvents: .TouchUpInside)
self.view.addSubview(flatButton)
```

### Create a Raised button and change its default elevation

```objective-c
MDCButton* raisedButton = [MDCRaisedButton button];
// See https://www.google.com/design/spec/what-is-material/elevation-shadows.html
[raisedButton setElevation:4.0f forState:UIControlStateNormal];
[raisedButton setTitle:@"Tap Me Too" forState:UIControlStateNormal];
[raisedButton addTarget:self action:@selector(tap:) forControlEvents:UIControlEventTouchUpInside];
[self.view addSubView:raisedButton];
```

```swift
var raisedButton = MDCRaisedButton.button()
// See https://www.google.com/design/spec/what-is-material/elevation-shadows.html
raisedButton.setElevation(4, forState: .Normal)
raisedButton.setTitle("Tap Me Too") forState: .Normal)
raisedButton.addTarget(self, action: "tap:", forControlEvents: .TouchUpInside)
self.view.addSubview(raisedButton)
```

### Create a Floating button

```objective-c
MDCButton* floatingButton = [MDCFloatingButton button];
[floatingButton setTitle:@"Tap Me" forState:UIControlStateNormal];
[floatingButton addTarget:self action:@selector(tap:) forControlEvents:UIControlEventTouchUpInside];
[self.view addSubView:floatingButton];
```

```swift
var floatingButton = MDCFloatingButton.button()
floatingButton.setTitle(@"Tap Me", forState: .Normal)
floatingButton.addTarget(self, action: "tap:", forControlEvents: .TouchUpInside)
self.view.addSubView(floatingButton)
```