# Digispark101
A very simple cheatsheet to get started with a Digispark (ATtiny85 microcontrolller).

## Requirements
First, download the [Arduino IDE](https://www.arduino.cc/en/main/software) and follow the instructions [on there](https://digistump.com/wiki/digispark/tutorials/connecting) to set it up correctly.

Then you will need this [encoder.jar](https://github.com/hak5darren/USB-Rubber-Ducky/blob/master/Encoder/encoder.jar) file, to convert your ducky script into a payload.

Finally, clone the [duck2spark](https://github.com/mame82/duck2spark.git) repository to convert the payload into an arduino sketch.

## Getting started

Once you have all the requirements installed, create a [.duck file](wallpaper.duck) and write your ducky script inside of it.

---

Then convert the ducky script into a .bin payload by entering the following command :

`java -jar encoder.jar -i myscript.duck -o myscript.bin -l en`
> Dont forget to replace `myscript.duck` and `myscript.bin` by the name of your script

> The  `-l en` flag is specifying the keyboard layout of the payload, change it according to the target's keyboard layout.

---

Next, use duck2spark to turn your .bin payload into an arduino sketch, by issuing this command : 

`python duck2spark.py -i myscript.bin -l 1 -o myscript.ino`

---

Now, open Arduino IDE and open the .ino sketch you just created.

Click *Upload* and plug-in your Digispark.

Enjoy !
