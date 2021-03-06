**super**: **[UITabBarController](UITabBarController.md)** (on iOS)

A container window that manages a radio-style selection interface where one item is selected at a time. The selection determines which child window to display.

### Events

* **Load**()
This event is called when the object becames available in the current runtime system.

* **WillShow**()
Use this event to be notified when navigation is about to be added to a view hierarchy.

* **DidShow**()
Use this event to be notified when navigation was added to a view hierarchy.

* **WillHide**()
Use this event to be notified when navigation is about to be removed from a view hierarchy.

* **DidHide**()
Use this event to be notified when navigation was removed from a view hierarchy.

* **Unload**()
This event is called when the object has been removed from the current runtime system (but not yet deallocated).



### Properties

* **var** **bounds**: **[Rect](Rect.md)**
The bounds rectangle, which describes the view’s location and size in its own coordinate system.

* **var** **frame**: **[Rect](Rect.md)**
The frame rectangle, which describes the view’s location and size in its superview’s coordinate system.

* **var** **statusBarVisibility**: **<a href="#_enum_StatusBarVisibility">StatusBarVisibility</a>**
A value indicating whether the status bar should be visible.

* **var** **statusBarStyle**: **<a href="#_enum_StatusBarStyle">StatusBarStyle</a>**
The style of the status bar.

* **var** **tabBarTranslucent**: **[Bool](../gravity/bool.md)**
Description not yet ready.

* **var** **windows**: **[List](../gravity/list.md)**
Array of windows currently managed by the TabBar.

* **var** **selectedWindow**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**
Returns the currently selected Window or Navigation.

* **var** **selectedIndex**: **[Int](../gravity/int.md)**
The index of the Window associated with the currently selected tab item.

* **var** **barTintColor**: **[Color](Color.md)**
The tint color to apply to the bar.

* **var** **tintColor**: **[Color](Color.md)**
The tint color to apply to the selected item.

* **var** **unselectedItemTintColor**: **[Color](Color.md)**
The tint color to apply to unselected tabs.

* **var** **objectName**: **[String](../gravity/string.md)**
The name of the object.



### Methods

* **func** **open**(**completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion ()" data-content="The completion closure, if set, is executed when the open action completes. The self value points to the container being opened, so you can safely perform setup operation in this context.">Closure</a> = null**)
Open window in currently displayed window or navigation using the destination object default behaviour.

* **func** **openIn**(**window**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**, **completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion ()" data-content="The completion closure, if set, is executed when the open action completes. The self value points to the container being opened, so you can safely perform setup operation in this context.">Closure</a> = null**)
<pre><code class="swift">TargetWindow.openIn(ContainerWindow);</code></pre>
Open callee object (TargetWindow) inside parameter object (ContainerWindow) using its default behaviour. Note that TargetWindow and/or ContainerWindow can be a Window or a Navigation.

* **func** **openWindow**(**window**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**, **completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion ()" data-content="The completion closure, if set, is executed when the open action completes. The self value points to the container being opened, so you can safely perform setup operation in this context.">Closure</a> = null**)
If the Window is already contained in the TabBar window list, the TabBar set it as the selected Window. Otherwise, the TabBar add the new Window to its windows and set it as the selected Window.

* **func** **openModal**(**TransitionStyle**: **<a href="#_enum_TransitionStyle">TransitionStyle</a>**, **completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion ()" data-content="The completion closure, if set, is executed when the open action completes. The self value points to the container being opened, so you can safely perform setup operation in this context.">Closure</a> = null**)
Open window modally usign the specified transition style.

* **func** **close**(**animated**: **[Bool](../gravity/bool.md) = true**)
Close window if modally opened.





### Enums

<div id="_enum_StatusBarVisibility"></div>

#### StatusBarVisibility
 * .Default
 * .Hidden
 * .Visible

<div id="_enum_StatusBarStyle"></div>

#### StatusBarStyle
 * .DarkContent
 * .Default
 * .LightContent

<div id="_enum_TransitionStyle"></div>

#### TransitionStyle
 * .Cards
 * .CoverVertical
 * .CrossDissolve
 * .Crossfade
 * .Cube
 * .Default
 * .Explode
 * .Flip
 * .FlipHorizontal
 * .Fold
 * .NatGeo
 * .NotAnimated
 * .PartialCurl
 * .Portal
 * .Turn



