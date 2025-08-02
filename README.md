[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/4R0Hg2yO)
# CECS 378 Lab: It'sa me, Mario! Or....IS IT???

## Assignment description

We're in the section of the class where we discuss malware, and what better way to practice all of the same skill-set of skills than to do some ROM hacking!

Recently, [Nintendo announced the Switch 2](https://en.wikipedia.org/wiki/Nintendo_Switch_2). While we all know that it won't be nearly as hardware-good as other consoles out there, there is one reason we all want it: Mario! (And Zelda, and Metroid, and...the exclusives, really).

So, let's revisit what made Nintendo the powerhouse game company that it is today: the original Super Mario Bros! 

Except...Mario is in trouble. And he needs YOUR help!

![Help me, Mario!](https://upload.wikimedia.org/wikipedia/en/8/8d/Super_Mario_Bros_Princess_Is_In_Another_Castle_Quote.png)

Which is why you will be inserting yourself into the original game and attempt to rescue him! Or, at least some pixilated 8-bit avatar of yourself (it doesn't really have to look like you at all). In this assignment, you will be tasked with changing the character sprite of Mario to something else. You can change it to anything you want, but it must be a sprite that you create yourself. You can use any image editing software you want to create the sprite, but it must be your own work.

You will have to grab an emulator for old NES-roms, and my #1 recommendation is Mesen. It's a great open-source emulator that has a lot of debugging tools that will help you with this assignment. [It can even do crazy things, like apply high-resolution graphics and music patches to old NES games and make them look modern](https://www.youtube.com/watch?v=ITkHnhLQh1E).

(Pro tip: Mesen also has a built-in hex editor. And image support. And a lot of other things that will make this assignment easier.)

|  OS        |  Emulator                                      |
|------------|------------------------------------------------|
| All OSes   |  [Mesen](https://github.com/SourMesen/Mesen2)  |

I also want you to create an *.ips file to apply your patch on my own, unmodified game. [You can find info on patching with this tutorial](https://fantasyanime.com/patching). This is the final step that most romhackers do to release their game on the Internet for others to enjoy!

I got a lot of my info (really, virtually everything for doing this assignment) from [ROMhacking.net](https://www.romhacking.net). I recommend you look at that site too, particularly the [*documents*](https://www.romhacking.net/documents) section.

Here are a few documents I found helpful:

- [6502 Instruction Summary](https://www.romhacking.net/documents/113)
- [NES Palette hacking: The Fast way](https://www.romhacking.net/documents/145)

Plus, of course, a healthy dose of knowledge from classes like CECS 341 or similar architecture class. You will also need to tinker with this assignment: get creative; try things; make an early copy of your ROM file and don't worry about messing it up; experiment; play around with this. Many hackers learn more from *play* than work.

## Some obvious things that shouldn't need to be said, but have to be right now

1. **Don't apply any patches or third-party code to your ROM file** other than the code *you* write. A simple run of a `diff` program will easily tell me which pieces have been changed and which haven't and your `.ips` file will also tell me more.
2. **Do your own work**. Cheating and plagiarism are at all time highs in our department and we are being extra watchful right now.
3. **Come to me if you need help**. Really. I'm surprised people don't do this *more*. There are some things that I won't be able tell you about, but quite a bit that I can.
4. **Have fun with this assignment**. It's *supposed* to be fun. Hard, yes. But the best puzzles are always the hardest ones ;-).

## Deliverables

Here is what I will need from you:

1. Your modified, runnable (in working order) `Super Mario Bros. (World).nes` file (you may rename the file for your own, new game) which will include:
   - Your new character sprite in place of Mario!
   - Mario in place of Princess Peach (at the end of the game)! He needs rescuing!
   - Your name as hacking credits in the game code, preferably displayed when the game runs on the title screen. Something we can see when we run the game.
2. An `ips` patch file that will change the original `Super Mario Bros. (World).nes` file to your modified one. This will be done with a program like [Lunar IPS](https://www.romhacking.net/utilities/240/). When applying the patch, it *must* result in the exact same file as the modified one you submit.
3. At least one screenshot of the game, with your new character in front of a unique background within the game (something not everyone else is going to have like the first screen in the game). Something to show that you did the work.
4. A write up with *at a minimum* the following information:
    - The offsets of the RAM locations changed, what the value was, and what the new value is (in hex format, i.e. `0x66:0x77->0x88`)
    - Your experiences with the project
    - Anything else you want to tell me

### Please note:

* Your writeup *must* be done in [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) format and must be included in the repository as a separate file. View the file [`README.md`](README.md?plain=1) for an example of Markdown.
* Screenshots should be done in `*.jpg`, `*.png`, or `*.gif` formats, and be included individually as files in your repository (i.e. no binary ‘document’ with the images pasted inside). Screenshots which are too zoomed-in, which do not show your desktop, or are otherwise unidentifiable as belonging to you will not be counted.
* Screenshots *may* be linked in your Markdown file writeup if you wish to do so. 

Your submission must follow the following rules, *else I will not grade it and you will receive a zero for the submission*:

* Do not use compression on your files
* Make sure that all significant code is *commented* with your own explanations
