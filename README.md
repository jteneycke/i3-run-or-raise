# i3-run-or-raise

Run or raise implementation for i3, in node.js.

## Usage

You can use it from the commandline as well as from your configuration
file.

It takes 3 arguments in this form:

```
i3-run-or-raise --class <WindowClass> --name <WindowName> <Command>
```

You can also use short versions of the parameters:

```
i3-run-or-raise -c <WindowClass> -n <WindowName> <Command>
```

## Examples

```
bindsym $mod+c exec ~/path/to/i3-run-or-raise -c "Google-chrome" google-chrome
bindsym $mod+m exec ~/path/to/i3-run-or-raise -c "Pidgin" -n "^(?!Buddy List)$" pidgin
```

The first example is pretty straight forward. It will cycle between
chrome windows open, and if it doesn't find anything it will open it.

The second example is more interesting. The instant messenger client
Pidgin gives the same classes to conversation windows and the contact
list. So, to be able to focus the conversation window, or cycle
between them if more are open, I make a negative lookahead on the
title of the contact list window.
