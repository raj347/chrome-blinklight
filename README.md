blinklight for Chrome and Firefox
=================================

This is an extension for Chrome and Firefox on Linux that notifies you about new
content (such as unread messages) in pinned tabs, using one of your laptop's
LEDs, like the power button on newer ThinkPads, or the ThinkLight on older models.

Most interactive websites, like mail and chat web apps, change the page title
in order to indicate new messages. If that happens in a pinned tab in the
background, the tab is highlighted in order to get your attention. With this
extension, in addition, an LED will be used, in order to indicate that a pinned
tab's title has changed. This is in particular useful, when the browser window
is minimized or on another workspace.

In order to pin a tab, right click on the tab and choose "Pin tab".

Installation
------------

*blinklight* consists of two parts, a browser extension that observes
pinned tabs, and a native host application that controls the LED.
In order for *blinklight* to work, both have to be installed.

### On Debian/Ubuntu

A package is available from the author's PPA, which can be installed by running
following commands (as root):

```
add-apt-repository ppa:s.noack/ppa
apt-get update
apt-get install chrome-blinklight
```

The next time you start Chromium or Firefox, the extension should be active,
and the settings, where you have to set the LED and trigger, should pop up.
If your browser is already running, restart it now. However, if you are using
Google Chrome, you have to install the extension seperately from the [Chrome Web Store][1].

### Building from source

In order to build the host application, you need a C compiler, *autotools*
and the *json-c* development files. Given you have all of these installed,
and you are in the project root now, run following commands:

```
cd native-messaging-host
autoreconf --install
./configure
make
```

Then, install the host application, by running following command (as root):

```
make install
```

Finally, install the extension for [Chrome][1] or [Firefox][2], if not done yet.
During development, you can also load the extension directly from the
`extension` subdirectory in the source tree, this however, is not recommended
for normal usage.

[1]: https://chrome.google.com/webstore/detail/blinklight/jiaipmkogklkpmpabagihfledlejmgaf
[2]: https://addons.mozilla.org/en-US/firefox/addon/blinklight/
