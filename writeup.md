#  Helen Ton - Lab 2 Write Up 
### _____________________________________________________________________

### My Expereince with the Project
- Overall, I thought this project taught me a lot about ROM hacking, virtual machines, and emulators. It also helped me realize that a lot of tools are online and easy to find. 

- For this project, I used Tile Layer Pro to edit the tiles for the Mario and Princess Peach sprites. I originally tried using Mesen but realized that a graphics editor would
be much more efficient. The first editor I tried was YY-CHR but the tiles were all compressed and not boxed properly so I switched to Tile Layer Pro.

- To change the text on the title page to my name, I used HxD hex editor. I used the memory viewer and tile viewer on Mesen as a reference to determine which hex values to change. I found that the starting offset for sprite tiles is 0x8010 on HxD by using the find tool to locate hex value patterns. 

- Lastly, I used Lunar IPS to create an ips patch file as reccommended by the professor. 

- Almost all of the applications I downloaded for this project are for WindowsOS. Since I am working from my MacBook, I used UTM to create a virtual machine for Windows. I downloaded Tile Layer Pro, HxD, and Lunar IPS there, and installed Mesen on my Mac. I used the network drive to share project files. I used this method because having Mesen on MacOS made testing the game a lot smoother and faster. 

### _____________________________________________________________________
### Changes made to the MARIO sprites
### =============================================================
** Super Mario Walk 1 ** 
- Offset ```0x8010```: (*"Mario's top left head"*):
    - Original hex values: ```03 0F 1F 1F 1C 24 26 66 00 00 00 00 1F 3F 3F 7F```
    - NEW hex values:      ```00 01 03 07 0F 0F 0E 0C 00 01 03 07 0F 0F 3F 3F``` 

- Offset ```0x8020```: (*"Mario's top right head"*):
    - Original hex values: ```E0 C0 80 FC 80 C0 00 20 00 20 60 00 F0 FC FE FE```
    - NEW hex values:      ```00 C0 F8 FC FE FF 7F 1F 00 C0 F8 FC FE FF FF FF``` 

- Offset ```0x8030```: (*"Mario's bottom left head"*):
    - Original hex values: ```60 70 18 07 0F 1F 3F 7F 7F 7F 1F 07 00 1E 3F 7F ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00``` 

- Offset ```0x8040```: (*"Mario's bottom right head"*):
    - Original hex values: ```FC 7C 00 00 E0 F0 F8 F8 FC FC F8 C0 C2 67 2F 37 ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C2 83 07 ``` 

- Offset ```0x8050```: (*"Mario's left body"*):
    - Original hex values: ```7F 7F FF FF 07 07 0F 0F 7F 7E FC F0 F8 F8 F0 70 ```
    - NEW hex values:      ```7F 7F FF FF 07 07 0F 0F 61 70 F0 F0 F8 F8 F0 70 ```  

I kept the original bottom half of mario since it worked well with my sprite. 
The hex values for offsets ```0x8060```, ```0x8070``` and ```0x8080``` which 
correspond to Mario's right body, left foot, and right foot respectively, 
did not change. 

### _____________________________________________________________________
** Super Mario Walk 2** 
- Offset ```0x8090```: (*"Mario's top left head"*):
    - Original hex values: ```00 00 01 07 0F 0F 0E 12 00 00 00 00 00 00 0F 1F ```
    - NEW hex values:      ```00 01 03 07 0F 0F 0E 0C 00 01 03 07 0F 0F 3F 3F ```  

- Offset ```0x80A0```: (*"Mario's top right head"*):
    - Original hex values: ```00 00 F0 E0 C0 FE 40 60 00 00 00 10 30 00 F8 FE ```
    - NEW hex values:      ```00 C0 F8 FC FE FF 7F 1F 00 C0 F8 FC FE FF FF FF ```  

- Offset ```0x80B0```: ("Mario's bottom left head"*):
    - Original hex values: ```13 33 30 18 04 0F 1F 1F 1F 3F 3F 1F 07 08 17 17 ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00``` 

