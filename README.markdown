# Draggable Test

## Hang Issue (FB13899357)

This test app reproduces an issue related to SwiftData, SwiftUI and animations that results in the UI completely locking up.

The main focus of this test app is the sidebar elements, which has a number of card elements each with a `Int32` `sortIndex` parameter. Mock data is populated on first launch.

Tapping the bug button will start the test, and then once each second two of the sidebar cards will swap `sortIndex`s. When the issues occurs isn't consistent, but eventually (usually between 30-120 seconds) the UI will completely freeze.

Given enough time this issue seems to be 100% reproducable with this setup from my testing in iOS 17.x and iPadOS 17.x simulators on M1 MacBook Pro and physical iPad mini (6th gen). I have observed the issue within a macOS native app, however, the macOS version of this test app doesn't seem to trigger it.

*YouTube video of SwiftUI Instruments profile run:*
[![SwiftUI Instuments session](http://img.youtube.com/vi/dbtQewjDoug/0.jpg)](https://youtu.be/dbtQewjDoug)

## Drop Animation Issue (FB13899959)

In iOS/iPadOS 18 Seed 1 the drop animation for the draggable sidebar card views is not nearly as nice as that on iOS/iPadOS 17.x, and seems perhaps unintentional.

*YouTube video of showing different animation iPadOS 17.4 vs iPadOS 18 Seed 1:*
[![Draggable Drop Animation](http://img.youtube.com/vi/ElB-7bKf3sw/0.jpg)](https://youtu.be/ElB-7bKf3sw)
