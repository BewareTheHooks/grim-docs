# How to get Grim Dawn Mods on Steam Deck Linux

Author: [scottc](https://github.com/scottc)

Popular unofficial Grim Dawn community mods. (Not steam workshop)

DISCLAIMER: I am not the author of these mods. Use at your own risk, no warranty provided, may destroy your save games, may cause data loss, get your steam account stolen, permanently banned, damage to hardware or personal injury.

At time of writing this post:

## GrimInternals

0.  Download [GrimInternals](http://www.grimdawn.com/forums/showthread.php?t=53629).
    
1.  Extract GrimInternals, as per the windows instructions.  
    (Typically; `"/home/__YOUR_USER__/.local/share/Steam/steamapps/common/Grim Dawn"`)
    

> OK, I got it working tonight. For me, I had to make sure GrimInternals64.exe and GrimInternalsDll64.exe were located directly in my Grim Dawn folder. Having them in the x64 folder simply would not work.

[@SherrifsNear](https://github.com/SherrifsNear) [#466 (comment)](https://github.com/ValveSoftware/Proton/issues/466#issuecomment-503800017)

2.  Can dump the proton run command via adding launch options to Grim Dawn:  
    Properties > SET LAUNCH OPTIONS...  
    `PROTON_DUMP_DEBUG_COMMANDS=1 %command%`
    
3.  Run and then exit Grim Dawn.
    
4.  Make a copy of the dumped run command, to home directory:  
    `cp "/tmp/proton_$USER/run" "$HOME/run_grim_dawn.sh"`
    
5.  Edit `$HOME/run_grim_dawn.sh` with text editor, and modify the `DEF_CMD` var file path to point at GrimInternals. And any other customizations as you see fit.
    

```
cd "/home/__YOUR_USER__/.local/share/Steam/steamapps/common/Grim Dawn"
DEF_CMD=("/home/__YOUR_USER__/.local/share/Steam/steamapps/common/Grim Dawn/GrimInternals64.exe")
```

**Note:** I also explicitly have the version of proton installed, under Library > Tools. Which appears under `$HOME/.local/share/Steam/steamapps/common/Proton __VERSION__/`

6.  Make it executable:  
    `chmod +x ~/run_grim_dawn.sh`
    
7.  Run it:
    

```
cd ~
./run_grim_dawn.sh
```

If it fails to run, you can remove this line from the run command, to get errors printed to the console. To help troubleshoot. But comes with a small performance penalty.

```
WINEDEBUG="-all" \
```

Should also be able to add it as a Non-Steam game shortcut.

## Item Color Filter

0.  Download [Item Color Filter](http://www.grimdawn.com/forums/showthread.php?t=63773&page=15#post718407) and check that you have the latest version.  
    (outdated versions may break in-game text descriptions)
1.  Extract the Item Color Filter, as per the windows instructions.  
    (Typically; `"/home/__YOUR_USER__/.local/share/Steam/steamapps/common/Grim Dawn"`)
2.  Play Grim Dawn.
3.  Manually update after each Grim Dawn release.

## GDItemAssistant

I haven't had any luck with [GDItemAssistant](http://www.grimdawn.com/forums/showthread.php?t=35240) which depends on dll injection.

## GDStash

As per [@lieff](https://github.com/lieff) 's comments below:  
[#466 (comment)](https://github.com/ValveSoftware/Proton/issues/466#issuecomment-483631990)

> `java -Xms1024m -Xmx1024m -jar GDStash.jar`

You can also put this in a shell script (`.sh`) file with executable permissions `chmod +x`, and then add to steam library for convenience.

```
#!/bin/sh
java -Xms1024m -Xmx1024m -jar GDStash.jar
```