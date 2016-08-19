# ROP

It is possible to specify ROP file name with HTTP GET parameter, like:

http://Madridi7.github.io/ROP/rop?MemoryDump.dat

It is also possible to patch filename or binary data inside ROP data:

http://Madridi7.github.io/ROP/rop?MemoryDump.dat&memdump.bin

in this case dmc:/memody.bin will be changed to dmc:/memdump.bin

The patching parameter may be one one of the following:

1. HEX (string with only 0-9,a-f,A-F characters used) - patch data bytes at offset 0x220 with this data

2. string (not HEX) - patch first filename found by "dmc:/" prefix (original string in ROP must be aligned to 2 bytes to be found)

3. HEX=HEX same as 1. but offset is specified before "="

4. HEX=string - patch string data bytes at offset specified before "=" character (offset will be alignet to 2 bytes)


ROP files available at the server:

# [MemoryDump]

MemoryDump.dat

2nd string parameter substitutes default memory.bin


# [LoadROP]

LoadROP.dat - for 1.7567 browser (fw 7.1+) E/J/U (C/K/T?) regions

LoadROP5.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U (C/K/T?) regions

LoadROP4.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions

2nd parameter substitutes default ROP.dat


# [LoadCode]

LoadCode.dat - for 1.7567 browser (fw 7.1+) E/J/U (C/K/T?) regions

LoadCode5.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U (C/K/T?) regions

LoadCode4.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions

2nd string parameter substitutes default code.bin


# [RegionThree]

RegionThree.dat - for 1.7567 browser (fw 7.1+) E/J/U (C/K/T?) regions

RegionThree5.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U (C/K/T?) regions

RegionThree4.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions

No parameters required


# [Gateway Launcher]

GW17567.dat - for 1.7567 browser (fw 7.1+) E/J/U regions

GW17567C.dat - for 1.7567 browser (fw 7.1+) C region

GW17567K.dat - for 1.7567 browser (fw 7.1+) K region

GW17567T.dat - for 1.7567 browser (fw 7.1+) T region

GW17552.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U regions

GW17552C.dat - for 1.7552 browser (fw 5.0-7.0) C region

GW17552K.dat - for 1.7552 browser (fw 5.0-7.0) K region

GW17552T.dat - for 1.7552 browser (fw 5.0-7.0) T region

GW17538K.dat - for 1.7538 browser (fw 4.x) K region

GW17538T.dat - for 1.7538 browser (fw 4.x) T region

GW17498.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions

GW17455.dat - for 1.7455 browser (fw 2.1) E/J/U (C/K/T?) regions

GW17412.dat - for 1.7455 browser (fw 2.0) E/J/U (C/K/T?) regions

GW17567O.dat - for 1.7567 browser (fw 7.1+) E/J/U regions (old version)

GW17552O.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U regions (old version)

GW17498O.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions (old version)

GW17455O.dat - for 1.7455 browser (fw 2.1) E/J/U (C/K/T?) regions (old version)

GW17412O.dat - for 1.7455 browser (fw 2.0) E/J/U (C/K/T?) regions (old version)

2nd string parameter substitutes default Launcher.dat


# [DownloadCode]

DownloadCode.dat - for 1.7567 browser (fw 7.1+) E/J/U (C/K/T?) regions

DownloadCode5.dat - for 1.7552 browser (fw 5.0-7.0) E/J/U (C/K/T?) regions

DownloadCode4.dat - for 1.7498 browser (fw 4.x) E/J/U (C/K/T?) regions

Special LoadCode version that requires code.bin data to be added to the end of the file and downloaded as one file with this ROP. 2nd parameter patches all ROP witn code.bin part.


# [Virtual Console ROM injector]

VC.dat

GBCRomSwap https://gbatemp.net/threads/injecting-roms-into-vc-with-only-the-web-browser-sure.379760/. DownloadCode based, i.e. have code.bin integrated and requires only GB/GBC rom file at SD card. 2nd parameter substitutes default rom.gbc, max filename with extension=25


# [Action Replay cheat code engine]

arcode.dat

Based on https://gbatemp.net/threads/spider-arcode.383937/, AR code patch offset is 0xE00, first 32-bit word is AR code lines count, then AR code data, macimum length is 27 lines. DownloadCode based, i.e. have code.bin integrated and do not require any files at SD card. Ex.: http://Madridi7.github.io/ROP/rop?arcode.dat&E00=0100000076543210FEDCBA98 equals to AR cheat 01234567 89ABCDEF. For the ease just use 3DS online tools that allows copy-paste cheat code in common format is and get link or QR code


# [FCRAM dumper]

memdump.dat

Based on https://gbatemp.net/threads/spider-arcode.383937/. 2nd parameter substitutes default FCRAM.bin, max filename with extension=10. DownloadCode based, i.e. have code.bin integrated and do not require any files at SD card. Ex.: http://Madridi7.github.io/ROP/rop?memdump.dat&memdump.bin


# [Animal Crossing: New Leaf RAM editor]

acnldump.dat - dump

acnlinjc.dat - inject

Based on Animal Crossing: New Leaf RAM editor https://gbatemp.net/threads/spider-animal-crossing-new-leaf-ram-editor.382965/. 2nd parameter substitutes default acnlram.bin. DownloadCode based, i.e. have code integrated and do not require acnldump.bin/acnlinjc.bin files at SD card


# [Spoof firmware]

spoof.dat

Based on Spoof firmware by motezazer

https://gbatemp.net/threads/how-to-spoof-firmware-to-access-eshop-and-more-on-new-3ds-and-old-3ds.386591/, DownloadCode based, i.e. have code.bin integrated and do not require any files at SD card. No parameters required


# Credits:

All of these ROP code files are taken from Dukesrg .. This is just my mirror of it
