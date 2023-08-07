# LEGO® Mindstorms® Spike Hub and the Hub Buttons

A Python snippet utilizing the LEGO Spike buttons, [MicroPython](https://lego.github.io/MINDSTORMS-Robot-Inventor-hub-API/), and the `is_pressed()` and `is_released()` commands.

## Sample Code

```py
from mindstorms import MSHub
from mindstorms.control import wait_for_seconds

hub = MSHub()

while True:

    if hub.left_button.is_pressed() and hub.right_button.is_pressed():

        break

    elif hub.left_button.is_pressed():

        hub.speaker.start_beep(50)
        hub.status_light.on('violet')
        hub.light_matrix.show_image('ARROW_W')

        hub.left_button.wait_until_released()

    elif hub.right_button.is_pressed():

        hub.speaker.start_beep(70)
        hub.status_light.on('green') 
        hub.light_matrix.show_image('ARROW_E')

        hub.right_button.wait_until_released()

    hub.speaker.stop()
    hub.status_light.off()
    hub.light_matrix.off()

    wait_for_seconds(1)

    hub.speaker.beep(90)

hub.speaker.beep()
```

***

## Repo Resources

* [Visual Studio Code](https://code.visualstudio.com/)
* [MicroPython for LEGO Robot Inventor](https://www.lego.com/en-ca/themes/mindstorms/downloads)
* [LEGO Mindstorms](https://www.lego.com/en-ca/themes/mindstorms)
* [LEGO Mindstorms App for Mac](https://apps.apple.com/us/app/lego-mindstorms-inventor/id1515448947)
* [LEGO Mindstorms App for Android](https://play.google.com/store/apps/details?id=com.lego.retail.mindstorms)
* [LEGO Mindstorms App for Windows](https://www.microsoft.com/store/apps/9N7GN3KC2GK6)

<a href="https://codeadam.ca">
<img src="https://codeadam.ca/images/code-block.png" width="100">
</a>

