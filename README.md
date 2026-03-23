# sound-toggle-light-using-PUSH-BUTTON-
A light control project where sound input is stimulated using a pushbutton in wokwi to toggle an LED
# Button Toggle LED

## What it does
Toggles LED ON and OFF with single button press

## My Logic
- Boolean flag remembers LED state
- !ledState flips between true and false
- lastButtonState prevents multiple triggers

## What I learned
- Boolean toggle logic
- Button debouncing
- State management

## Live Simulation
"https://wokwi.com/projects/459294994010103809"

## Challenges I Faced
- Button was triggering multiple times when held
- Fixed using lastButtonState variable to detect 
  single press only
- Learned difference between INPUT_PULLUP 
  and INPUT_PULLDOWN

## What is INPUT_PULLUP?
Uses Arduino's internal pull up resistor
Default pin state = HIGH
Button pressed = LOW
No external resistor needed for button!
Button NOT pressed:
5V → Resistor → Pin 7 → Button OPEN → nothing
Pin 7 reads = HIGH ✅
LED stays in current state
Button PRESSED:
5V → Resistor → Pin 7 → Button CLOSED → GND
Current flows to ground!
Pin 7 reads = LOW ✅
LED toggles!

## How INPUT_PULLUP works in this project
WITHOUT PULLUP RESISTOR — button pin floats 
randomly causing false triggers.

with INPUT_PULLUP — pin stays HIGH by default.
When button pressed — pin connects to GND 
and reads LOW.
This is why we check:
if (buttonState == LOW) → button is pressed

This is why we check:
if (buttonState == LOW) →
