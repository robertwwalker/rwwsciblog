---
title: 15 Characters that Made Me Better in the Classroom
subtitle: Celebrating quarto, reveal.js and multiplex
author: RWW
date: '2022-09-22'
slug: []
categories:
  - R
  - hybrid
tags: []
---

**"You forgot to share your screen," is one of the phrases that I will most closely associate with pandemic-era teaching.  But, when deploying code in the classroom, screen sharing is not enough.  `quarto`, `reveal.js` and `multiplex: true` have empowered me to be better at my job.** 

Many academics faced challenges in the transition to hybrid and fully online education during COVID-19.  This post is dedicated to recent developments made easy by RStudio's `quarto` project  that solves three difficult and interrelated problems that frequently arose, and continue to arise, during the ongoing pandemic and in a hybrid teaching world.  In concert, I believe that they have improved my effectiveness in online data science education.  What are the the two main problems?

- Sharing code
- Sharing screens

There is a third interrelated problem; student access to the code on the screen and this problem is present for both in-person and online learners in the hybrid environment.

# In Steps Quarto and Magic Happens with the Wonders of Reveal.js

In fifteen keystrokes, `quarto` has a **literally perfect** solution.

`multiplex: true`

## Background

I have used Yihui Xie's excellent `xaringan` package for slides for a few years now.  It really is an amazing tool.  The thing that prompted my original foray into using it was the easy ability to share code in slides.  But with the transition to Zoom during the pandemic and ubiquitously before the pandemic, presenting slides in a classroom or with screen sharing puts a barrier to copying and pasting the provided code.

The barrier for in-person learners is that the code is on the projector screen, **not their screen**.  Zoom's screen share presents a very similar problem, the code is on their screen, but **it is an image rather than copy-pasteable text**.

## The Quarto Solution

With fifteen magic keystrokes, the barriers to code access disappear.  Moreover, they have the magnificent side effect of rendering the initial problem moot.  Whether or not one shares the screen, the content of the screen share is available to all learners, in-person or hybrid, with only a browser window open.

`multiplex: true`

## The Details

My goal in the classroom is make the process interactive.  To a management school academic with the goal of teaching future managers how to glean insights from data, I need code to both give the computer instructions on how to manipulate and display the data that is the source of those insights and to provide the scaffolding for transferring the deployed methods to other problems.  I suspect these twin aims are shared by those in the social and natural sciences, management, geography, public health, and all of the disciplines where data science is not the end but instead informs some application in combination with subject-area expertise.

### The Dark Ages: Powerpoint

Long ago, my tool of choice was Microsoft's `Powerpoint`.  Don't judge.  In management schools and in industry, Powerpoint is ubiquitous as presentation software and for white paper creation -- decks that violate basically every principle of effective presentation.  It is familiar.  It does a job.  But everything becomes `curly-quotes` without care and this is a nightmare for writing code.  Moreover, the workflows involve a lot of unnecessary labor.

### `RMarkdown` and The Middle Ages

With `RMarkdown`, `\(\LaTeX\)` beamer presentations in .pdf format and various versions of .html slides became possible and this saved me a lot of manual copying and pasting.  With `xaringan` by Yihui Xie, nice formatting boxes for code and the magic of various innovations in .html became possible.  I still love `xaringan` and for presentations where the audience is not actively engaged in recreating output, `xaringan` is still my favorite.  Indeed, if I could figure out how to get `xaringan` to do what `multiplex` can, I would still use it.

The core limitation, as a presenter, of all of the aforementioned implementations of slides in `RMarkdown` is that the audience needs to follow along with the presenter to obtain the code and to deploy it.  No matter how detailed or careful one is, the slides don't just move themselves.

### Modernity and Multiplexing

The pandemic brought new challenges though they were not dissimilar from old challenges. In the hybrid format or in the classroom with a projector or television, the problem remains.  The slides don't move themselves.  Though online learners are far closer to the presentation than are those sitting in the auditorium, there is still a barrier to access.  Neither the computer screen nor the projector screen is accessible in the sense that the code is rendered on that screen as an image rather than as manipulable text.  With quarto and reveal.js, my job and the experience of my students have been vastly improved.
