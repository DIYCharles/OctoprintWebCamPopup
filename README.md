# Octoprint Webcam Popup
=========

This is a simple html webpage that lets you open the webcam stream as a popup without toolbars. 

![alt text](https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/2.JPG "img1.jpg")

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

![alt text](https://raw.githubusercontent.com/DIYCharles/OctoprintWebCamPopup/main/photos/1.JPG "img2.jpg")






```h
/* key matrix size */
#define MATRIX_ROWS 1
#define MATRIX_COLS 5

/* key matrix pins */
#define MATRIX_ROW_PINS { F7 }
#define MATRIX_COL_PINS { B3, B4, B1, B2, B5 }
#define UNUSED_PINS

#define ENCODERS_PAD_A { D1 }
#define ENCODERS_PAD_B { E6 }
#define ENCODER_DIRECTION_FLIP

/* COL2ROW or ROW2COL */
#define DIODE_DIRECTION COL2ROW

/* number of backlight levels */
```
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

