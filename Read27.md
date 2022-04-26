# Intents, Activities, and SharedPreferences

## Lifecycle of a task and its back stack

* A task is a collection of activities that users interact with when trying to do something in your app. These activities are arranged in a stack—the back stack—in the order in which each activity is opened.

* When we move from one activity to another the current activity push in stack because when we want to back to this activity we will use pop method to it

## Back press behavior for root launcher activities

* Root launcher activities are activities that declare an Intent filter with both ACTION_MAIN and CATEGORY_LAUNCHER this is Uniqu 
* when we want to back from this launcher there's some Android version finishes the activity and the other version moves the activity and its task to the background instead of finishing the activity

___

## Difference between Forground and Background

* Foreground Service is used when User is interaction with application and when Service is doing something visible to user. Background Service is used when even user close application

## Multiple activity instances 
 
if we have two activity that connect with same activeit when push this similer activity we will to do clone for this activity then push it to the stack to protect the arrangmetn.

## Defining launch modes

* Launch modes allow you to define how a new instance of an activity is associated with the current task Using two way : 
    1. Using the manifest file : When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

    2. Using Intent flags : When you call startActivity(), you can include a flag in the Intent that declares how (or whether) the new activity should associate with the current task.
* We have four type to the launch modes : 
    1. Standard :  
        It creates a new instance of activity every time even if activity instance is already present.(default launch)
    2. Single Top:  
        If an instance of activity already exists at the top of the current task, a new instance will not be created.If an instance is not present on top of the task then a new instance will be created.
    3. SingleTask :  
        An activity declared with launch mode as singleTask can have only one instance in the system (singleton). At a time only one instance of activity will exist.
    4. SingleInstance:  
        It is similar to singleTask except that no other activities will be created in the same task. If another Activity is called from this kind of Activity, a new Task would be automatically created to place that new Activity.

___

## Handle affinities

* An affinity indicates which task an activity prefers to belong to. By default, all the activities from the same app have an affinity for each other. So, by default, all activities in the same app prefer to be in the same task. However, you can modify the default affinity for an activity. 

## Clear The back stack

* If the user leaves a task for a long time, the system clears the task of all activities except the root activity. When the user returns to the task again, only the root activity is restored. The system behaves this way, because, after an extended amount of time, users likely have abandoned what they were doing before and are returning to the task to begin something new.

___ 

## Save key-value data

* if we have a relatibely small collection of key-balues we can use the "SharedPerferences" APIs is a object points to a file cointaining key-value and provides simple mehtods to read and write them

## We will to learn about how we can use SharedPerferences APIs to store key-value

1. create new shared perference file by using one of these method : 
    1. getSharedPerferences() : Use this if you need multiple shared preference files identified by name
    2. getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity
2. Write to shared perferences :   
    1. To write to a shared preferences file, create a SharedPreferences.Editor by calling edit() on your SharedPreferences.
    2. Pass the keys and values you want to write with methods such as putInt() and putString(). Then call apply() or commit() to save the changes. For example:
3. Read from shared preferences 
    * To retrieve values from a shared preferences file, call methods such as getInt() and getString(), providing the key for the value you want, and optionally a default value to return if the key isn't present. For example:
    