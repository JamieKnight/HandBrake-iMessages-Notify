HandBrake iMessages Notify
======================

Growl Applescript Action for sending iMessages when HandBrake completes an encoding job or queue. There are two scripts provided

* All Encodes - Sends an iMessage any Handbrake encodes complete.
* Notify Named Encodes Only - Sends iMessage only when the file name includes the term "notify"

HandBrake does not provide an event for when the Queue is complete, hence the "Notify Named Encodes Only". If you set the last encode in your queue to have "notify" in the name, then it acts as a work around to "Queue Completed"

## Dependencies

This Script Requires:

* Handbrake 0.9.9 or greater from http://handbrake.fr
* Growl ([Growl on the App Store](http://growl.info/growlupdateavailable#updatemas), or [Compile Grown from Source](http://growl.info/growlupdateavailable#buildgrowlfromsource))
* Working iMessages.app (OSX 10.7 Onwards)

## Setup

### Step 1: Install Growl
Either build it from source or download it from the App Store

### Step 2: Enable AppleScript support in Growl
To be allowed on the App Store, growl does some odd stuff to work with apples scripts. Follow the instructions at: http://growl.info/documentation/applescript-rules.

### Step 3: Add a Contact to notify
iMessage does not allow you to message yourself. So my script looks for a contact named 'Notify Me', add a contact under that name and add either an iMessage enabled phoned number or email address.

### Step 4: Install script 
Download or checkout this repo to ``` ~/Library/Application Scripts/com.Growl.GrowlHelperApp.```

### Step 5: Test Script
In growl, open preferences and then create a new action called'messages' of type 'Script Action'. Select the script you want in the window and click preview.

You should see iMessages for Mac load and receive the message on yor target device. If this fails, then go to 'trouble shooting' below.

### Step 6: Handbrake Config
With your script tested now let's tell handbrake to alert growl. Go into handbrake preferences and set it to notify growl when it is done. 

### Step 7: Setup Growl
Finally, in growl preference setup handbrake to call the messages action we created when encodes complete.

## Other Methods
If you only want to get an imessage for every encode, then you can use the script provided to create an application, and set that application to be called in Handbrake. However, the growl message is more flexable and better decoupled.




