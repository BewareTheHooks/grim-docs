---
comments: true
---

# How-To Edit NPC Names

Author: [powbam](https://forums.crateentertainment.com/u/powbam)

## 1. Navigate to GD’s root installation folder.

![scr1](https://forums.crateentertainment.com/uploads/default/original/3X/0/c/0c6c1115564077f687c6805775e9e86cd898b5fa.png)


Mine’s on my D:\ drive but default path (for Steam) is:
`C:\Program Files (x86)\Steam\steamapps\common\Grim Dawn`


## 2. Scroll down and select/highlight ArchiveTool.exe

then find zlibwapi.dll , hold down the Ctrl key, and select it as well so that both are selected. Now hit Ctrl+C to copy them both into system memory.


## 3. Enter the resources folder. 

Press Ctrl+V to paste both files here.

![scr2](https://forums.crateentertainment.com/uploads/default/original/3X/c/b/cbbc3b9ec8204827ad63d7479ecd71b7111f3b41.png)


## 4. Right-click an empty spot in the folder and call up Powershell.

![scr3](https://forums.crateentertainment.com/uploads/default/original/3X/0/0/00128e81304a5523a60558eb72fa34b06a590430.png)


## 5. Extract Contents

From here we are going to tell `ArchiveTool.exe` to extract the contents of `Text_EN.arc` and `Conversations.arc`…

![scr4](https://forums.crateentertainment.com/uploads/default/original/3X/3/3/33199df987f303b0749b4b36db2c4dbf31fbb080.png)

Just copy and paste the block of text below. Ensure that the paths are the same as yours.

```
.\ArchiveTool.exe "C:\Program Files (x86)\Steam\steamapps\common\Grim Dawn\resources\Text_EN.arc" -extract "C:\Program Files (x86)\Steam\steamapps\common\Grim Dawn\resources"; .\ArchiveTool.exe "C:\Program Files (x86)\Steam\steamapps\common\Grim Dawn\resources\Conversations.arc" -extract "C:\Program Files (x86)\Steam\steamapps\common\Grim Dawn\resources"
```

If everything is right Powershell should quickly spit out a bunch of text in sequence and you will have two new folders occupying the directory.

![scr5](https://forums.crateentertainment.com/uploads/default/original/3X/6/0/60eb296c7418b5a038fd9695704f9e15f6923239.png)


## 6. Now for the actual edits. First, enter the `text_en` folder…

![scr6](https://forums.crateentertainment.com/uploads/default/original/3X/d/f/df18ef3c9a63b47e7b6c39239075ffc4d8536f71.png)

…and copy the `tags_storyelements.txt` file from here then navigate to Grim Dawn’s `Settings` folder in it’s local saving location:

`C:\Users\YOUR_USERNAME\Documents\My Games\Grim Dawn\Settings`

Create a new folder here and name it `text_en` and then paste your copied text file inside of it.

![scr7](https://forums.crateentertainment.com/uploads/default/original/3X/8/6/86cbc72e5b041f31b74970a57c3c8cb084e61768.png)

Open it up to edit it and scroll down a bit to the #NPC Names section.

![scr8](https://forums.crateentertainment.com/uploads/default/original/3X/b/b/bba1fdca00bb6e1aaf48f72bb16970a9f89d8515.png)

Comment out John Bourbon’s tag with a # sign but copy the text and paste it on the line below it. Lets call him Cap’n Crunch instead. Save the file and fire the game up and go talk to Cap’n Crunch.

![scr9](https://forums.crateentertainment.com/uploads/default/original/3X/8/7/87e5d35d0ad89cbb0613b6360b3e6142a29f1456.jpeg)

We managed to change his name that shows when you hover your mouse on him but his conversation window still retains the original name.

## 7. Go Back
Which brings us to the last bit that needs to be done. Go back to where you extracted files at earlier and enter the `conversations` folder you extracted there. See the file named `npc_johnbourbon_reversetest_01.cnv`? That’s your next target…

![scr10](https://forums.crateentertainment.com/uploads/default/original/3X/c/a/ca9f2ab076a38f927be9d1398c559999dec8b2b4.png)

…but first you need to go back two directories to GD’s root install directory…

![scr11](https://forums.crateentertainment.com/uploads/default/original/3X/1/b/1bebdda51b8e5b7491755576962709f9c7035248.png)

…and launch the `ConversationEditor.exe` located there. It will ask you for a `Working Directory` and a `Build Directory` on first launch. You can just give it the root install folder in both cases but for our purposes it really doesn’t matter.

Click the little `Open` button and feed it the above mentioned `npc_johnbourbon_reversetest_01.cnv` file I mentioned just before.

![scr12](https://forums.crateentertainment.com/uploads/default/original/3X/a/f/af4fa2e98185b0ba915022d7617322d14820cc11.png)

When it loads click and highlight where it says `John Bourbon` near the top so you can edit the name in the Text Editor down below it. Change that to Cap’n Crunch…

![scr13](https://forums.crateentertainment.com/uploads/default/original/3X/0/c/0c0a972f430f48f3ad5fdf9d791d4c8164331831.png)

…then simply press the ‘Save’ button and close the `ConversationEditor`.

![scr14](https://forums.crateentertainment.com/uploads/default/original/3X/a/7/a77c04b81a0ee5b8d901fd16180c2d1a46ac96cc.png)

Now go copy your freshly edited `npc_johnbourbon_reversetest_01.cnv` file and head on back to GD’s `Settings` folder again and create another new folder in it and name it conversations and paste your file into it.

![scr15](https://forums.crateentertainment.com/uploads/default/original/3X/9/b/9b77f09b6a8d689650eca580310790d2013dd34d.png)

Fire up the game and head back to have a chat with Ye Olde Cap’n Crunch again.

![scr16](https://forums.crateentertainment.com/uploads/default/original/3X/b/c/bc7e08d2f1ea5b147a06f55b3dd3c60ac1532788.jpeg)

Wow. You did it champ.

You can now either delete your folders you extracted or hold on to 'em if ya wanna poke around some more. Keep in mind that NPC’s like Bourbon get their name tossed around in a number of other conversation (.cnv) files, so if ya wanna be technical with it you still might have a leeeetle bit more work to do. But now you’re on your way.