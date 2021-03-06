**super**: **[UIResponder](UIResponder.md)** (on iOS)

This class is reserved and cannot be directly instantiated.





### Properties

* **var** **supportedInterfaceOrientations**: **<a href="#_enum_InterfaceOrientationMask">InterfaceOrientationMask</a>**
Returns all of the interface orientations that the Window supports.

* **var** **title**: **[String](../gravity/string.md)**
A String that provides the current title of the window or navigation.

* **var** **interfaceOrientation**: **<a href="#_enum_InterfaceOrientation">InterfaceOrientation</a>**
Convenience property that provides the current orientation of the interface. \(read-only\)

* **var** **editing**: **[Bool](../gravity/bool.md)**
A Boolean value indicating whether the view currently allows the user to edit the contents.

* **var** **automaticallyAdjustsScrollViewInsets**: **[Bool](../gravity/bool.md)**
A Boolean value that indicates whether the view should automatically adjust its scroll view insets.

* **var** **parent**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**
The parent container (NavigationBar, TabBar, etc.). \(read-only\)

* **var** **presentingWindow**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**
The Window that presented this Window modally. If the Window was not presented modally, but one of its ancestors was, this property contains the Window that presented the ancestor. If neither the current Window or any of its ancestors were presented modally, the value in this property is null. \(read-only\)

* **var** **presentedWindow**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**
The Window that is presented modally by this Window. \(read-only\)

* **var** **navigationBar**: **[UINavigationController](UINavigationController.md)**
The nearest ancestor in the Window hierarchy that is a NavigationBar. \(read-only\)

* **var** **tabBar**: **[UITabBarController](UITabBarController.md)**
The nearest ancestor in the Window hierarchy that is a TabBar. \(read-only\)

* **var** **pageSplit**: **[UISplitViewController](UISplitViewController.md)**
The nearest ancestor in the Window hierarchy that is a PageSplit. \(read-only\)

* **var** **modalPresentationStyle**: **[Int](../gravity/int.md)**
The presentation style determines how a modally presented view controller is displayed onscreen. In a horizontally compact environment, modal view controllers are always presented full-screen. In a horizontally regular environment, there are several different presentation options.

* **var** **objectName**: **[String](../gravity/string.md)**
The name of the object.



### Methods

* **func** **isViewLoaded**()<strong>: [Bool](../gravity/bool.md)</strong> 
Returns a Boolean value indicating whether the view is currently loaded into memory, it does not attempt to load the view if it is not already in memory.

* **func** **updateStatusBar**()
Indicates to the system that the status bar attributes have changed.





### Enums

<div id="_enum_InterfaceOrientationMask"></div>

#### InterfaceOrientationMask
 * .All
 * .AllButUpsideDown
 * .Landscape
 * .LandscapeLeft
 * .LandscapeRight
 * .Portrait
 * .PortraitUpsideDown

<div id="_enum_InterfaceOrientation"></div>

#### InterfaceOrientation
 * .LandscapeLeft
 * .LandscapeRight
 * .Portrait
 * .PortraitUpsideDown