- Offset ```0x80C0```: (*"Mario's bottom right head"*):
    - Original hex values: ```00 10 7E 3E 00 00 C0 E0 FF FF FE FE FC E0 40 A0 ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C0 80 00 ``` 

- Offset ```0x80D0```: ("Mario's left body"*):
    - Original hex values: ```3F 3F 3F 1F 1F 1F 1F 1F 37 27 23 03 01 00 00 00 ```
    - NEW hex values:      ```3F 3F 3F 1F 1F 1F 1F 1F 00 00 00 00 00 00 00 00 ```

- Offset ```0x80E0```: (*"Mario's right body"*):
    - Original hex values: ```F0 F0 F0 F8 F8 F8 F8 F8 CC FF FF FF FF 70 00 08 ```
    - NEW hex values:      ```F0 F0 F0 F8 F8 F8 F8 F8 0C 0F 0F 07 07 00 00 00 ```

I didn't change the hex values for Offsets ```0x80F0``` and ```0x8100``` which contain 
(Super Mario Walk 1 - *"Mario's left and right foot"*)

### _____________________________________________________________________
** Super Mario Walk 3 ** 
- Offset ```0x8110```: (*"Mario's top left head"*):
    - Original hex values: ```00 03 0F 1F 1F 1C 24 26 00 00 00 00 00 1F 3F 3F ```
    - NEW hex values:      ```00 01 03 07 0F 0F 0E 0C 00 01 03 07 0F 0F 3F 3F ```  

- Offset ```0x8120```: (*"Mario's top right head"*):
    - Original hex values: ```00 E0 C0 80 FC 80 C0 00 00 00 20 60 00 F0 FC FE ```
    - NEW hex values:      ```00 C0 F8 FF FF FF 7F 1F 00 CF FF FC FE FF FF FF ```  

- Offset ```0x8130```: (*"Mario's bottom left head"*):
    - Original hex values: ```66 60 30 18 0F 1F 3F 3F 7F 7F 3F 1F 00 16 2F 2F ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00 ```  

- Offset ```0x8140```: (*"Mario's bottom right head"*):
    - Original hex values: ```20 FC 7C 00 00 E0 E0 F0 FE FC FC F8 C0 60 20 30 ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C0 80 00 ```  

- Offset ```0x8150```: (*"Mario's left body"*):
    - Original hex values: ```3F 3F 3F 3F 3F 3F 3F 1F 2F 2F 2F 0F 07 03 00 00 ```
    - NEW hex values:      ```3F 3F 3F 3F 3F 3F 3F 1F 2F 23 20 00 00 00 00 00 ```  

I didn't change the hex values for Offsets ```0x8160```, ```0x8170```, and ```0x8180```  which contain (*"Mario's right body, left foot, and right foot"*)

### _____________________________________________________________________
** Super Mario Twist ** 
- Offset ```0x8190```: ("Mario's top left head"*):
    - Original hex values: ```03 3F 7F 19 09 09 28 5C 00 30 70 7F FF FF F7 F3 ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00 ```  

- Offset ```0x81A0```: (*"Mario's top right head"*):
    - Original hex values: ```F8 E0 E0 FC 26 30 80 10 00 18 10 00 F8 F8 FE FF ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C0 80 00 ```  

I didn't change the hex values for Offsets ```0x81B0```. ```0x81C0```, ```0x81D0```, ```0x81E0```, ```0x81F0```, and ```0x8200``` which contain (*Mario's top left body, top right body, bottom left body, bottom right body, left foot, and right foot*)

### _____________________________________________________________________
** Super Mario Jump ** 
- Offset ```0x8210```: (*"Mario's top left head"*):
    - Original hex values: ```00 00 03 0F 1F 1F 1C 24 00 00 00 00 00 00 1F 3F ```
    - NEW hex values:      ```00 01 03 07 0F 0F 0E 0C 00 01 03 07 0F 0F 3F 3F ```  

- Offset ```0x8220```: (*"Mario's top right head"*):
    - Original hex values: ```00 04 E6 E0 FF FF 8F 83 0E 1F 1F 1F 1F 03 FF FF ```
    - NEW hex values:      ```00 C0 F8 FC FE FF 7F 1F 00 C0 F8 FC FE FF FF FF ```  

