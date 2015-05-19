About
=====

In [blink_led](/led_blink), we learnt how to hook up and LED to a resistor and make it blink with some example code. Your project would probably require some user interface and the classic method is to have a button dedicated for a certain task. 

eg. Turn on/off my desk lamp when a button is pressed or order a pizza by hitting a huge button!

**Items required:**
 - 1k Ohm Resistor
 - Mini Pushbuttons
 - Tinker App or Cloud IDE

**Schematic diagram:**

![Example LED](images/ex-button.png)

**Hands-on Activity:**

When you run the [firmware example](firmware) provided, LED on D0 or D7 will light up accordingly.

 In example code:
      
  1. Change the `HIGH` in if(digitalRead(inputpin) == HIGH) to `LOW`
  2. You will notice that the led lights up by default and turns off only when you press it!
  3. We will now 'count' the number of times the button is pressed and change the blinking speed of the LED accordingly
  
  eg. Vary LED blink speed using button

```
bool ledstatus = LOW;

void loop() {
 	if(digitalRead(inputpin) == HIGH){   //check if button is pressed
 	    ledstatus = !ledstatus;
 	    delay(300); //wait awhile for user to release button
 	}
 	
	digitalWrite(led, ledstatus);    // Turn On/OFF depending on button pressed
        digitalWrite(led2, ledstatus); 
}
```

Here's a little secret (~shhh)....If you are playful and decided not to release the pushbutton, the LED ends up blinking. How cool is that?! 2 in 1 function! ;)
       
 In hardware:  
      
   1. Reverse the connection with one side to Ground --> Pushbutton leg 1, Pushbutton leg 2 --> Resistor --> +3.3v
   2. This way, the readings will be HIGH when the Pushbutton is left untouched and changes to LOW when pressed.
