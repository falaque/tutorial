screen command in linux:
=======================

## Command: “Ctrl-a”

 Screen uses the command “Ctrl-a” that’s the control key and a lowercase “a”  as a signal to send commands to screen instead of the shell.

For example, “Ctrl-a” then “?”. You should now have the screen help page.

## Creating Windows

### Command: “Ctrl-a” “c”.

To create a new window, you just use “Ctrl-a” “c”. This will create a new window for you with your default prompt.  Your old window is still active.

### Switching Between Windows
 * To go to first window: "Ctrl-a" "0"
 * To go to 2nd widndow: "Ctrl-a" "1"
 * To go to next window: "Ctrl-a" "n", previous: "Ctrl-a" "p" 

## Detaching/Reattach Screen
Detaching is the most powerful part of screen.  Screen allows you to detach from a window and reattach later.

You can detach from the window using: “Ctrl-a” “d”

you can re-attach by just running:
```
$ screen -r
$ screen -r <name_of_screen>
```
Create screen with name:
```
$ screen -S my_screen
```
## Other Commands:

#### To see how many screen are available:
```
$ screen -ls
```
#### To Activate screen loggin:
 To activate screen logging function, just press ***“Ctrl-A”*** and ***“H“*** . (Please be careful, we use capital ‘H’ letter. Using non capital ‘h’, will only create a screenshot of screen in another file named hardcopy).

At the bottom left of the screen, there will be a notification that tells you like: Creating logfile “screenlog.0“. You will find screenlog.0 file in your home directory.

Another way to activate logging feature, you can add the parameter “-L” when the first time running screen:
```
$ screen -L
```





Refereces:
* https://www.rackaid.com/blog/linux-screen-tutorial-and-how-to/