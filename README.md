Foreward:

This has been a fun project that I’ve immersed myself in over the past several months. What started as a rudimentary romhacking attempt ended up spiraling into an adventure in z80 assembly! Initially, I thought this game was simple and short enough that I’d just replace the text and get the ‘jist’ of things. I wanted to do this because [at the time] there was no translation for the PC-88 version, which seemed criminal to me considering how impactful and influential this game was. 

I began poking around in the hex editor around October and on Christmas Eve, another hacker reached out to me informing me they had their own translation effort on the very same game and were ready to release. Since I had taken this project on for fun and to learn some things, I didn’t see any reason to abandon it and decided to carry on and take the time to learn a few more things along the way. 

It was sort of like a pressure was gone now that I didn’t need to worry about what expectations might come with being the “first” translation, and at the same time it also gave me a need to do more than what I was initially planning to. Now I could take my time and try and do all the things I wanted to do with it!

Without that having happened, I don’t know if I would have even learned any z80 assembly, let alone had a project turn out anything close to what it has. I must give Fishbone a very special thank you for reaching out to me and being a major catalyst in my romhacking adventure!

What’s in the Patch?
PC-88:
• Variable Width Font - Characters like ‘i’ and ‘l’ use half the screen space as most other characters..
• Window Drawing Adjustments (so the boxes aren’t drawn for all full-width characters).
• Dictionary Compression
• Color Text Highlighting
• Messages like “I can’t afford that” and “I already have one” wait to be cleared so player can read 
• Field “pager” which can cascade additional text boxes to the screen
• Shop “pager” which completely redraws the text area used in shops/houses for infinite use
• “Book Emulation” for the books to look more like books when you read them
• Support for custom item acquisition messages

Sharp X1:
• Variable Width Font - Characters like ‘i’ and ‘l’ use half the screen space as most other characters..
• Window Drawing Adjustments (so the boxes aren’t drawn for all full-width characters).
• Dictionary Compression
• Messages like “I can’t afford that” and “I already have one” wait to be cleared so player can read 
• Shop “pager” which completely redraws the text area used in shops/houses for infinite use

MSX:
• Variable Width Font - Characters like ‘i’ and ‘l’ use half the screen space as most other characters..
• Window Drawing Adjustments (so the boxes aren’t drawn for all full-width characters).
• Font color changed to match other releases
• Faux-highlighting via colored glyphs
• Color of ‘ENEMY’ text changed to better match other releases
• Inventory text color changed to make highlighting more visible

Translation Notes (Contains spoilers where marked):
This translation aims for a balance between honoring the original vision while taking newer entries into consideration. I wanted to be true to Tomoyoshi Miyazaki’s vision first and foremost, so I sought to “understand” the game as best I could. It’s interesting how playing through a game while translating it will give you a certain kind of perspective of things, and then how learning about the sources of inspriation for things may enhance or even change that perspective.

It seems almost every single version of Ys I is largely based on the script of this release, and in the cases of the Sharp X1, MSX, FM-7, FM-77AV, and PC-98 releases is virtually identical (and the English MS-DOS and Apple II GS releases are fairly accurate translations of this original script)! With this in mind, the various translation differences we’ve seen over the years become more intriguing, and give a deeper insight to the script as a whole.

For example, in the bar you meet a man who lost something. The original MS-DOS/Apple II GS releases [correctly] translate his words to indicate the object was a gift for his mother. However, the English localization for the Turbo Duo remake changes this to be a gift for his wife, and even the much more recent English release of Chronicles sticks with this idea (in all versions, he isn’t keen to return home without it). This is a very subtle thing, but I think it ends up making a very different character in the end:
 • The original version of the character seems to be holding his mother in a very high regard, and is in a state of dispair because he wanted to do something special for her.
• The changed version of the character seems instead to be scared of his wife, as he suggests he’ll be in some sort of “trouble” if he returns without it.

The more I think about what either of those situations, the more different they seem to feel, thus I felt it all the more important to stick with the original concept. However, this does not mean this translation is 100% true to every original word, as other areas of the script have certainly had some “liberties” taken.

***MAJOR SPOILERS AHEAD***

One of the biggest “changes” is to the dialog with Feena. When the player rescues her, Adol actually speaks and tells her to sneak away while the monsters are distracted with him. This presents a few problems:

