Simple text editor
 
 
Sanos has a simple text editor. It is a text-mode application that runs with any VT-100 compliant console or terminal, like xterm, telnet, PuTTY, and the Linux console. While most other text-mode editors (e.g. vi, emacs, and nano) have custom key bindings, the Sanos text editor tries to follow the principle of least surprise by using the same key bindings as most GUI-based text editors like gedit and notepad. These key bindings should also be familiar to anyone who has used a web browsers. You navigate around in the text using the normal cursor control keys (up, down, left, right, home, end, pgup, pgdn) and text can be selected by holding down the shift key while navigating. The text editor has a clipboard and you can cut (Ctrl+X), copy (Ctrl+C), and paste (Ctrl+V) text. Other commands also use the standard key bindings for GUI applications, like Ctrl+O to open a file, Ctrl+S to save the file, and Ctrl+Q to quit the editor.
The Sanos text editor is a very simple editor. There is only one source file (edit.c) and it does not rely only any external components except the standard libraries. It is not as powerful as programmer's editors like emacs and vi, which can be used as complete programming IDEs, but it can be used as a rudimentary editor for editing text files. It doesn't need any install program. It just consists of a single executable binary, and it doesn't require any configuration files to work.
 
Using the text editor on Sanos
 
The text editor is part of the standard Sanos SDK distribution and can be found in /bin/edit.exe. The source is located in /usr/src/utils/edit and there is a Makefile to build it.
 
Using the text editor on Linux
 
The text editor can also be used on Linux. There is only one source file so you just download this and compile the text editor using GCC. It does not depend on any special libraries, so it should compile on most systems that have GCC installed. The -Os option is used to generate a small binary. On my Linux box the editor binary is 23,493 bytes.
wget http://www.jbox.dk/downloads/edit.c
gcc -o edit edit.c -Os
./edit edit.c
Use Ctrl-Q to exit the editor.
 
Editor Command Summary
 
<up>        Move one line up (*)         Ctrl+N  New editor
<down>      Move one line down (*)       Ctrl+O  Open file
<left>      Move one character left (*)  Ctrl+S  Save file
<right>     Move one character right (*) Ctrl+W  Close file
<pgup>      Move one page up (*)         Ctrl+Q  Quit
<pgdn>      Move one page down (*)       Ctrl+P  Pipe command
<home>      Move to start of line (*)    Ctrl+A  Select all
<end>       Move to end of line (*)      Ctrl+C  Copy selection to clipboard
Ctrl+<home> Move to start of file (*)    Ctrl+X  Cut selection to clipboard
Ctrl+<end>  Move to end of file (*)      Ctrl+V  Paste from clipboard
<backspace> Delete previous character    Ctrl+Z  Undo
<delete>    Delete current character     Ctrl+R  Redo
Ctrl+<tab>  Next editor                  Ctrl+F  Find text
<tab>       Indent selection             Ctrl+G  Find next
Shift+<tab> Unindent selection           Ctrl+L  Goto line
                                         F1      Help
(*) Extends selection if combined        F3      Navigate to file
    with Shift                           F5      Redraw screen
