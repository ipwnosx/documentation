**super**: **[UIApplication](UIApplication.md)** (on iOS)

The Application class provides a centralized point of control and coordination for apps running on your device. Every running app has exactly one instance of Application. When an app is launched, the system calls its various events in order to notify its running status. Current running application can be accessed through the App global instance.

A major role of your app's application object is to handle the initial routing of incoming user events. The application object informs of significant runtime events like app launch, low-memory warnings, and app termination, giving it an opportunity to respond appropriately.

### Events

* **DidStart**()
Use this method to initialize your app and prepare it to run. This event is called after your app has been launched and loaded, but before your app’s state has been restored. At the time this method is called, your app is in the inactive state.

* **FinishLaunching**()
Use this method to complete your app’s initialization and make any final tweaks. This method is called after state restoration has occurred but before your app’s window and other UI have been presented. At some point after this method returns, the OS calls another of your app methods to move the app to the active (foreground) state or the background state.

* **WillEnterForeground**()
This method is called as part of the transition from the background to the active state. You can use this method to undo many of the changes you made to your app upon entering the background. The call to this method is invariably followed by a call to the DidBecomeActive event, which then moves the app from the inactive to the active state.

* **DidBecomeActive**()
This method is called to let your app know that it moved from the inactive to active state. This can occur because your app was launched by the user or the system. Apps can also return to the active state if the user chooses to ignore an interruption (such as an incoming phone call or SMS message) that sent the app temporarily to the inactive state. You should use this method to restart any tasks that were paused (or not yet started) while the app was inactive.

* **WillResignActive**()
This method is called to let your app know that it is about to move from the active to inactive state. This can occur for certain types of temporary interruptions (such as an incoming phone call or SMS message) or when the user quits the app and it begins the transition to the background state. An app in the inactive state continues to run but does not dispatch incoming events to responders. You should use this method to pause ongoing tasks and disable timers. An app in the inactive state should do minimal work while it waits to transition to either the active or background state. If your app has unsaved user data, you can save it here to ensure that it is not lost. However, it is recommended that you save user data at appropriate points throughout the execution of your app, usually in response to specific actions. For example, save data when the user dismisses a data entry screen. Do not rely on specific app state transitions to save all of your app's critical data.

* **DidEnterBackground**()
Use this method to release shared resources, invalidate timers, and store enough app state information to restore your app to its current state in case it is terminated later. You should also disable updates to your app’s user interface and avoid using some types of shared system resources (such as the user’s contacts database).  Your implementation of this method has approximately five seconds to perform any tasks and return.  In practice, you should return from a DidEnterBackground event as quickly as possible. If the method does not return before time runs out your app is terminated and purged from memory.

* **OpenSettingsForNotification**(**identifier**: **[String](../gravity/string.md)**, **userInfo**: **[Map](../gravity/map.md)**)
Asks the application to display the in-app notification settings.

* **OpenUrl**(**url**: **[String](../gravity/string.md)**, **options**: **[Map](../gravity/map.md)**)
Asks the application to open a resource specified by a URL, and provides a dictionary of launch options.

* **DeviceOrientationDidChange**()
Posted when the orientation of the device changes. You can obtain the new orientation by getting the value of the Device.orientation property.

* **WillPresentNotification**(**identifier**: **[String](../gravity/string.md)**, **userInfo**: **[Map](../gravity/map.md)**)<strong>: <a href="#_enum_NotificationPresentationOptions">NotificationPresentationOptions</a></strong> 
Asks the application how to handle a notification (local or remote) that arrived while the app was running in the foreground. Return NotificationPresentationOptions.None to silence the notification completely. Specify other values to interact with the user (a combination of the following NotificationPresentationOptions bitmask options: .Badge,.Sound,.Alert).

