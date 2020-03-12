I recevied questions about how I produce videos on
https://youtube.com/kisonecat so I record some of my thoughts here.

# Overview

It's harder to have acceptable audio than acceptable video, so use a
reasonable microphone.

If you're looking to make videos *quickly* then various sorts of
"screencast" software is the fastest thing to do, especially if you
have a device with a pen so you can act as if you're writing on a
small blackboard.  **The most important thing is to find something you
like doing, and can do quickly.**

For large courses, I've also run "office hours" on
https://www.twitch.tv/kisonecat but this isn't as interactive as
anyone would like.

# How can I do voice-over on beamer slides?

I've created

  https://github.com/kisonecat/beaudiomer

which takes a beamer file with `\audio{wavefile.wav}` commands and
produces an `.mp4` video.

You can build frames like

```
\begin{frame}
  I'm talking \audio{talking-here.wav} \pause and whispering
  \audio{also-whispering.wav}.
\end{frame}
```

and the `\audio` gets attached before and after the `\pause`.

This does require recording a large number of short audio files.

# What equipment did you use for the videos?

The camera is a Canon VIXIA so I can shoot in HD.

In some of the videos, I used a wireless lav mic, but more recently
I'm using an AT4053b hypercardioid mic connected to a preamp. It would
be nice if the camcorder had XLR inputs.

# How long does it take to make video?

It took about a week to produce the first five minutes of video.

But with practice it gets much faster.  From initially drafting a
script to finishing the video editing, I estimate I was spending about
20 hours to produce between 1 and 2 hours of video.

# What software did you use?

For software, the titles and other computer generated effects were
generated entirely with software I wrote myself using LaTeX and
ffmpeg, and the video editing also was done with software I wrote
myself using MLT; you can find some of this at

  https://github.com/kisonecat/autocut

All this software is freely available (and indeed, if you use it,
please let me know!).

The autocutter is especially important, because it cuts off the
silence portions before and after each clip, meaning I do not have to
do much at all in the way of editing the video.

# What is the workflow like?

I start with scripts that look like this

```
talk: if we care about extreme values, it'd help to know how to find them; we can use the
following theorem
paper: Suppose f is defined on the interval (a,b); if c is an extreme point of f, and f
is differentiable at c, then f'(c) = 0
talk: it's actually easier to show something slightly different
paper: if f is differentiable at c, and f'(c) \neq 0, then c is NOT an extreme point
talk: why is this? intuitively, if the derivative is nonzero, then if I wiggle the input
a bit, it'll  make the output larger or smaller
paper: we can do this formally, too; f(c+h) - f(c)/h = L neq 0
talk: notice what just happened
paper: we started with infintesimal information (a limit) and we ended up with local
information (something true for inputs near c)
```

and then film all the "talk" parts in order as a talking head, and all
the paper pieces with the camera pointing down on my desk.  There's
nobody behind the camera.

That gives me a bunch of clips, some of which were filmed upside down
(namely the "paper" parts).  The scripts are really designed as notes
for me to riff from.  I almost never reshoot video after I feel like I
had a good enough shot.

Then I use the aforementioned tool I wrote called the "autocutter"

   https://github.com/kisonecat/autocut

to rotate the upside-down clips, chomp the silent beginnings and
endings of all the clips, and then concatenate them together as a
single video.  I watch the video at highspeed at this point (mostly to
make sure that the upside paper scenes were in fact flipped -- that
being the most common error).  Another tool generates the animated
title (the latest version of which uses blender) from a .tex title.

# What about the other special effects?

These are all done with one-off tricks.

There's an augmented reality effect is visible in ["How far out can you
build a one-sided bridge?"](http://youtu.be/BjmypdFCl-Q?t=10m20s) 
which demonstrates how I've composited computer generated objects into
scenes (that bridge isn't really there). Video is less interactive
than a lecture---I say it is more like TV than like community
theater---but video does permit these sorts of effects that simply
couldn't be done in class or with powerpoint.

["Visually, what is the limit of a sequence?"](http://youtu.be/0UCRZAsIkXM?t=38s)
is another example where I interact with a computer generated image.

The video ["In what sense is sum 9 + 90 + 900 + ... meaningful?"](http://youtu.be/4OaNH1OsqUc?t=8m50s)
resonated with a lot of people, especially the monologue at the end on
the reality of mathematics.

The video ["What is the limit of (sin x)/x?"](http://youtu.be/otW6HcxrRlY?t=2m4s)
is an example of superimposing graphics onto paper.  This argument is
often given on blackboards, but being able to draw some nice rectangles
really helps.

In ["How can more functions be made?"](http://youtu.be/nEqCaj3hBKU?t=2m4s)
I combine both writing and computer generated graphics.  This video
emphasizes "functions as transformations" while at some point, the
student must also think of functions are "inputs covarying with
outputs."  Being able to make these metaphors more visible is another
way in which video shines.

["Does sum 1/n converge or diverge?"](http://youtu.be/_Ui5_-lIK34?t=3m8s)
does a nice job of demonstrating how we try to make math more tactile
with arguments involving paper.

["What does d/dx mean by itself?"](http://youtu.be/wouMgDxvMSY?t=50s)
is an example of trying to make math into characters and telling a
story. A similar thing is done in ["What is the difference between
potential and actual infinity?"](http://youtu.be/rNBoGy19lHc).