- Offset ```0x8230```: (*"Mario's bottom left head"*):
    - Original hex values: ```26 26 60 78 18 0F 7F FF 3F 3F 7F 7F 1F 00 7E FF ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00 ```  

- Offset ```0x8240```: (*"Mario's bottom right head"*):
    - Original hex values: ```01 21 FE 7A 06 FE FC FC FF FF FE FE FE DE 5C 6C ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C0 80 00 ```  

I didn't change the hex values for Offsets ```0x8250```. ```0x8260```, ```0x8270```, and ```0x8280``` which contain (*Mario's left body, right body, left foot, and right foot*) 

### _____________________________________________________________________
** Super Mario Swim 1 ** 
- Offset ```0x8290```: (*"Mario's top left head"*):
    - Original hex values: ```13 33 30 18 04 0F 1F 1F 1F 3F 3F 1F 07 09 13 17 ```
    - NEW hex values:      ```19 39 38 1C 06 0C 1E 1F 1F 3F 3F 1F 07 03 01 00 ```  

- Offset ```0x82A0```: (*"Mario's top right head"*):
    - Original hex values: ```00 10 7E 30 E0 F0 F0 E0 FF FF FE FF FE FC F8 E0 ```
    - NEW hex values:      ```43 47 8E 8E 1C 30 70 F8 FF FF 7E 7E FC C0 83 07 ```  

I kept the rest of the body the same for Super Mario Swim. The hex values did not change for offsets ```0x82B0``` to ```0x8320```

### _____________________________________________________________________
** Mario Walk 1 ** 
- Offset ```0x8330```: (*"Mario's left head"*):
    - Original hex values: ```00 03 07 07 0A 0B 0C 00 00 00 00 07 0F 0F 0F 03 ```
    - NEW hex values:      ```17 2F 18 38 12 10 31 38 07 07 0F 3F 3F 3F 3E 3F ``` 

- Offset ```0x8340```: (*"Mario's right head"*):
    - Original hex values: ```00 E0 FC 20 20 10 3C 00 00 00 00 F0 FC FE FC F8 ```
    - NEW hex values:      ```D0 E8 38 38 5C 08 88 38 C0 C0 E8 F8 FC F8 78 F8 ``` 

- Offset ```0x8350```: (*"Mario's left body"*):
    - Original hex values: ```07 07 07 1F 1F 3E 21 01 07 0F 1B 18 10 30 21 01 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x8360```: (*"Mario's right body"*):
    - Original hex values: ```E0 E0 E0 F0 F0 E0 C0 E0 A8 FC F8 00 00 00 C0 E0 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

### _____________________________________________________________________
** Mario Walk 2 ** 
- Offset ```0x8370```: (*"Mario's left head"*):
    - Original hex values: ```07 0F 0E 14 16 18 00 3F 00 00 0F 1F 1F 1F 07 3C ```
    - NEW hex values:      ```17 2F 18 38 12 10 31 38 07 07 0F 3F 3F 3F 3E 3F ``` 

- Offset ```0x8380```: (*"Mario's right head"*):
    - Original hex values: ```C0 F8 40 40 20 78 00 C0 00 00 E0 F8 FC F8 F0 C0 ```
    - NEW hex values:      ```D0 E8 38 38 5C 08 88 38 C0 C0 E8 F8 FC F8 78 F8 ``` 

- Offset ```0x8390```: (*"Mario's left body"*):
    - Original hex values: ```3F 0E 0F 1F 3F 7C 70 38 FC ED C0 00 00 60 70 38 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x83A0```: (*"Mario's right body"*):
    - Original hex values: ```F0 F8 E4 FC FC 7C 00 00 7E 1E 04 0C 0C 0C 00 00 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

### _____________________________________________________________________
** Mario Walk 3 ** 
- Offset ```0x83B0```: (*"Mario's face from walk 2"*):
    - Original hex values: ```07 0F 0E 14 16 18 00 0F 00 00 0F 1F 1F 1F 07 0D ```
    - NEW hex values:      ```17 2F 18 38 12 10 31 38 07 07 0F 3F 3F 3F 3E 3F ``` 

