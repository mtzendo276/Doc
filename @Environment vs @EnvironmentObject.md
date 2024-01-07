**@EnvironmentObject**

- Its similar like `@ObservedObject`
- The model should conform to the `ObservableObject` protocol
- We need to mark properties in this model as `@Published` to notify changes to view which actively using the object
- The model object should be as class for sure
- _No need for default value_, because it can read default value from environment. If object is not available in environment, **app will crash**.
- Another major difference is, say we have 5 views(V1…V5), if we want to pass a object directly from V1 to V5 we could use `@EnvironmentObject` rather than `@ObservedObject`. Set data to be passed in V1 and retrieve it in V5(or wherever needed). Code will be much simple.
- It will hold only one type of instance at same time environment.
- Its purely based on views. If a parent view sets environment object all its child can make use of it. If another parent view set another env object, their child’s can make us of it. Eg: If you set environment object in your ContentView in SceneDelegate all its child views can make use of it.

**@Environment**

- We can use this to get system related values like whether apps is running in light or dark mode, core data's managed object context, size classes, etc...
- We need to provide proper keys to access its value, because it holds same datatype against multiple keys.