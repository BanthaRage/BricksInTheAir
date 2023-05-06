# Documentation for ICDs/SDDs and Datasheets

## Background documents

[Lego Power Functions](./LEGO_Power_Functions_RC_v120.pdf) : Background
documentation on how the lego power function controllers work.  

## Project documentation

[FlySafe Developer Documentation](./FlySafe_Developers_Documentation.docx): This
 is the document that guides individuals through the assignment.  


## Tailoring

For a given Lego kit setup it is necessary to configure and custom load each of
the individual microcontrollers to the parameters of the Lego kit. For instance
the time it takes to raise the landing gear may be different than the time to
lower the gear and each of those variables would be specific to that kit. It is
recommended to determine those parameters with a fresh set of batteries.


## Initial Setup

The computer provided for the participant (i.e. Raspberry Pi) should be
configured with the following:

```
# edit the ~/.bash_aliases
alias buspirate='picocom -b 115200 --ompa delbs /dev/ttyUSB0'
```

That will make a shortcut to open the buspirate with the correct parameters
specifically the correct baud rate, mapping of the delete and backspace keys for
normal humans and connect to the appropriate USB device of the buspirate.

Also, consider enlarging the Terminal app font and window size as this will
be the only window that participants will be using. Filling the screen with a
font sufficiently easy to read helps everyone.

### Troubleshooting

If running the alias doesn't work ensure that the /dev/ttyUSB0 mapping is correct.
Begin with the buspirate disconnected and type in the terminal

```
ls /dev/tty*
```

Then plug in the buspirate via USB and rerun the same command. Look for the
newly connected USB device and plug that path into the alias


## Setup

With everything above completed and ready to go it's time to set it all up and
allow participants to play. A few last things to be all ready. Plug everything in
and turn it all on.

  1. Open a terminal Window and type the configured alias from above "buspirate"
  2. This will open the buspirate interactive menu. To configure it type:
      1. Type 'm' to set the correct mode
      2. Type '4' to set I2C
      3. Type '3' to select '~100KHz'
      4. Type 'W' to turn ON the 5V power rails
          - Press the momentary power switch button to power the Bricks in the Air
      Board. Verify by ensuring the LEDs on that board are illuminated.
      5. Type '(1)' to run the 7bit address search macro. This will list all the
    connected I2C devices and you should see 3 available. Now you're all set

After somone completes a challenge it's often useful and easiest to "reset" the
Bricks in the Air board by pressing the momentary power switch button twice
to power off then back on the board in effect reseting it. When doing this however
ensure that the Lego kit matches the initial state with the Lego Remote Control.

### Troubleshooting

Bricks in the Air board isn't powered.

  - Ensure the 5V power rails on the buspirate are ON via the step listed above.
  - Press the momentary power switch button to reset the board.