* **DidReceiveNotification**(**identifier**: **[String](../gravity/string.md)**, **userInfo**: **[Map](../gravity/map.md)**, **threadIdentifier**: **[String](../gravity/string.md)**, **actionIdentifier**: **[String](../gravity/string.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
Asks the application to process the user's response to a delivered notification (local or remote) or a remote silent notification. Return false if you have finished processing the notification. If you performs some async activities, you must return true and then invoke the notificationProcessingCompleted method at some point after processing the notification to let the system know that you are done.

* **DidAuthorizeForPushNotifications**(**granted**: **[Bool](../gravity/bool.md)**, **error**: **[String](../gravity/string.md)**)
If you have enabled the PushNotifications (remote notification) for you apps, the authorization is performed automatically when the app is launched. After determining the authorization status, this event is fired. The event has no return value and has the two parameters, granted and error. Granted is a Bool value indicating whether authorization was granted. The value of this parameter is true when authorization was granted for one or more options. The value is false when authorization is denied for all options. Error is a String containing error information or null if no error occurred.

* **DidRegisterForPushNotifications**(**token**: **[String](../gravity/string.md)**)
This event informs you that the app successfully registered with Apple Push Notification service (APNs). The token parameter is a globally unique token that identifies this device to APNs. Send this token to the server that you use to generate remote notifications. Your server must pass this token unmodified back to APNs when sending those remote notifications.

* **DidFailToRegisterForPushNotifications**(**error**: **[String](../gravity/string.md)**)
This event informs you when Apple Push Notification service cannot successfully complete the registration process.

* **DidReceiveMemoryWarning**()
This event is called when the app receives a memory warning from the system. If your app does not release enough memory during low-memory conditions, the system may terminate it outright.

* **WillTerminate**()
This method lets your app know that it is about to be terminated and purged from memory entirely. You should use this method to perform any final clean-up tasks for your app, such as freeing shared resources, saving user data, and invalidating timers. Your implementation of this method has approximately five seconds to perform any tasks and return. If the method does not return before time expires, the system may kill the process altogether.



### Properties

* **var** **language**: **[String](../gravity/string.md)**
Returns current application language. \(read-only\)

* **var** **version**: **[String](../gravity/string.md)**
Returns current application version. \(read-only\)

* **var** **build**: **[String](../gravity/string.md)**
Returns current application build. \(read-only\)

* **var** **bundleID**: **[String](../gravity/string.md)**
Returns current application unique bundle ID. \(read-only\)

* **var** **idleTimerDisabled**: **[Bool](../gravity/bool.md)**
A Boolean value that controls whether the idle timer is disabled for the app. The default value of this property is false. When most apps have no touches as user input for a short period, the system puts the device into a sleep state where the screen dims. This is done for the purposes of conserving power. However, apps that don't have user input except for the accelerometer—games, for instance—can, by setting this property to YES, disable the idle timer to avert system sleep.

* **var** **count**: **[Int](../gravity/int.md)**
Returns the number of times your application has launched. \(read-only\)

* **var** **iconBadgeNumber**: **[Int](../gravity/int.md)**
The number currently set as the badge of the app icon in Springboard. Set to 0 to hide the badge number. The default value of this property is 0.

* **var** **memoryChecker**: **[Float](../gravity/float.md)**
A value (in seconds) to set the frequency of the memory checker to run (set to 0 to disable automatic memory checker).

* **var** **objectName**: **[String](../gravity/string.md)**
The name of the object.



### Methods

* **func** **loadContainer**(**container**: **[Window](Window.md) or [NavigationBar](NavigationBar.md)**)
Container can be a Window or a Navigation. When you set a Startup Window into Creo IDE you are setting the container parameter of this method. The new container is configured to track the window size, changing as the window size changes. If the window has an existing view hierarchy, the old views are removed before the new ones are installed.

* **func** **scheduleNotification**(**identifier**: **[String](../gravity/string.md)**, **title**: **[String](../gravity/string.md)**, **delay**: **[Float](../gravity/float.md)**, **body**: **[String](../gravity/string.md) = null**, **subtitle**: **[String](../gravity/string.md) = null**, **badge**: **[Int](../gravity/int.md) = null**, **userInfo**: **[Map](../gravity/map.md) = null**, **threadIdentifier**: **[String](../gravity/string.md) = null**, **actions**: **[List](../gravity/list.md) = null**, **repeats**: **[Bool](../gravity/bool.md) = null**)
Schedule a notification.

* **func** **removePendingNotifications**(**identifiers**: **[List](../gravity/list.md)**)
Unschedules the specified notification requests.

* **func** **removeAllPendingNotifications**()
Unschedules all pending notification requests.

* **func** **removeDeliveredNotifications**(**identifiers**: **[List](../gravity/list.md)**)
Removes the specified notification requests from Notification Center.

* **func** **removeAllDeliveredNotifications**()
Removes all of the app’s delivered notifications from Notification Center.

* **func** **openURL**(**url**: **[String](../gravity/string.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
Attempts to open the resource at the specified URL.

* **func** **canOpenURL**(**url**: **[String](../gravity/string.md)**)<strong>: [Bool](../gravity/bool.md)</strong> 
Returns a Boolean value indicating whether an app is available to handle a URL scheme.

* **func** **memoryUsage**()<strong>: [Float](../gravity/float.md)</strong> 
Returns current device memory usage (as Float). On macOS, due to the underline architecture differences, this value usually overestimates by several factors the real device memory usage.

* **func** **notificationProcessingCompleted**(**fetchResult**: **[Int](../gravity/int.md)**)
This function must be call if you return false in the DidReceiveNotification event. You should call it after fetching new data or processing the notification to let the system know that the task is done.





### Enums

<div id="_enum_NotificationPresentationOptions"></div>

#### NotificationPresentationOptions
 * .Alert
 * .Badge
 * .None
 * .Sound



