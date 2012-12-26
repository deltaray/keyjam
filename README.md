keyjam
======

keyjam is a simple synthesis tool that allows you to use your computer's keyboard to play and control from a terminal window

Description
===========

This is a synthesizer you can use with your computer keyboard. Its
basically a frontend to the sox play command, which produces the
actual sythesized sounds you hear.

Because of its design and difficulties in doing things, it lacks
(and may never have) certain abilities, like being able to sustain
notes until you release the keys and the number of notes you can
trigger at the same time is limited to your keyboard drivers, which
probably only allow 3 key presses to be registered at once.

Its more of a novelty. But its fun to play with so I thought I'd
release it. Surprisingly, the play command is pretty fast so there
is almost no delay between pressing a key and hearing a sound.
Process forks never sounded so good.


Requirements
============

You will need to make sure you have four things to use keyjam. Well, four actually.

*   Unix, probably Linux would work best since that's where the development is done.
*   Working sound (Of course!)
*   Perl's Term::ReadKey module.
*   sox play command

You can install the last two on Debian with the following command

 `apt-get install sox libterm-readkey-perl`


Usage
=====

To quit keyjam, press `<Esc>`.

Note: If you're not using a qwerty mapped keyboard, you're going to have to do
some work to get this to work properly. A future version will try to detect your
keyboard layout.

By default, the home row and top row letter keys are used in a piano style way
to play the notes. Below is an example of what keys on a qwerty keyboard map
to which piano keys. The note name is shown below the mapped key in parentheses.
  
    _____________________________
    |  | | | |  |  | | | | | |  |
    |  | | | |  |  | | | | | |  |
    |  |w| |e|  |  |t| |y| |u|  |
    |  |_| |_|  |  |_| |_| |_|  |
    | a | s | d | f | g | h | j |
    |(C)|(D)|(E)|(F)|(G)|(A)|(B)|
    |___|___|___|___|___|___|___|

You can print the current keyboard mapping using `<F1>` or `?`.

Here are some other keys that can be used to control keyjam:

*   `<PgDown>`, `<PgUp>` - Change octave (down/up)
*   `<F3>`, `<F4>` - Change instrument (down/up)
*   `<F11>`, `<F12>` - Change detune range effect. (down/up)


Demos
=====

It would be great to see people demostrating keyjam in online videos
or something like that. Please e-mail at the contact address below if
you'd like to share yours and I'll include it here.

Development
===========

If you want to change the key mappings, you can define a new one in
the program itself, just search for the line, `my %notes_keymaps`
and you'll see where you can define your own mapping. Mapping is done
by listing the keys that correspond to each note on a twelve tone scale
in the western tonality system. Spaces used in the mapping string are ignored
and stripped. You can map additional octaves onto your keymap by continuing
on after you reach the 12th note. You will need to prefix the following octave
with an underscore character. keyjam will detect this automatically and
setup the next octave automatically. You can also skip mappings of certain
notes by using an underscore character(`_`).

In the future I may turn this into more of a curses like program that always
displays the keyboard and current settings.


License
=======

keyjam is distributed under the terms of the GNU General Public License version 3.
Please see the file COPYING included with the software.

Contact
=======

You may contact the author Mark Krenz at deltaray _ slugbug + org (`tr _+ @.`)

