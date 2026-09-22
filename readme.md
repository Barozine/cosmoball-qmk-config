# cosmoball

*A Cosmos Dactyl build using Lemon Wired Controllers with QMK firmware featuring a unique 71 key matrix, RGB underglow, and under-palm trackball similar to the keyball61.*

# Current trackball status: Funtional!
* Issue was a break in continuity between Pin 15 and its resistor. After heating it with the soldering iron, continuity was restored and everything started working properly!

# Steps taken to fix trackball issues:
* Continuity tested between the breakout board and the sensor's pins
* Voltage of 3.3v wire tested
* Pin 4 tested at 1.9v, pin 5 tested at 3.3v.
* Pins defined in config.h as described in vendor's pinout diagram
* halconf.h and mcuconf.h set to enable SPI1
* Dasky's firmware blob added to keymap.c and SROM checked
* pointing_device_get_status() returns 3, which translates to POINTING_DEVICE_STATUS_SUCCESS
* Pointing device debug messages “PMW33XX (0): motion: 0x6c dx: 0 dy: 0”
