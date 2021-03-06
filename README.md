<p align="center" >
<img src="https://github.com/igormatyushkin014/Sensitive/blob/master/Logo/logo-1024-300.png" alt="Sensitive" title="Sensitive">
</p>

<p align="center">
<a href="https://swift.org"><img src="https://img.shields.io/badge/Swift-4-orange.svg?style=flat"></a>
<a href="https://cocoapods.org"><img src="https://img.shields.io/cocoapods/v/Sensitive.svg?maxAge=2592000"></a>
<a href="https://cocoapods.org"><img src="https://img.shields.io/cocoapods/dt/Sensitive.svg?maxAge=2592000"></a>
<a href="https://tldrlegal.com/license/mit-license"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat"></a>
</p>

# At a Glance

`Sensitive` library is a new way to work with gestures in iOS. Approach is very similar to Android's `onClick` handler for `View` subclasses. Forget about targets and actions of primitive `UIGestureRecognizer`s. Instead of that, you can simply use blocks with methods like `onTap`, `onPinch`, `onSwipe`, etc. Each `UIView` object includes those methods via special extension. That's all that you should know to start. For details, see [Usage](#usage) section.

## How To Get Started

- Copy content of `Sensitive` folder to your project.

or

- Use `Sensitive` cocoapod.

## Requirements

* iOS 9.0 and later
* Xcode 9.0 and later
* Swift 4

## Usage

```swift
let view = UIView()

/*
 * Add tap gesture recognizer without configuration block to view.
 */

view.onTap { (tapGestureRecognizer) in
    // Handle tap on view
    tapGestureRecognizer.view!.backgroundColor = .green
}

/*
 * Add tap gesture recognizer with configuration block to view.
 */

view.onTap(when: .always, handle: { (tapGestureRecognizer) in
    // Handle tap on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (tapGestureRecognizer) in
    // Configure gesture recognizer
    tapGestureRecognizer.numberOfTouchesRequired = 1
    tapGestureRecognizer.numberOfTapsRequired = 2
}

/*
 * Add one-time tap gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onTap(when: .once, handle: { (tapGestureRecognizer) in
    // Handle tap on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (tapGestureRecognizer) in
    // Configure gesture recognizer
    tapGestureRecognizer.numberOfTouchesRequired = 1
    tapGestureRecognizer.numberOfTapsRequired = 2
}

/*
 * Set number of times to handle tap gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onTap(when: .times(count: 10), handle: { (tapGestureRecognizer) in
    // Handle tap on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (tapGestureRecognizer) in
    // Configure gesture recognizer
    tapGestureRecognizer.numberOfTouchesRequired = 1
    tapGestureRecognizer.numberOfTapsRequired = 2
}

/*
 * Add long press gesture recognizer without configuration block to view.
 */

view.onLongPress { (longPressGestureRecognizer) in
    // Handle long press on view
    tapGestureRecognizer.view!.backgroundColor = .green
}

/*
 * Add long press gesture recognizer with configuration block to view.
 */

view.onLongPress(when: .always, handle: { (longPressGestureRecognizer) in
    // Handle long press on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (longPressGestureRecognizer)
    // Configure gesture recognizer
    longPressGestureRecognizer.numberOfTouchesRequired = 1
}

/*
 * Add one-time long press gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onLongPress(when: .once, handle: { (longPressGestureRecognizer) in
    // Handle long press on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (longPressGestureRecognizer)
    // Configure gesture recognizer
    longPressGestureRecognizer.numberOfTouchesRequired = 1
}

/*
 * Set number of times to handle long press gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onLongPress(when: .times(count: 10), handle: { (longPressGestureRecognizer) in
    // Handle long press on view
    tapGestureRecognizer.view!.backgroundColor = .green
}) { (longPressGestureRecognizer)
    // Configure gesture recognizer
    longPressGestureRecognizer.numberOfTouchesRequired = 1
}

/*
 * Add pan gesture recognizer without configuration block to view.
 */

view.onPan { (panGestureRecognizer) in
    // Handle pan gesture on view here...
}

/*
 * Add pan gesture recognizer with configuration block to view.
 */

view.onPan(when: .always, handle: { (panGestureRecognizer) in
    // Handle pan gesture on view here...
}) { (longPressGestureRecognizer)
    // Configure pan gesture recognizer here...
}

/*
 * Add one-time pan gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onPan(when: .once, handle: { (panGestureRecognizer) in
    // Handle pan gesture on view here...
}) { (longPressGestureRecognizer)
    // Configure pan gesture recognizer here...
}

/*
 * Set number of times to handle pan gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onPan(when: .times(count: 10), handle: { (panGestureRecognizer) in
    // Handle pan gesture on view here...
}) { (longPressGestureRecognizer)
    // Configure pan gesture recognizer here...
}

/*
 * Add pinch gesture recognizer without configuration block to view.
 */

view.onPinch { (pinchGestureRecognizer) in
    // Handle pinch gesture on view here...
}

/*
 * Add pinch gesture recognizer with configuration block to view.
 */

view.onPinch(when: .always, handle: { (pinchGestureRecognizer) in
    // Handle pinch gesture on view here...
}) { (pinchGestureRecognizer) in
    // Configure pinch gesture recognizer here...
}

/*
 * Add one-time pinch gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onPinch(when: .once, handle: { (pinchGestureRecognizer) in
    // Handle pinch gesture on view here...
}) { (pinchGestureRecognizer) in
    // Configure pinch gesture recognizer here...
}

/*
 * Set number of times to handle pinch gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onPinch(when: .times(count: 10), handle: { (pinchGestureRecognizer) in
    // Handle pinch gesture on view here...
}) { (pinchGestureRecognizer) in
    // Configure pinch gesture recognizer here...
}

/*
 * Add rotation gesture recognizer without configuration block to view.
 */

view.onRotation { (rotationGestureRecognizer) in
    // Handle rotation gesture on view here...
}

/*
 * Add rotation gesture recognizer with configuration block to view.
 */

view.onRotation(when: .always, handle: { (rotationGestureRecognizer) in
    // Handle rotation gesture on view here...
}) { (rotationGestureRecognizer) in
    // Configure rotation gesture recognizer here...
}

/*
 * Add one-time rotation gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onRotation(when: .once, handle: { (rotationGestureRecognizer) in
    // Handle rotation gesture on view here...
}) { (rotationGestureRecognizer) in
    // Configure rotation gesture recognizer here...
}

/*
 * Set number of times to handle rotation gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onRotation(when: .times(count: 10), handle: { (rotationGestureRecognizer) in
    // Handle rotation gesture on view here...
}) { (rotationGestureRecognizer) in
    // Configure rotation gesture recognizer here...
}

/*
 * Add swipe gesture recognizer without configuration block to view.
 */

view.onSwipe { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}

/*
 * Add swipe gesture recognizer with configuration block to view.
 */

view.onSwipe(when: .always, handle: { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}) { (swipeGestureRecognizer) in
    // Configure swipe gesture recognizer here...
    swipeGestureRecognizer.direction = .Right
}

/*
 * Add one-time swipe gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onSwipe(when: .once, { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}) { (swipeGestureRecognizer) in
    // Configure swipe gesture recognizer here...
    swipeGestureRecognizer.direction = .Right
}

/*
 * Set number of times to handle swipe gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onSwipe(when: .times(count: 10), { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}) { (swipeGestureRecognizer) in
    // Configure swipe gesture recognizer here...
    swipeGestureRecognizer.direction = .Right
}

/*
 * Add swipe up gesture recognizer without configuration block to view.
 */

circleView.onSwipe(to: .up) { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}

/*
 * Add swipe right gesture recognizer without configuration block to view.
 */

circleView.onSwipe(to: .right) { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}

/*
 * Add swipe down gesture recognizer without configuration block to view.
 */

circleView.onSwipe(to: .down) { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}

/*
 * Add swipe left gesture recognizer without configuration block to view.
 */

circleView.onSwipe(to: .left) { (swipeGestureRecognizer) in
    // Handle swipe gesture on view here...
}

/*
 * Add screen edge pan gesture recognizer without configuration block to view.
 */

view.onScreenEdgePan { (screenEdgePanGestureRecognizer) in
    // Handle screen edge pan gesture on view here...
}

/*
 * Add screen edge pan gesture recognizer with configuration block to view.
 */

view.onScreenEdgePan(when: .always, handle: { (screenEdgePanGestureRecognizer) in
    // Handle screen edge pan gesture on view here...
}) { (screenEdgePanGestureRecognizer) in
    // Configure screen edge pan gesture recognizer here...
}

/*
 * Add one-time screen edge pan gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onScreenEdgePan(when: .once, handle: { (screenEdgePanGestureRecognizer) in
    // Handle screen edge pan gesture on view here...
}) { (screenEdgePanGestureRecognizer) in
    // Configure screen edge pan gesture recognizer here...
}

/*
 * Set number of times to handle screen edge pan gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onScreenEdgePan(when: .times(count: 10), handle: { (screenEdgePanGestureRecognizer) in
    // Handle screen edge pan gesture on view here...
}) { (screenEdgePanGestureRecognizer) in
    // Configure screen edge pan gesture recognizer here...
}

/*
 * Add touch gesture recognizer without configuration block to view.
 */

view.onTouch { (touchGestureRecognizer) in
    // Handle touch gesture on view here...
}

/*
 * Add touch gesture recognizer with configuration block to view.
 */

view.onTouch(when: .always, handle: { (touchGestureRecognizer) in
    // Handle touch gesture on view here...
}) { (touchGestureRecognizer) in
    // Configure touch gesture recognizer here...
}

/*
 * Add one-time touch gesture recognizer with configuration block to view.
 * Gesture recognizer will be removed from view after first recognition.
 */

view.onTouch(when: .once, handle: { (touchGestureRecognizer) in
    // Handle touch gesture on view here...
}) { (touchGestureRecognizer) in
    // Configure touch gesture recognizer here...
}

/*
 * Set number of times to handle touch gesture in view.
 * Gesture recognizer will be removed from view after 10 recognitions.
 */

view.onTouch(when: .times(count: 10), handle: { (touchGestureRecognizer) in
    // Handle touch gesture on view here...
}) { (touchGestureRecognizer) in
    // Configure touch gesture recognizer here...
}
```

Also, you can use gesture recognizers of these types:
* `Sensitive.TapGestureRecognizer`
* `Sensitive.LongPressGestureRecognizer`
* `Sensitive.PanGestureRecognizer`
* `Sensitive.PinchGestureRecognizer`
* `Sensitive.RotationGestureRecognizer`
* `Sensitive.SwipeGestureRecognizer`
* `Sensitive.ScreenEdgePanGestureRecognizer`
* `Sensitive.TouchGestureRecognizer`

Each of those gesture recognizers (except `TouchGestureRecognizer` is a subclass of gesture recognizer from iOS SDK. For example, `Sensitive.TapGestureRecognizer` is subclassed from `UITapGestureRecognizer`. The purpose of subclasses is to use closure as parameter instead of target-action approach. For example, this is how you initialize `UITapGestureRecognizer`:

```swift
let tapGestureRecognizer = UITapGestureRecognizer(target: self, action: #selector(SomeViewController.didTapWithGestureRecognizer(_:)))
```

And this is how you should use `Sensitive.TapGestureRecognizer`:

```swift
let tapGestureRecognizer = TapGestureRecognizer { (tapGestureRecognizer) in
    // Do something...
}
```

Quite simple, isn't it?

All other gesture recognizers can be initialized similar way.

`TouchGestureRecognizer` has no analogues in iOS SDK. The purpose of `TouchGestureRecognizer` is to handle any touches on the view (tap, pan, pinch, swipe, rotation, etc). You can initialize `TouchGestureRecognizer` instance similar to this way:

```swift
let touchGestureRecognizer = TouchGestureRecognizer { (touchGestureRecognizer) in
    NSLog("Recognized gesture with \(touchGestureRecognizer.numberOfTouches) touches")
}

/*
 * Now let's tell to gesture recognizer to handle gestures with one touch only.
 */

touchGestureRecognizer.numberOfTouchesRequired = .equalTo(count: 1)

/*
 * Or handle gestures with 1 or 3 touches only.
 */

touchGestureRecognizer.numberOfTouchesRequired = .predicate(block: { (numberOfTouches) -> Bool in
    return (numberOfTouches == 1)
        || (numberOfTouches == 3)
})


/*
 * Or handle gestures with any number of touches.
 */

touchGestureRecognizer.numberOfTouchesRequired = .any
```

## License

`Sensitive` is available under the MIT license. See the [LICENSE](./LICENSE) file for more info.
