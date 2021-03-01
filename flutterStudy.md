# Flutter notes

## Provider
One of the main goals of using Provider: **make rebuilding widgets more intentional/faster** </br>
Provider is a Dart library used for dependency injection (DI) and state management.
Provider itself is a widget. You wrap the app around with it. </br>
Provider.of<Flavor>(context) enables us to access data from the top of the widget tree (Provider widget is at the top of the widgets that need access to it).
Provider.of<T> does two things: retrieves the value/object that we ask for and registers current widget as the listener (context identifies the listener)
Separate flavors mean something like 'separate branches of the app (?)'. Example names of the flavors are "development, production, staging, demo". This makes testing easier, makes sure you deploy the correct version of the app etc. Different flavors enable to test different backend environments (what does it mean exactly?). For example a flavor can be used as a developer testing app with options for testing.
App flavors are defined in the app.gradle file for Android.

## Provider and Consumer widgets

setState() call causes rebuild of widgets (lifting state up, 'going up on the widget tree') - but this technique is not as efficient as when using Provider. Instead of setState() you could add Provider as ancestor widget. It will make the state update more direct and notifying the widgets easier to update. This alternative technique allows rebuild of only necessary widgets, instead of the whole tree 'below' as is the case with setState() technique.  
## ChangeNotifier & ValueNotifier

## Injecting a flavor with Provider

Flavors enable user to get the app to be configured/behave differently depending on whether it's running development, stagin or production (or another) build.

## What is a dependency injection?

Dependency injection means injecting a flavor and make it accessible inside a widget tree.

## MVP - Minimum viable product

MVP is a version of the product with **just enough features** to be usable by clients. <br> Additional features can be added after this basic version, which results in quicker delivery and avoiding unnecessary work, while keeping client product requests in mind.

## MVVM

Model-view-viewmodel

## Using Router

## BLoC development pattern - state management system for Flutter

The pattern name stand for Business, Logic and Components. It's architecture goal is to **separate presentation layer from the business logic layer**. <br> This way it's more sustainable/easier to add new features (given separate layers for adding and testing) and avoid introducing bugs to the program. <br>
In simple terms, Events come in, States come out.
![BLoC data flow](https://miro.medium.com/max/700/1*MqYPYKdNBiID0mZ-zyE-mA.png)

In the BLoC pattern some terms are heavily used, they are: </br>
**State** is the data your app is currently displaying </br>
**Event** is any action detected by an app (eg clicking a button) </br>
**Stream** is a "pipe" that enables data flow/transfer </br>
**Sink** is a point that acts as a receiver of the data 
