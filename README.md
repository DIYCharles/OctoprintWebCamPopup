# Octoprint Webcam Popup

This is a simple html webpage that lets you open the webcam stream as a popup without toolbars. You can also set this window to persist on top so you can monnitor your print while working in other windows. 

<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/2.JPG" alt="drawing" width="80%"/>
<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/5.JPG" alt="drawing" width="80%"/>


Table of contents
=================

<!--ts-->
   * [Reason](#Reason)
   * [How To Use](#How-To-Use)
<!--te-->

Reason
============

There are a couple issues I have with the octoprint webcam stream. From the UI you can't really open it full screen well and If you zoom in it will also be super zoomed in when you return to octoprint. 

There is a webcam url you can use but it has the same problems listed above. Additionally it uses large borders and it does not scale when you resize the window. Additionally it has all the chrome toolbars that stay pinned to the top of the window taking up lots of space. 
<div style="align: center">
    <img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/1.JPG" alt="drawing" width="80%"/>
<div/>

Also if you were to make the page persist on top there is too thick of borders to be a less intrusive overlay. 



How To Use
============

1. Download the [octoprintwebcam.html](https://github.com/DIYCharles/OctoprintWebCamPopup/blob/main/octoprintwebcam.html)
2. In a text editor change the IP address to match your printer here
```html
    <div>
        <img style="-webkit-user-select: none;margin: auto; height: 100%" src="http://172.16.0.6/webcam/?action=stream">
    </div>
```

3. Change the path to match the location of where you installed this .html page
```html
<script>
    function openTheWindow() {
        var myWindow = window.open("file:///C:/Users/Charles/Desktop/octoprintwebcam.html","_blank",
    "toolbar,scrollbars,resizable,top=500,left=500");
    }
</script>
```
4. Open the .html file in a web browser like chrome. (right click> open with> chrome) Bookmark the page for easy access if you want.
5. Scroll down on the webpage a tiny bit and click the button under the stream
<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/4.JPG" alt="drawing" width="50%"/>

Thats it!

How To Make The Page Persist On Top
============

I used the guide [here](https://www.groovypost.com/howto/howto/windows-programs-always-on-top/#:~:text=To%20make%20the%20active%20window,top%E2%80%9D%20for%20the%20active%20window.)

1. Install Autohotkey [here](https://www.autohotkey.com/)
2. Make a new txt doc by right clicking your desktop>new>text document
3. Rename it ontop.ahk
4. Confirm change of file type extension
5. Right click the file ontop.ahk and edit.
6. Add paste this in the file.``` ^SPACE::  Winset, Alwaysontop, , A ```
7. Save it
8. Copy the file to ```C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp```
9. Restart your pc
10. Open the webcam stream popup window
11. Type Ctrl+SPacebar

The page should now persist on top and allow you to use the window actively underneath

To stop always on top either exit the oage or go to your tray in the taskbar and right click on the H and select pause script.