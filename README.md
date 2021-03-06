# Nextpeer + Cocos2d-X

[Nextpeer](http://nextpeer.com) is the easiest way to play with your friends on mobile devices. Get the SDK and start challenging the world.

## iOS Setup for Cocos2d-X Integration

#### AppDelegate.mm

The AppDelegate controls Nextpeer delegate events, it serves as gate of information into the game.

1. Open `AppDelegate.mm`.

2. Create your Nextpeer App on [Nextpeer](http://developers.nextpeer.com/).

3. Copy your new app's product id into `AppDelegate.mm`:

```objective-c
	[Nextpeer initializeWithProductKey:@"PUT_YOUR_PRODUCT_KEY_HERE" andSettings:settings andDelegates:
     [NPDelegatesContainer containerWithNextpeerDelegate:self notificationDelegate:nil tournamentDelegate:self currencyDelegate:nil]];
```

#### PZNextpeer

`PZNextpeer.mm` is a wrapper for Nextpeer, it can be used by C++ code. When adding it to your project, make sure you add it to your compilation target by turning on the file's "target membership" flag.

#### GameFieldBaseScene

`GameFieldBaseScene.cpp` is the C++ game scene, the code demonstrates how to add Nextpeer only to the iOS version of the game, as well as how to report different events.
Pay attention to the notification center usage as a bridge between the objective c and the cpp scene.
