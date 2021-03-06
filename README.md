# Multiple State Toggle UIButton
A UIButton subclass that implements tap-to-toggle button text. (Like the camera flash and timer buttons)

<p align="center">
<img src="screenshots/toggle.gif">
</p>

## Usage

Just **create** it with the states, and it's good to go:

```swift
let toggleButton = ToggleButton(image: myImage, states: ["First", "Second", "Last"])
```

Get and set the **current state**:

```swift
let state = toggleButton.currentStateIndex
toggleButton.currentStateIndex = 0
```

Add a **tap action** (in addition to the built-in state toggle):

```swift
toggleButton.action = { (sender) -> () in
    doStuff(sender.currentStateIndex)
}
```

Set **different colors** for different states (nil uses the button's ```tintColor```):

```swift
toggleButton.colors = [nil, UIColor.grayColor(), UIColor.redColor()]
```

Set **different images** for different states:

```swift
toggleButton.images = [myFirstImage, mySecondImage, myLastImage]
```

Or do it **all at once**:

```swift
let toggleButton = ToggleButton(
    images: [myFirstImage, mySecondImage, myLastImage],
    states: ["First", "Second", "Last"],
    colors: [nil, UIColor.grayColor(), UIColor.redColor()],
    action: { (sender) -> () in doStuff(sender.currentStateIndex) }
)
```