- Offset ```0x83C0```: (*"Mario's left body"*):
    - Original hex values: ```1F 1F 1F 1C 0C 07 07 07 1E 1C 1E 0F 07 00 07 07 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x83D0```: (*"Mario's right body"*):
    - Original hex values: ```E0 60 F0 70 E0 E0 F0 80 60 90 00 80 00 E0 F0 80 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

### _____________________________________________________________________
** Mario Twist ** 
- Offset ```0x83E0```: (*"Mario's left head"*):
    - Original hex values: ```07 1F 3F 12 13 08 1F 31 00 10 3F 7F 7F 3F 03 0F ```
    - NEW hex values:      ```17 2F 18 38 12 10 31 38 07 07 0F 3F 3F 3F 3E 3F ``` 

- Offset ```0x83F0```: (*"Mario's right head"*):
    - Original hex values: ```C0 F0 40 00 30 18 C0 F8 00 00 E0 F8 FC F8 B0 38 ```
    - NEW hex values:      ```D0 E8 38 38 5C 08 88 38 C0 C0 E8 F8 FC F8 78 F8 ``` 

I didn't change the hex values for Offsets ```0x8400``` and ```0x8410``` which contain (*Mario's left and right foot*) 

### _____________________________________________________________________
** Mario Jump, Mario Swim, Mario Grow, and Mario Stand ** 
- Offset ```0x8420```: (*"Mario's head from walk 1"*):
    - Original hex values: ```00 E0 FC 27 27 11 3E 04 07 07 03 F7 FF FF FE FC ```
    - NEW hex values:      ```D0 E8 38 38 5F 0F 8C 38 C0 C3 EB FF FC F8 78 F8 ``` 

- Offset ```0x8430```: (*"Mario's left body"*):
    - Original hex values: ```3F 7F 3F 0F 1F 3F 7F 4F 3E 7F FF E2 50 38 70 40 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x8440```: (*"Mario's right body"*):
    - Original hex values: ```F8 F9 F9 B7 FF FF E0 00 E8 71 01 4B 03 03 00 00 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

- Offset ```0x8450```: (*"Mario's left body "*):
    - Original hex values: ```07 07 0F 3F 3F 3F 26 04 05 03 01 30 30 30 26 04 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x8460```: (*"Mario's right body"*):
    - Original hex values: ```F0 F0 F0 E0 C0 00 00 00 FE FC E0 00 00 00 00 00 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

- Offset ```0x8470```: (*"Mario's left body"*):
    - Original hex values: ```07 07 0F 1F 3F 0F 1C 18 05 03 01 10 30 0C 1C 18 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x8480```: (*"Mario's right body"*):
    - Original hex values: ```E0 E0 E0 E0 C0 80 00 00 C0 E0 F0 78 18 08 00 00 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

- Offset ```0x8490```: (*"Mario's left body"*):
    - Original hex values: ```07 0F 1F 0F 3F 0F 1C 18 07 0F 3E 7C 30 0C 1C 18 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x84A0```: (*"Mario's right body"*):
    - Original hex values: ```E0 E0 E0 40 C0 80 00 00 60 60 60 80 00 00 00 00 ```
    - NEW hex values:      ```30 38 64 EC EC 0C 00 00 FE DE 84 0C 0C 0C 00 00 ``` 

- Offset ```0x84B0```: (*"Mario's body"*):
    - Original hex values: ```7F FF FF FB 0F 0F 0F 1F 73 F3 F0 F4 F0 F0 70 60 ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x84C0```: (*"Mario's standing body"*):
    - Original hex values: ```3F 7E 7C 7C 3C 3C FC FC 00 00 00 00 3C 3C FC FC ```
    - NEW hex values:      ```3F 7F 7F FF 3C 3C FC FC 00 00 00 00 3C 3C FC FC ``` 

- Offset ```0x84D0```: (*"Mario's left head"*):
    - Original hex values: ```60 70 18 08 0F 1F 3F 7F 7F 7F 1F 07 0B 1B 3B 7B ```
    - NEW hex values:      ```60 71 38 3C 0C 1E 3F 7F 7F 7E 3F 3F 03 01 00 00 ``` 

