# TeslaChargeDoorOpener
Open the Tesla charge door with an Arduino and an ASK STX882 transmitter

## Introduction

The Tesla charging cables come with a button that can open the charge door of the car so that is is quicker to plug in.
Non-original cables do not have this button.

With an Arduino and a STX882 or similar ASK transmitter that costs a dollar or less on eBay, it is very easy to use this program to obtain the same functionality. You do not need an antenna, as the STX882 has long enough reach without one. This makes it a quite compact solution.

It can be programmed on an ATtiny to make it fit into small places, or on any other type of Arduino. It uses only 1078 bytes of storage and 53 bytes of RAM. I use an Arduino Nano and added a microswitch to the charge plug wall holder so that the signal is sent when I pull the plug out of the holder, making it smooth to plug it into the car with the door already open. For this use I do not use a battery.

Using a push button to power it on, it can be battery powered and last virtually forever.

## How it works

This sketch will when powered on send a radio signal that will open the charge door of a Tesla car. After sending this signal at power-on, it will do nothing. This is meant for battery powered operation using a push button. You can of course change it to be always on and trigger on something else.

Pin 11 must be connected to the signal pin of an ASK STX882 433.92MHz transmitter that can be bought on eBay for a low price.

Normally, a transmitter should not be used without an antenna, but I have used the STX882 without one without problems for this project to keep the range very short to avoid opening the charge door of other cars nearby. The transmit times are so short it is unlikely to cause problems.

The message that is sent has been grabbed by using an SRX882 receiver to pick up the data sent by a Tesla charging cable with built in push button. The signal will be sent 5 times repeatedly, just like the charge cable button does.

The cable uses this signal to open the charge door when pushing the button while not being plugged in to the car. The car must be unlocked or you must be in bluetooth range with your paired phone.

When plugged in, the button of the cable can unlock the cable from the car too. This is not done by RF but through wires in the cable, so this sketch will not unlock the cable when plugged in.

