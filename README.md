# Octoprint Webcam Popup

This is a simple html webpage that lets you open the webcam stream as a popup without toolbars. You can also set this window to persist on top so you can monitor your print while working in other windows. 

<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/8.JPG" alt="drawing" style="display: block; margin-left: auto; margin-right: auto; width: 50%;"/>
<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/7.JPG" alt="drawing" style="display: block; margin-left: auto; margin-right: auto; width: 80%;"/>


Table of contents
=================

<!--ts-->
   * [Reason](#Reason)
   * [NEW How To Use Chrome App Mode](#NEW-How-To-Use-New-Chrome-App-Mode)
   * [How To Use](#How-To-Use)
   * [How To Make The Page Persist On Top](#how-to-make-the-page-persist-on-top)
<!--te-->

Reason
============

There are a couple issues I have with the octoprint webcam stream. From the UI you can't really open it full screen well and If you zoom in it will also be super zoomed in when you return to octoprint. 

There is a webcam url you can use but it has the same problems listed above. Additionally it uses large borders and it does not scale when you resize the window. Additionally it has all the chrome toolbars that stay pinned to the top of the window taking up lots of space.
    <img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/1.JPG" alt="drawing" style="display: block; margin-left: auto; margin-right: auto; width: 80%;"/>

Also if you were to make the page persist on top there is too thick of borders to be a less intrusive overlay. 

NEW How To Use Chrome App Mode
============
The App mode has a much smaller window with no address bar as you can see here <img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/6.JPG" alt="" width="50%"/>

1. Download the [octoprintwebcamNoButton.html](https://github.com/DIYCharles/OctoprintWebCamPopup/blob/main/octoprintwebcamNoButton.html) and [octoprintwebcamAppMode.bat](https://github.com/DIYCharles/OctoprintWebCamPopup/blob/main/octoprintwebcamAppMode.bat)

2. Open octoprintwebcamNoButton.html in a text editor change the IP address to match your printer here
```html
    <div>
        <img style="-webkit-user-select: none;margin: auto; height: 100%" src="http://172.16.0.6/webcam/?action=stream">
    </div>
```

3. Open octoprintwebcamAppMode.bat in a text editor Change the path to match the location of where you installed the octoprintwebcamNoButton.html
```bat
start chrome.exe -app=file:///C:/DEV/Repo/OctoprintWebCamPopup/octoprintwebcamNoButton.html
```
4. After saving both, open file explorer and double click octoprintwebcamAppMode.bat to run it.
5. You can resize your window to whatever you want.
6. If you want the window to stay open even if you click behind it follow [How To Make The Page Persist On Top](#how-to-make-the-page-persist-on-top) at the bottom of this page.

Thats it!

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

#### **[An In depth guide for this can be found in my other repo StayOnTop](https://github.com/DIYCharles/StayOnTop)**

Here is a quick overview of the steps

1. Download StayOnTop.exe from this repo 
2. Run the .exe
3. Open the webcam stream popup window and click on the top taskbar for the window to make sure it is the selected active window 
4. Type Ctrl+Spacebar

The page should now persist on top and allow you to use the window actively underneath

To stop always on top click ctrl+spacebar again, exit the page, or go to your tray in the taskbar and right click on the atom icon and select pause script.

### Optional How To Make StayOnTop Run On Startup

You will need to run the StayOnTop.exe every time you restart your computer. If your would like for it to automatically run on start follow these steps.
1. Copy the StayOnTop.exe or a shortcut to StayOnTop.exe to ```C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp```
2. Restart your pc
3. You should see the Atom icon in your system tray in the taskbar after startup
4. Activate anytime by going to the window you want to keep on top and pressing Ctrl+Spacebar 