- Offset ```0x84E0```: (*"Mario's right head"*):
    - Original hex values: ```FC 7C 00 20 F0 F8 FC FE FC FC F8 E0 D0 D8 DC DE ```
    - NEW hex values:      ```0C 9C 1C 38 30 78 FC FE FC 7C FC F8 C0 80 00 00 ``` 

- Offset ```0x84F0```: (*"Mario's body"*):
    - Original hex values: ```0B 0F 1F 1E 3C 3C 3C 7C C4 E0 E0 40 00 3C 3C 7C ```
    - NEW hex values:      ```3C 0C 0E 1F 0F 60 70 38 FB E3 C1 00 00 60 70 38 ``` 

- Offset ```0x8500```: (*"Mario's standing body"*):
    - Original hex values: ```1F 3F 0D 07 0F 0E 1C 3C 1D 3C 3A 38 30 00 1C 3C ```
    - NEW hex values:      ```1C 3C 0E 0F 1F 3F 1C 3C 1B 3B 31 30 20 00 1C 3C ``` 

### _____________________________________________________________________
** Mario Loss ** 
- Offset ```0x89F0```: (*"Mario head"*):
    - Original hex values: ```03 07 0A 1A 1C 1E 0B 08 00 10 7F 7F 7F 1F 0F 0F ```
    - NEW hex values:      ```17 2F 18 38 12 10 31 38 07 07 4F FF FF FF 3E 3F ``` 

- Offset ```0x8A00```: (*"Mario body"*):
    - Original hex values: ```1C 3F 3F 3D 3F 1F 00 00 03 33 39 3A 38 18 00 00 ```
    - NEW hex values:      ```1C 3E 3F 7F 7F 7F 00 00 03 21 20 70 70 70 00 00 ```

### _____________________________________________________________________

### Changes made to PRINCESS PEACH 
### =============================================================
** Princess Peach ** 
- Offset ```0x87B0```: (*"Princess Peach's left head"*):
    - Original hex values: ```16 1F 3F 7F 3D 1D 3F 1F 16 1F 00 00 05 0D 3F 1F ```
    - NEW hex values:      ```00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ``` 

- Offset ```0x87C0```: (*"Princess Peach's right head "*):
    - Original hex values: ```80 80 C0 E0 F0 F0 F0 F8 80 80 00 00 00 A0 A0 E0 ```
    - NEW hex values:      ```00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ``` 

- Offset ```0x8D90```: (*"Princess Peach's ballgown skirt"*):
    - Original hex values: ```0C 00 00 00 07 7F 7C 00 03 1F 3F 3F 78 00 03 FF ```
    - NEW hex values:      ```1F 3F 0D 07 0F 0E 1C 3C 1D 3C 3A 38 30 00 1C 3C ``` 

- Offset ```0x8DB0```: (*"Princess Peach's left body"*):
    - Original hex values: ```3F 3F 1F 1B 36 30 7F 3F 23 27 1F 07 0F 1F 7F 3F ```
    - NEW hex values:      ```03 1F 02 02 04 1E 00 03 00 00 07 1F 3F 1F 0F 03 ``` 

- Offset ```0x8DC0```: (*"Princess Peach's right body"*):
    - Original hex values: ```F8 F8 F8 B8 18 D8 D8 B8 E0 80 80 40 E0 E0 E0 C0 ```
    - NEW hex values:      ```E0 F0 70 28 68 18 00 FC 00 00 F0 F8 F8 F8 E0 3C ``` 

### Changes made to TITLE SCREEN TEXT
### =============================================================
** Title Screen Text ** 
- Offset ```0x9FC0```: (*"1 Player Game" --> "Hacker Helen"*):
    - Original hex values: ```17 0D 18 22 4B 0D 01 24 19 15 0A 22 0E 1B 24 10 ```
    - NEW hex values:      ```17 0D 18 22 4B 0D 11 0A 0C 14 0E 1B 24 11 0E 15 ``` 