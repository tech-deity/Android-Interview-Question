# Android-Interview-Question


## What is Android ?

1. Android is mobile platform it consist of linux operating system , middleware and key Application
2. By Google **Android is an open source , linux based software stack created for  wide array of devices and form factors**



## Android Components
### Explain briefly all the Android application components

**App components** are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app.
There are four different types of app components :

* **Activities** - An activity is the entry point for app interaction with the user. It represents a single screen with a user interface.
* **Services** - A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons. It is a component that runs in the background to perform long-running operations or to perform work for remote processes.
* **Broadcast receivers** - A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements.
* **Content providers** - A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access.



### What is an Activity?

An **Activity** represent a single screen with a user interface just like window or frame of java .. Android activity is the subclass of context Theme Wrapper Class

An **activity** provides the window in which the app draws its UI. This window typically fills the screen, but may be smaller than the screen and float on top of other windows. Generally, one activity implements one screen in an app. For instance, one of an app’s activities may implement a Preferences screen, while another activity implements a Select Photo screen.

--------------
## Activity Lifecycle
### Activity Lifecycle (in execution order) -

| Method  | Called When  |
|---|---|
| onCreate()   | Activity is first created.  |
| onStart()    | Activity is becoming visible to the user.  |
| onResume()   | Activity will start interacting with the user.  |
| onPause()    | Activity is not interactable to the user.  |
| onStop()     | Activity is no longer visible to the user.  |
| onRestart()  | After activity is stopped, prior to start.  |
| onDestroy()  | Before activity is destroyed.  |

 >*Note - The onCreate() and onDestroy() methods are called only once throughout the activity lifecycle.



### Uses case of activity lifecycle with execution order

##### **When activity is opened:**
```kotlin
onCreate()

onStart()

onResume()
```
##### **When moved to another activity:**
> Here A == first activity and B == second activity

```kotlin
onPause() - (A)

onCreate() - (B)

onStart() - (B)

onResume() - (B)

onStop() - (A)
```

##### **When another activity is closed and moving back to first activity:**

```kotlin
onPause() - (B)

onRestart() - (A)

onStart() - (A)

onResume() - (A)

onStop() - (B)

onDestroy() - (B)
```

### onStart vs onResume
**onStart()** -> called when the activity becomes visible, but might not be in the foreground (e.g. an AlertFragment is on top or any other possible use case).

### **What is the project structure of an Android Application?**


**onResume()** -> called when the activity is in the foreground, or the user can interact with the Activity.

### onPause vs onStop
**onPause()** -> If you can still see any part of it (Activity coming to foreground either doesn't occupy the whole screen, or it is somewhat transparent).

**onStop()** -> If you cannot see any part of it


