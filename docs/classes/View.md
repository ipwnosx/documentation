**super**: **[UIScrollView](UIScrollView.md)** (on iOS)

The View class defines a rectangular area on the screen and the interfaces for managing the content in that area. At runtime, a view object handles the rendering of any content in its area and also handles any interactions with that content. The View class itself provides basic behavior for filling its rectangular area with a background color.

### Events

* **Load**()
This event is called when the object becames available in the current runtime system.

* **WillShow**()
The view is about to be added to the App's views hierarchy.

* **WillHide**()
The view is about to be removed from the App's views hierarchy.

* **Draw**(**rect**: **[Rect](Rect.md)**)
Draws the receiver’s image within the passed-in rectangle.

* **TouchesBegan**(**touches**: **[Object](../gravity/object.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
This event is called when one or more new touches occurred in this view and the userInteractionEnabled property is enabled. Return "true" if you want to consume the event and not forward it to the next responder, return "no" to forward any events that you do not handle yourself.

* **TouchesMoved**(**touches**: **[Object](../gravity/object.md)**, **touchInside**: **[Bool](../gravity/bool.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
This event is called when the location or force of a touch changes and the userInteractionEnabled property is enabled. Return "true" if you want to consume the event and not forward it to the next responder, return "no" to forward any events that you do not handle yourself.

* **TouchesEnded**(**touches**: **[Object](../gravity/object.md)**, **touchInside**: **[Bool](../gravity/bool.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
This event is called when one or more fingers are raised and the userInteractionEnabled property is enabled. Return "true" if you want to consume the event and not forward it to the next responder, return "no" to forward any events that you do not handle yourself.

* **TouchesCancelled**(**touches**: **[Object](../gravity/object.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
This event is called when the sysyem receives a system interruption (such as a system alert) requiring cancellation of the touch sequence and the userInteractionEnabled property is enabled. Return "true" if you want to consume the event and not forward it to the next responder, return "no" to forward any events that you do not handle yourself.

* **ViewForZooming**()<strong>: [UIView](UIView.md)</strong> 
Asks for the view to scale when zooming is about to occur in the scroll view. Return nil if you don’t want zooming to occur. Zooming is enabled if you returns a valid view in this event and if the maximumZoomScale is greater than the minimumZoomScale. Pinch to zoom is not currently supported in Creo Simulator but it works in iOS devices and in the Apple iOS simulators.

* **DidZoom**()
This event is called when the scroll view’s zoom factor changed.

* **DidScroll**()
This event is called when the user scrolls the content view.

* **DidEndDragging**(**decelerate**: **[Bool](../gravity/bool.md)**)
This event is called when dragging ended in the scroll view. The scroll view sends this event when the user’s finger touches up after dragging content. The decelerating property of the scroll view controls deceleration. The decelerate value is true if the scrolling movement will continue, but decelerate, after a touch-up gesture during a dragging operation. If the value is NO, scrolling stops immediately upon touch-up.

* **DidEndDecelerating**()
This event is called when the scroll view ends decelerating the scrolling movement.

* **DidShow**()
The view has been added to the App's views hierarchy.

* **DidHide**()
The view has been removed from the App's views hierarchy.

* **Unload**()
This event is called when the object has been removed from the current runtime system (but not yet deallocated).



### Properties

* **var** **passthroughTouches**: **[Bool](../gravity/bool.md)**
A Boolean value that determines whether user events are ignored by the view. This property doesn't affect the user interaction with subviews.

* **var** **autoContentSize**: **[Int](../gravity/int.md)**
A value that specifies how the view should calculate its size to eventually scroll. With Manual you have to specifiy the size via contentSize and the view may scroll if the size in any direction is bigger than the frame; with Fixed the content size always matches the frame, therefore the content can not scroll by user interaction; with Flex (and if flex is enabled) the size depends on how much space the childrens require along the flex main direction, the view may become scrollable if the display does not fit the space required.

* **var** **rowIndex**: **[Int](../gravity/int.md)**
Use this property to set row index in case of view used in a controls that require an array of views.

* **var** **customView**: **[CustomView](CustomView.md)**
Custom view template set in the View inspector.

* **var** **dataSet**: **[Object](../gravity/object.md)**
The <a href="DataSet.html">DataSet</a> object provides information that View needs to construct its content. The dataSet must return a List of objects and each object represents a different row. If the DataSet value is not flat, for example a Map from a JSON result of an <a href="HTTPRequest.html">HTTPRequest</a>, the keyPath property defines the list of keys used to browse the data tree to get a List node.

* **var** **keyPath**: **[String](../gravity/string.md)**
The base keyPath to get a particular node of the <a href="DataSet.html">DataSet</a> value. The DataSet must provide a List of objects and each object represents a different item. The view shows an item at a time, depending on the rowIndex property value. If the DataSet value is not flat, for example a Map from a JSON result of an <a href="HTTPRequest.html">HTTPRequest</a>, the keyPath defines the list of keys used to browse the data tree to get a List node. The values for each exposed property of the cell are retrieved by adding the current index and the cell property key to the base keyPath.

* **var** **minimumZoomScale**: **[Float](../gravity/float.md)**
A floating-point value that specifies the minimum scale factor that can be applied to the scroll view's content. The default value is 1.0.

* **var** **maximumZoomScale**: **[Float](../gravity/float.md)**
A floating-point value that specifies the maximum scale factor that can be applied to the scroll view's content. The default value is 1.0. Zooming is enabled if you returns a valid view in the ViewForZooming event and if the maximumZoomScale is greater than the minimumZoomScale.

* **var** **zoomScale**: **[Float](../gravity/float.md)**
A floating-point value that specifies the current scale factor applied to the scroll view's content. The default value is 1.0.

* **var** **objectName**: **[String](../gravity/string.md)**
The name of the object.



### Methods

* **func** **reload**(**reloadDataSet**: **[Bool](../gravity/bool.md)**)
Reloads the content of the view.

* **func** **image**()<strong>: [Image](Image.md)</strong> 
Returns the rasterized Image of the current view.

* **func** **animate**(**duration**: **[Float](../gravity/float.md)**, **delay**: **[Float](../gravity/float.md)**, **options**: **<a href="#_enum_AnimationOption">AnimationOption</a>**, **animations**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="animations ()" data-content="The animations closure, if set, contains the changes to commit to the views. This is where you programmatically change any animatable properties of the views in your view hierarchy. This block takes no parameters and has no return value.">Closure</a>**, **completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion (finished: Bool)" data-content="The completion closure, if set, is executed when the animation sequence ends. This block has no return value and takes a single Bool argument that indicates whether or not the animations actually finished before the completion handler was called. If the duration of the animation is 0, this block is performed at the beginning of the next run loop cycle.">Closure</a>**)
Animate changes to one or more views using the specified duration, delay, options and completion handler.

* **func** **setFocus**()
Force focus to be set to the selected control. For TextField and TextView that means force Keyboard to appear.

* **func** **clearFocus**()
Clear focus from selected control





### Enums

<div id="_enum_AnimationOption"></div>

#### AnimationOption
 * .AllowAnimatedContent
 * .AllowUserInteraction
 * .Autoreverse
 * .BeginFromCurrentState
 * .CurveEaseIn
 * .CurveEaseInOut
 * .CurveEaseOut
 * .CurveLinear
 * .LayoutSubviews
 * .OverrideInheritedCurve
 * .OverrideInheritedDuration
 * .OverrideInheritedOptions
 * .Repeat
 * .ShowHideTransitionViews
 * .TransitionCrossDissolve
 * .TransitionCurlDown
 * .TransitionCurlUp
 * .TransitionFlipFromBottom
 * .TransitionFlipFromLeft
 * .TransitionFlipFromRight
 * .TransitionFlipFromTop
 * .TransitionNone



