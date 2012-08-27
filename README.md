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
is almost no delay between pressing a key and hearing a sound. Every
note you here is a process fork.



Requirements
============

You will need to make sure you have three things to use keyjam. Well, four actually.

1) Unix, probably Linux would work best since that's where the development is done.
2) Working sound (Duh!)
3) Perl's Term::ReadKey module.
4) sox play command

You can install the last two on Debian with the following command

 apt-get install sox libterm-readkey-perl


Usage
=====

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

To quit keyjam, press <Esc>.

Here are some other keys that can be used to control keyjam:

 - <PgUp>, <PgDown> - Change octave
 - <F1>, <F2> - Change instrument (up/down)
 - <F11>, <F12> - Change detune range effect. (up/down)


Development
===========

If you want to change the key mappings, you can define a new one in
the program itself, just search for the line, "my %notes_keymaps"
and you'll see where you can define your own mapping. Mapping is done
by listing the keys that correspond to each note on a twelve tone scale
in the western tonality system. Spaces used in the mapping string are ignored
and stripped. You can map additional octaves onto your keymap by continuing
on after you reach the 12th note. You will need to prefix the following octave
with an underscore character. keyjam will detect this automatically and
setup the next octave automatically. You can also skip mappings of certain
notes by using an underscore character(_)


License
=======

keyjam is distributed under the terms of the GNU General Public License version 3.
Please see the file COPYING included with the software.

Contact
=======

You may contact the author Mark Krenz at deltaray _ slugbug + org (tr _+ @.)