• Adol gets to where he is because of the Tovah Crystal he is carrying. While one could argue that since Feena is one of the Goddesses, she can likely use the statues without needing a crystal, however at this point she does not have any of her memories and would not know that, and more importantly, it’s Adol’s idea and he doesn’t know any of that!

• Feena is in a very vulnerable state here and her lack of memories only makes Adol’s words telling her to find a way without him seem quite callous. While Adol is more of an “adventurer” rather than a classic “hero”, I feel the way they’ve built his character otherwise suggest he would not say THAT (and the ACTUAL reason for this was simply that Feena was part of the background tiles rather than being a sprite, and therefore could not follow the player or anything like that, so this was what they wrote when they decided to “move on”).

I decided that since Pim seems to have an endless supply of wings to sell and they’re common enough that Goban is keen to “hold onto” yours when you leave for Darm Tower, that even an amnesiac Feena may have indeed at least heard of them and know how they work, so she just needed to be released from her bonds in order to be able to use the one she has (or knows where to find one, if it’s unrealistic to think she’d have one on her person whilst locked in the cell; it’s not that deep). While this is definitely a significant change from the source material, I feel it’s justified by giving a proper in-game explanation for how she’s able to escape without Adol, and is a bit more consistent with how Adol seems to be eager and willing to help everyone else along his way here.

*** END OF SPOILERS ***

While I could go further in-depth and explain other liberties (like the Asteka references or finding Roda’s brother’s name in the demo), in order to keep this README from being big enough to be the 7th Book of Ys, I’ll just say that a lot of thought went into each thing to try and make sure everything “fit” the themes of Miyazaki’s story.

Technical Notes on Other Versions:
I noticed rather early on that the PC-98 version had the exact same text and pointers as the PC-88 version (and assets such as the font were stored in the same manner with the same overall data). This was well before any assembly hacks were even considered possible, so I initially set out to pretty much “copy/paste” everything when it was finished. 

I was nearly finished with the first draft of Disk A before I fell down the z80 assembly rabbit hole, so once I added assembly hacks to the PC-88 version it meant I’d have two different scripts, but fortunately I already had the non-assembly one ~50% complete, so figured I’d still make the patch for it, as well.

Further research indicated that the FM-7, FM-77AV, and Sharp X1 versions also had the same text and pointers, and the MSX version mostly did except the high bytes were different. Interestingly, the high bytes should be different on the X1 version as well (and the FM-7/77AV versions should [probably] be big endian), but the code around them seems to have the math to “convert” them. This means that the PC-88 version is actually much more flexible for where you can point to than the others. 

The X1 version was similar enough in code that most of the PC-88 hacks I did were able to be ported within a day or so (in fact, most of it was ported by looking at the hex without even running the game and simply recalculating addressses). I’m still rather new to coding, let alone z80 assembly, and couldn’t get things like the color text highlighter and field window drawing to work properly. 

The MSX version has a lot of the same code, but some of it is also a good bit different. For example, the spacing routine uses the same king of logic as the PC-88 and X1 versions, but with an entirely different formula, so I had to write the VWF routine a bit differently. Since the dictionary isn’t very useful without being able to control screen blanking and window drawing for additional text boxes (but a VWF still looks nice), I decided that the MSX version would mostly be the base for all the non-assembly hacked versions (and they could have their scripts tweaked according to their needs later, like what seemed to be the case in their initial porting of all of the different versions). 

Surprisingly, the FM-7 version seems to have a LOT of z80 code present, but doesn’t seem to be using it as I was surprised to discover absolutely none of my hacks seemed to have any affect when ported over. It was this discovery that helped lead to a plan that could handle different scripts with the same integrity and objectives in mind.

As the project evolved, it was less realistic to try and port all of the code from the PC-88 hacks since I kept running into little nuances that required me to tweak the code, change the dictionary, etc. I do believe it’s possible to port them all, but I also kind of liked the idea of letting each version be a bit unique from each other. 

Differences Between Other Versions:
All of the ports are based on the PC-88 version, which all have various pros and cons. Here is my summary of observations about the different versions:

• MSX - This version feels more “8-bit” than any other version (besides the Famicom port, of course). However, it has the advantage of using a 16-color palette so some people might actually prefer the graphics from this version over the others because of its use of color. This version certainly moves the slowest of all the original releases, but the gameplay is balanced accordingly and it certainly feels properly like Ys. This version uses PSG sound, so there’s no FM in any of the music, and the tracks for the Title Screen, Mine, Darm Tower, Ending and Credits are entirely different. Speaking of the ending, this version actually has 3 different pictures it cycles between (just like the FM-77AV version). Music stops when it needs to access the disk, and the game uses the same [primary] disk drive for the game disk and the user disk, so you’ll need to eject and insert quite a bit (although you can seemingly write your user data to the game disk safely, this is generally not recommended). This is the only version to use arrow keys for movement, as all other versions use the number pad.

