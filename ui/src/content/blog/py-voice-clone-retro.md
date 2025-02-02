---
author: David Garcia
pubDatetime: 2024-08-10T18:30:00.632Z
title: Py-voice-clone Retrospective
slug: py-voice-clone-retro
featured: false
draft: true
tags:
  - machine-learning
description:
  A retrospective on my voice cloning experiments
---

This blog goes over my experience with doing some voice cloning work.

Relevant codebase: https://github.com/Dgarc359/py-voice-clone

# Intro
This is one of those technologies that has some grim, cyberpunk-ish, undertones, so before we
go any further, I just want it to be clear where I was going with this implementation.

I pursued this technology maybe a year or two before this most recent, and more successful
attempt. I am someone who is interested in embedded systems engineering, and specifically
creating robots. I don't think I'm unique in imagining having a little robot
companion that can be fun to engage with.

One of the most engaging depictions of a robot companion is Wheatley from Portal 2.
He's got a unique charm to him and he has one of the more interesting designs
for a robot.

I've seen some videos of people creating Wheatley robots on Youtube

<iframe width="560" height="315" src="https://www.youtube.com/embed/OEn9hZ-Tw1E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

...

This is the type of content that makes me want to go deep on embedded systems and
learn as much as I can about robotics.

So, I had a dream, and my goal was to one day build one of these robots, but in the
meantime, I would prepare some technology so that it could have dynamic
conversations with people.

This is where the voice cloning comes in.

The ideal way that this would work is:
1. Person speaks with robot
2. Robot parses person's statements via Speech to text, and then process what they
said via whatever LLM works best at the time
3. LLM is given context about what kind of character they should be impersonating,
which gives some direction as to what kind of response needs to be generated
4. Generated LLM response is then used as input to generate voice line using cloned voice
(model created from the py-voice-clone codebase)

# Preparing a voice cloning dataset
After developing an initial pipeline, part of the process, outside of general improvements
to the codebase, was gathering good samples of Wheatley.

This kind of data is available to anyone with the savvy to look, but I won't be
distributing the dataset I ended up creating on here.

I tried a few initial runs with some unedited voice lines ripped pretty much
directly from the game. The results of this were less than promising

<audio controls>
  <source src="/assets/audio/output-01.wav" />
</audio>
