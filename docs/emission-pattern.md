---
comments: true
---

# Ceno Emissions Tutorial
Author: [Ceno](https://forums.crateentertainment.com/u/ceno/summary)

This post is dedicated to timing operations in an Emitter’s emission pattern. If you haven’t yet, I’d recommend reading the above post for some basic instructions on setting up an Emitter within the PSEditor for Grim Dawn.

Right now, our particles are all over the place. That’s no good! It’d be nice if we could make them all appear relatively on top of one another…click on ‘Emitter Size’.

![text](https://i.imgur.com/91jBO66.png)

Another window will appear, featuring a very nondescript line with two endpoints dictated by a pair of squares. Click+drag those squares to the bottom of this box (it can be tricky to get them to the actual bottom (0.00); you may need to bring a box close to the bottom, then reclick and redrag them down a little more again). The Emitter will update in real time as you make this change.

Can you see what’s going on here? We’re describing the size (in this context, it might make the most sense to suggest this size as a VOLUME) of our Emitter (which is presently in the shape of a Sphere, as defined by ‘Type’ above ‘Looping’. We don’t need to change the Type for now). Particles appear at random anywhere within the Emitter. If we shrink the size of this Emitter down to a minuscule proportion of what it was (or, in this case, zero) we can get our Particles to overlap one another more cohesively! Now we’re really getting a familiar-looking Sigil! It’s a little bright, though…

Close the Emitter Size window, then click on ‘Emit Rate’. Also change the lifespan of our Emitter to 0.1 seconds. This means that it will only exist for a brief time, spit out a ton of particles, and then disappear, whereupon it won’t emit anything else.

![text](https://i.imgur.com/yKWdcVL.png)

Right click the black line of the Emission Rate window, forming another manipulable square. Move it and the ending-square to the bottom of the window, and the starting-square to the top of the window. This further shortens the time our 0.1-second Emitter will actually emit stuff; an Emission Rate of 0.00 means no Particles will be Emitted at that timestep. Note that the X-axis is always going to be ‘Time’ in these windows, and the Y-axis will always be whatever you’re modifying to occur at that timestep.

Close the Emission Rate window (or don’t; you can leave these things open if you want and edit them as you go, but things can get kinda cluttered).

Good, our particle system isn’t quite so bright anymore…but pale white is such a bland color. This is a demonic sigil! Let’s make it devilishly purple! Click on Color/Alpha in the Particle Options section of the window.

![text](https://i.imgur.com/nd3Ue52.png)

Particles in Grim Dawn abide by an ARGB (not to be confused with an ARPG :p) color-coding system. ARGB stands for Alpha/Red Green Blue. As such, there are four lines in the window above, each one corresponding to [A]lpha, [R]ed, [G]reen, and [b]lue (R, G, and B will appear directly atop one another at first, and Alpha will be at the top).

You can manipulate these lines as you see fit. Get creative! Feeling like you want to work for Crate? Make a rainbow sigil perfect for that [Ponycorn mastery Grava keeps teasing us about…](https://www.twitch.tv/crateentertainment)

When you’ve finished, you should have a decent looking sigil. Unfortunately, it’s incredibly freaking small (0.5 meters). To fix this, click on ‘Size’ in the Particle Options.

![text](https://i.imgur.com/oJolpkM.png)

Here, the Y-axis corresponds to the number of meters your particular particle will be stretched to. But wait! This axis tops out at far too small a value! At the top of the Particle Size Curve window, click in the leftmost textbox and enter in a new radius for your sigil. Then click on ‘Set’. This will automatically scale up the Y-axis for your particle. You can make a particle shrink or grow (or both) over its lifespan. More ways to get creative!

We’re nearing the end of our tutorial, and have merely but minutiae left to touch upon. By manipulating Emitter and Particle effects over a varying span of time for multiple Emitters, you can create incredibly complex and visually stunning particle systems to use in-game! At this point, if you feel comfortable with the PSEditor’s user-interface, I’d start poking around in Grim Dawn’s existing pfx files and seeing how they work. Recolor some Particles, make Emitters last longer or shorter, change their emission rates! Add new Emitters to existing pfx files and save them as your own work (hehehehe…)!

I’ve touched up my sigil a bit:

![text](https://i.imgur.com/JizQXXA.png)

I’ve made the Particles emitted last a fifth of a second longer, and I’ve also made those emitted toward the end of the Emitter’s lifespan float up slightly. I think it looks much better. If you’ve Oriented Vertically, Velocity will bounce a Particle up (you can make it fall with ‘Gravity’ in Particle Options, which can go negative as well). Otherwise, its direction will be random.

When you’re satisfied with what you’ve got, go to File>Save As. Then select your output folder (you made one of those in /source, right?), add a ‘’ in the directory, and type out your pfx’s name (and suffix it with .pfx!). Then click ‘Accept’. You can name it whatever you want, though I try to keep things descriptive and akin to Crate’s standardization for naming:

![text](https://i.imgur.com/M1RzOZF.png)

Congrats! You’ve saved your first pfx file to your computer, and can now use it in a mod! There’s some fancy Asset Manager/database management stuff you need to do to actually link things up correctly, but that’s beyond the scope of this tutorial.

Keep experimenting! Keep tinkering! Keep thinking of ideas! There’s a lot of really cool stuff you can do in Grim Dawn’s PSEditor, though - as with anything in Grim Dawn Modding - you may need to get creative in a roundabout implementation of your idea.

Who knows, maybe you could even make a particle system to simulate a Whirlwind-style AoE buff! I doubt that’s possible, though…

![text](https://i.imgur.com/4B8DafD.png)