# applescripts

This is a repo of some basic Applescripts that I've made during my time doing stuff on the computer. I'm honestly not a huge fan of Applescript as a scripting language (the only thing that I *really* miss about Windows is [AutoHotKey](https://autohotkey.com), but it's verbose in a good way (aka very easy to understand, like, what everything does) and kinda endearing. 

---

In alphabetical order, here's a brief desciption of the scripts in this repo. 

*Last updated: 25 Febuary 2018*

## bulkScreenshotter

**Developed:** September 2017
**Versions:** 1

This is a fun one. Probably the script I've spent the most mental time on, design-wise. It automatically screenshots an on-screen area an arbitrary amount of times. It takes the x and y coordinates, width, height, and number of screenshots via input dialogs, and then executes the screenshot command via shell script. I have a retina screen and I've noticed that the coordinates on screen (and, thus, the width and height I enter into the script) are half the value of what the file info says on the actual screenshots. Maybe this breaks on non-retina screens? 

Also: unless you're really good at window positioning on the fly, you should probably run this from your menu bar to avoid accidentally screenshotting part of your window. It'll also display the progress bar in your menu bar instead of in SCript Editor. You can find out how to configure that [here](https://alvinalexander.com/mac-os-x/how-to-show-applescript-menu-item-mac-osx-menu-bar) (not my article).

**extensions:**

* allow x/y coords to be entered in one input dialog
* enter x/y coords of top-left and bottom-right instead of entering top-left, width, and height
* test this on a non-retina display and see if it breaks or if the file-info width and height are different

## charAdder

**Developed:** October 2014
**Versions:** 1

The companion app to `charDeleter`, this cute little script adds the string " - " to the end of an arbitrary amount of lines in Evernote. I originally wrote these two scripts to let me quickly format long lists of vocabulary words copied and pasted from a terribly-formatted PDF of a textbook. Ah, high school.

**extensions:**

* allow for an arbitrary text string to be pasted
* relatedly, don't use godforsaken keypresses for entering text
* add a progress bar!
* generalize this beyond Evernote! should be pretty easy to do, but it would require foresaking (or very much generalizing) the `tell application "Evernote" to activate` command that's so very useful.

## charDeleter

**Developed:** October 2014
**Versions:** 2

Deletes six (6) characters from the end of an arbitrary amount of lines of an Evernote list.

**changelog:** version 1 didn't have those nice, sexy dialog boxes. Version 2 does.

**extensions:**

* allow for an arbitrary amount of characters to be deleted
* add a progress bar
* generalize to non-Evernote apps (hard, not worth it probably, but cool)

## messageSenderSimple

**Developed:** July 2015
**Versions:** 4

This is a pretty simple (and pretty annoying) script I wrote to bulk-send a message to a given person an arbitrary amount of times using Messages.app. Can select between SMS or iMessage. The boolean `SMS` selects if the recipient is an SMS number or an iMessage user, `recip` is the recipient, `message` is the text to send, and `num` is the amount of times to send the message.

This script originated because I wanted to send my friend thousands of messages for the purpose of a funny badge app icon screenshot. Since then, it's, um, still been exactly that stupid.

**changelog**: version 1 was just a loop that sent an iMessage. Version 2 added the SMS ability, version 3 added the ability to switch between them with a boolean, and version 4 property-ized everything.

**extensions:**

* `messageSenderSimple` is named such because there's a non-working script called `messageSender` that I worked on for a little bit a long time ago. It'd allow you to select everything through dialog boxes and display a progress bar. However, it's pretty severely limited by Applescript's shitty options for dialog boxes, which makes the control flow a long-ass mess of spaghetti if-elses. `messageSender` really should be a program in some language with a full set of UI features that uses the Messages.app Applescript API as a backend.

* progress bars are fun and useful if you're running this in the menu bar, I should add one

* I think the SMS-iMessage distinction is pretty unforgiving (it leaves a lot to the programmer). It'd be worth looking into the Messages.app Applescript API a little more to see if tests exist or if the flow could be improved somewhat.

## spotifyFadeAlarm

**Developed:** Febuary 2018
**Versions:** 3

This script gradually fades in a playlist or album of your choice. Enter the [Spotify URI](https://news.spotify.com/us/2008/01/14/linking-to-spotify/) as the value of the property `alarmMusicURI`. You can also select if you want the playlist to be shuffled or not using the boolean `shuffle`.

**Note:** This script is designed to be triggered from Calendar.app (or however you wish) using Automator. You can add Applescripts to an Automator workflow pretty easily, [here's how](https://support.apple.com/guide/automator/add-applescript-scripts-to-a-workflow-aut4bb6b2b4f/mac).

**changelog:** version 2 added the shuffle feature, and version 3 added the `alarmMusicURI` property.

**extensions:**

* make the fading customizable (speed, severity, etc)
* add an option to turn off the custom music (aka just have the alarm press play and fade up whatever music was already playing)
* this absolutely goes beyond the scope of a simple script, but allowing the alarm to wake up the computer if it has gone to sleep would be a useful feature
