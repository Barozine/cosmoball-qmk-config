# cosmoball

*A Cosmos Dactyl build using Lemon Wired Controllers with QMK firmware featuring a unique 71 key matrix, RGB underglow, and under-palm trackball similar to the keyball61 (currently nonfuntional)*

# Current trackball status: Nonfuntional
* No IR light being emitted (confirmed with phone camera)
* QMK firmware seems to acknowledge initialization of the PMW3389
* **Issue appears to be related to LED_P on Pin 15, which is receiving 0v.**

# Steps taken to fix trackball issues:
* Continuity tested between the breakout board and the sensor's pins
* Voltage of 3.3v wire tested
* Pin 4 tested at 1.9v, pin 5 tested at 3.3v.
* Pins defined in config.h as described in vendor's pinout diagram
* halconf.h and mcuconf.h set to enable SPI1
* Dasky's firmware blob added to keymap.c and SROM checked
* pointing_device_get_status() returns 3, which translates to POINTING_DEVICE_STATUS_SUCCESS
* Pointing device debug messages “PMW33XX (0): motion: 0x6c dx: 0 dy: 0”