• X1 - This version uses the same soundtrack as the MSX version, and the graphics are nearly identical to the PC-88 version. The movement isn’t quite as smooth, and the music stops whenever the game needs to access the disk again just like the MSX version. It also uses a single [primary] disk drive for the user to juggle the Game Disk and User Disk between. 

• FM-7 - The most obvious difference between this version and all others is that when you press a button to move, Adol will continue to move until you press either another direction or you can press the space bar or 5 on the number pad to make him stop. After a while, you get used to it and in some instances, may even prefer that style of movement, but it also makes talking to NPCs that move even more difficult, and also makes the player need to release then hold the button to move when clearing a text box so that they don’t just stand there forever refreshing it. The second most obvious difference is that EVERY text bubble that occurs where the player can walk stops the music (further reducing incentive for the player to talk to anybody). If you search Disk B in a hex editor, the developers left a message that there was not enough memory to use the FM soundtrack, so this uses the same soundtrack as the MSX and X1 releases, however the unused “bonus” FM tracks from the PC-88’s hidden player on Disk B are also present here, and have their own “hidden player”. 

• FM-77AV - This version is nearly identical to the PC-88 version, has the proper FM soundtrack which still resets when disk loading occurs, but it seems much less frequent than other versions and faster and smother when it does occur. The ending also has better quality versions of the same art the MSX version uses but with the original ending theme from the PC-88 version. The movement is also “normal”, though not quite as smooth as the PC-88’s controls seem to be (not that there’s a huge difference, but it’s noticable in certain areas) and the credits are presented over a different graphic than any other version here. The graphics are a little bit better than the PC-88 version but the extra loading stops and slightly stiffer controls prevent this one from being objectively superior. 

• PC-98 - This version is also rather close to the PC-88 version, but there are definitely some differences. The graphics are slightly better than the PC-88 version, but scrolling is worse. I’m not sure if the music is inferior on this version or if PC-98 sound emulation is so bad that I can’t hear a proper rendition of it without real hardware. 

Special Thanks:
A super-massive special “thank you” goes out to Mr. Hiromasa Iwasaki (of Hudson Soft), who was kind and welcoming enough to answer any and every Ys question I could think of! As it turns out, he is quite the expert on the lore of Ys I & II (as he should be, considering he did the PC Engine port). 

I’d also like to thank Mr. Jakes of Basement Brothers’ youtube channel for not only making me aware of this original version of Ys, but also of many things about the PC-88 and its library of games (especially how to boot and navigate each title) through the numerous videos uploaded. The videos on Asteka and Ys were also particularly insightful for this project! 

The wonderful people of the #pc98_translation_discussion discord channel for language help, as well as pointing out additional resources, and the talented romhackers in the RHDI discord channel for various input and encouragement as the project progressed.

Kaisaan & Fishbone for reaching out to me, inviting me to the GeoFront and Dandelion communities 
Danchou Xavier for linking me to the translated manual by generic_archiver on archive.org
NightWolve for access to his Ys I Chronicles script for reference
Neill Corlett for helping me get into romhacking 20 years ago and inspiring me to assembly hack
RunningSnakes for helping me set up my wii to play PC88, PC98 and MSX
ian michael for helping me set up X1 Millennium on the Dreamcast
Calico, ManxomeBromide, abridgewater, Mugi, danke, … probably a few others I can’t recall at the moment - I appreciate all of the input, insight, and interactions!

Tools Used:
• Text Edit / Notepad
• Tile Molester
• WindHex/Hex Fiend
• m88
• quasi88
• quasi88-wii
• Random House Japanese-English English-Japanese Dictionary, Ballantine Books 10th Edition, 1996
• A Guide to Reading & Writing Japanese (Revised Ed), Charles E. Tuttle Company 77th printing, 1996
• google
• Rannome (https://rcktrncn.github.io/mysite)
• generic_archiver’s Ys I PC-88 Manual Scan + Translation
• youtube: BulletEyeGames, sayak@, LaTanaDiMrX, U Can Beat Video Games, Basement Brothers
