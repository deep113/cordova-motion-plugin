# ngMotion README

## Overview

Cordova plugin to detect when a user is driving or walking that supports both iOS and Android.

## Initialization

The `ng-motion` library will be initialized with driving and walking speed thresholds to determine when the tracked GPS motion is fast enough to be considered driving.

## Events

The `ng-motion` library should emit periodic events when the user is in motion. Each event will contain the following:

* type (walking/driving/motion)
    * walking - GPS motion with accelerometer motion that looks like walking, below the walking speed threshold.
    * driving - GPS motion that is not walking, above the driving speed threshold
    * motion - GPS motion that is not walking or driving
* speed
* heading
* current long/lat

## Logic

*Walking* - The `ng-motion` library will determine walking as below a certain speed threshold tracked via GPS motion and use the accelerometer to confirm that the user has walking-like motion. (see reference pedometer code for this)

*Driving* - The `ng-motion` library will determine driving as above a certain speed threshold traced via GPS motion and no exhibiting accelerometer motion consistentant with walking.

*Motion* - The `ng-motion` library will determine motion as any GPS motion that does not qualify as Walking or Driving.

## Example

Project will provide an example app using Ionic Framework. This app should listed to the events from the `ng-motion` library and display all the even details. It should also allow for adjusting the driving/walking speed thresholds.

## References

* [ngCordova DeviceMotion](http://ngcordova.com/docs/plugins/deviceMotion/)- Get access to the device's accelerometer.
* [ngCordova DeviceOrientation](http://ngcordova.com/docs/plugins/deviceOrientation/) - Get access to the device's compass.
* [ngCordova BackgroundGeoloc](http://ngcordova.com/docs/plugins/backgroundGeolocation/) - Cross-platform background geolocation for Cordova / PhoneGap with battery-saving "circular region monitoring" and "stop detection".
* [ngCordova Geolocation](http://ngcordova.com/docs/plugins/geolocation/) - Grab the current location of the user, or grab continuous location changes:
* [Pedometer Code ](http://stackoverflow.com/questions/10634892/javascript-undefined) - StackOverflow thread with some useable examples.
* [Build a PhoneGap Pedometer Tutorial](http://www.biosparkinnovation.org/build-your-own-health-app/)
* [Cordova Pedometer Plugin](https://github.com/leecrossley/cordova-plugin-pedometer) - looks very promising. An existing Cordova Plugin that provides "pedometer services". This is unfortunately only iOS so will only be usefully as reference.
* ["Walkable" Geolocation App](http://www.tricedesigns.com/2012/10/02/introducing-walkable-a-new-sample-app-for-phonegap/) - Example app that handles iOS/Android Geolocation features.