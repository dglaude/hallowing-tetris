# hallowing-tetris
Tetris game for the Adafruit Hallowing made by deshipu

## Description / Analyse

The hallowing is a Feather ( https://learn.adafruit.com/adafruit-hallowing/pinouts ) with:
* TFT 128*128 pixels
* 4 touch pin: A2 to A5
* speaker
* ...

This game only require 4 touch pin and works on a very small display (16*20) with only six colour in the palette:
    screen = displayio.Bitmap(16, 20, 6)
    grid = displayio.TileGrid(screen, pixel_shader=palette, x=0, y=-4)

To fill the screen, a scaling x8 is applied
    root = displayio.Group(scale=8)

16*8 = 128
20*8 = 160
y=-4 ???

The game also has a wave file that run in loop.

## Reuse

This is a simple game that has very simple requirement and can work on small or big screen.

This is ideal for testing the use of with Quico https://retro.moe/2020/12/31/building-quico-improved-sound-and-more-part-iii/

Plan is to try using this on
  (1) Matrix Portal M4 + Joystick
  (2) PyPortal + Joystic

Replace touch pin by some abstract joystick library (the goal is to use Bluepad32 https://retro.moe/2020/11/24/bluepad32-gamepad-support-for-esp32/ ).
Remove the audio part.
Try on simple hardware totally independant on (1) and (2).

