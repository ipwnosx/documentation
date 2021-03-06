**super**: **[UIAlertController](UIAlertController.md)** (on iOS)

The Alert class displays a customizable alert message to the user.

### Events

* **Load**()
This event is called when the object becames available in the current runtime system.

* **WillShow**()
Use this event to be notified when the Alert is about to be added to a view hierarchy.

* **DidShow**()
Use this event to be notified when the Alert was added to a view hierarchy.

* **Action**(**index**: **[Int](../gravity/int.md)**, **title**: **[String](../gravity/string.md)**)
Use this event to be notified when user selects a button.

* **WillHide**()
Use this event to be notified when the Alert is about to be removed from a view hierarchy.

* **DidHide**()
Use this event to be notified when the Alert was removed from a view hierarchy.

* **Unload**()
This event is called when the object has been removed from the current runtime system (but not yet deallocated).



### Constructors

* **func** **Alert**(**title**: **[String](../gravity/string.md)**)
Create a new Alert message with a specified title.

* **func** **Alert**(**title**: **[String](../gravity/string.md)**, **message**: **[String](../gravity/string.md)**)
Create a new Alert message with a specified title and message.

* **func** **Alert**(**title**: **[String](../gravity/string.md)**, **message**: **[String](../gravity/string.md)**, **buttons**: **[List](../gravity/list.md)**)
Create a new Alert message with a specified title and message plus an array of buttons titles.

* **func** **Alert**(**title**: **[String](../gravity/string.md)**, **message**: **[String](../gravity/string.md)**, **buttons**: **[List](../gravity/list.md)**, **completion**: **<a href="../gravity/closure.html" data-toggle="popover" data-trigger="hover" title="completion (index: Int, title: String)" data-content="The completion closure, if set, is executed when the open action completes. Button index and title are passed as parameters.">Closure</a>**)
Create a new Alert message with a specified title and message plus an array of buttons titles. The completion closure (if set) enables you to specify an action to be executed when user press a button (button index is passed as parameter).



### Methods

* **func** **addActionWithTitle**(**title**: **[String](../gravity/string.md)**, **style**: **[Int](../gravity/int.md) = 0**)
Use this method to add a button to a newly created Alert.

* **func** **show**()
Display Alert to the user.





