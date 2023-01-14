# Operational Description #

## Attraction Mode ##
System will start a mode, which will play a sound and flash some lights approximately every 15 +/- 1-5 Minutes. 

## Fortune telling ##
1. If Person is attracted either a button must be pressed or "coin" must be inserted.
2. Window of Machine opens and interior light turns on
3. Plasma-Globe is turned on
4. mannequin requests to put hand on Plasma-Globe timer _timeout_ starts
5. Arduino is monitoring voltage on current-sense resistor. If voltage overcomes a certain threshold ~0.95V timer _read_ is triggered. (Signaling to RPI) Hand must remain on Plasma-Globe during the "read". If hand is remove timer _timout_ starts.
6. Timer _read_ finishes -> 7  ||  or timer _timout_ finishes -> 11
7. Plasma-Globe turns off
8. Head and hands of mannuequin will start moving and lights are flashing for 15 seconds
9. Machine reads a random quote (Text to Speech?)
10. Machine asks if you want you quote printed.
    * Press Button
    * TTS?
    -> Quote will be printed
    // direct print?
11. Window Closes and interior lights turn off

*Note: SPI, I2C, Serial, any kind of signaling would work.

# Hardware #
* Arduino and Raspberry Pi
* Fridge compressor with pneumatic valve for air driven actuator (pneumatic cylinder)
* don't forget your freewheel diodes.

### No Touch ###

![alt text](https://github.com/SMLunchen/PanzerOfTheLake/blob/master/Image/current_wf_no_touchy.png?raw=true)

### Plasma-Globe touched ###

![alt text](https://github.com/SMLunchen/PanzerOfTheLake/blob/master/Image/current_wf_touchy.png?raw=true)
