# Octoprint Webcam Popup
=========

This is a simple html webpage that lets you open the webcam stream as a popup without toolbars. 

<img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/2.JPG" alt="drawing" width="80%"/>

Table of contents
=================

<!--ts-->
   * [Reason](#Reason)
   * [Build](#Build)
   * [QMK Firmware](#QMK-Firmware)
   * [Compile And Flash](#Compile-And-Flash)
<!--te-->

Reason
============

There are a couple issues I have with the octoprint webcam stream. From the UI you can't really open it full screen well and If you zoom in it will also be super zoomed in when you return to octoprint. 

There is a webcam url you can use but it has the same problems listed above. Additionally it uses large borders and it does not scale when you resize the window. Additionally it has all the chrome toolbars that stay pinned to the top of the window taking up lots of space. 
<div style="align: center">
    <img src="https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/1.JPG" alt="drawing" width="80%"/>
<div/>



How To Use
============

1. Download the octoprintwebcame.html
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

![alt text](https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/2.JPG "img4.jpg" width="15%" )


In the kb/keymaps/default/keymap.c you can change the key bindings. Currently I have them set to 

* LCTL(KC_Z) **Undo**
* LCTL(KC_C) **Copy**
* LCTL(KC_V) **Paste**
* LCTL(LSFT(KC_M)) **Mute mic in MS Teams**
* KC_MUTE **Rotary encoder push button mutes speakers**

```c
const uint16_t PROGMEM keymaps[][MATRIX_ROWS][MATRIX_COLS] = {

	KEYMAP(
		LCTL(KC_Z), LCTL(KC_C), LCTL(KC_V), LCTL(LSFT(KC_M)), KC_MUTE),
}
```

