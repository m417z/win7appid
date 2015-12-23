This is a fairly basic console application for setting the application id (`System.AppUserModel.ID` property) of a Windows 7 shortcut.

In Windows 7, taskbar items are grouped by a string known as the application id or AppId. This can be set in the shortcut that launches a program, or by the application itself. See http://msdn.microsoft.com/en-us/library/dd378459%28VS.85%29.aspx for more information.

This tool allows you to pin an application and then have another application's windows group under the same icon without modifying the applications themselves. It only works if you can launch both apps via a shortcut, child processes will have the default behaviour of having their own taskbar entry.

**Usage**
```
Win7AppId <shortcut> [<new_app_id>]
```
If the app id is omitted, it simply prints the current app id.

**Example**

I made the tool so I could pin a shortcut to start a Putty session with X forwarding, start gnome-terminal and have it's X window (running under Xming) group under the pinned icon.

I issued the commands:
```
  Win7AppId xming.lnk putty-xming
  Win7AppId puttysession.lnk putty-xming
```
And then put the xming shortcut in my Startup folder and pinned puttysession to the taskbar.