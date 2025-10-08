---
# You can also start simply with 'default'
theme: neversink
neversink_slug: 2025-10-07 DElab meeting
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: (More) Matching Pennies!
info: |
  Timothy Sit
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
seoMeta:
  # By default, Slidev will use ./og-image.png if it exists,
  # or generate one from the first slide if not found.
  ogImage: auto
  # ogImage: https://cover.sli.dev
---

# (More) Matching Pennies!

Timothy Sit


<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: slide-left
---

# Brief background on matching pennies


---
transition: slide-left
---

# Brief background on the matching pennies project

 - TODO: Go through Joanna matching pennies task 



---
transition: slide-left
clicks: 7
class: flex flex-col justify-center
---


# Tim joins the team!

<div class="flex flex-col h-full justify-center text-xl text-left -mt-6
            not-prose space-y-0">

  <!-- Items 1–3 -->
  <ol class="list-decimal pl-6 [&>li]:m-0 [&>li+li]:mt-1">
    <li :class="{'opacity-0 pointer-events-none': $clicks < 1}">
      Comparison of mouse and monkey matching pennies
    </li>
    <li :class="{'opacity-0 pointer-events-none': $clicks < 2}">
      Non-(GLM-HMM) ways of looking at matching pennies behaviour
    </li>
    <li :class="{'opacity-0 pointer-events-none': $clicks < 3}">
      Analysis of widefield data during mouse matching pennies
    </li>
  </ol>

  <!-- Items 4–6 wrapped in a v-mark box; spacing normalized -->
  <div class="self-start inline-block" v-mark.box.orange="7">
    <ol start="4" class="list-decimal pl-6 [&>li]:m-0 [&>li+li]:mt-1 -mt-1">
      <li :class="{'opacity-0 pointer-events-none': $clicks < 4}">
        Analysis of photometry data during mouse matching pennies
      </li>
      <li :class="{'opacity-0 pointer-events-none': $clicks < 5}">
        Mouse vs. Mouse matching pennies
      </li>
      <li :class="{'opacity-0 pointer-events-none': $clicks < 6}">
        Some ideas about human matching pennies
      </li>
    </ol>
  </div>

</div>

---
layout: section
color: orange 
transition: slide-left
---

# Part I: Photometry 


--- 
layout: top-title
color: orange 
transition: slide-left 
---

:: title ::

# Scientific Questions


---
layout: top-title
color: orange 
transition: slide-left
---

:: title ::

# Photometry experiments 

:: content :: 

<img src="/photometry-setup.png" class="opacity-100"/>

---
transition: slide-left
layout: top-title
color: orange 
clicks: 1
---

:: title :: 

# What does noradrenaline, dopamine and pupil correlate with?

:: content :: 

<div class="flex gap-4 justify-center">

<img src="/regression_model_schematic_v2.svg" class="opacity-100 w-1/2"/>

<div class="w-1/2"> 

<template v-if="$clicks === 0"> <img src="/regression_model_example_fits_w_pupil_v2.svg" class="w-full" /> 
</template> 

<template v-else> 
<div class="flex gap-4 justify-center">
<img src="/regression_photometry_model007_ev_v3.svg" class="w-[50%]" /> 
<img src="/regression_photometry_delta_ev_state_model005_w_pupil_model004_v3.svg" class="w-[50%]" /> 
</div>
</template> 

</div>

</div>

TODO: make it more clear the three peaks are because of sound and port, may need to add in an x-axis to show this


---
layout: top-title
color: orange 
transition: slide-left
---

:: title :: 
# Can the neuromodulator response be explained by pupil?


:: content :: 

<div class="flex gap-4 justify-center">

<img src="/pupil-cross-correlation-plain.svg" class="opacity-100 w-[40%]"/>

<img src="/regression_photometry_w_pupil_model005_ev.svg" class="opacity-100 w-[40%]"/>

</div>





---
transition: slide-left
---

# How does noradrenaline response differ across states? 


---



---
layout: side-title
color: orange 
align: lm-lm
transition: slide-left 
---

:: title :: 

# Photometry results summary 

:: content :: 

- Noradrenaline mostly signal task events, dopamine mostly signal reward
- Noradrenaline, dopamine and pupil have distict difference in temporal dynamics across states
- Before lick, noradrenaline responses are positively correlated with average reward rate. After/during lick, noradrenaline reward responses during switch trials are amplified only during bias states.  



---
layout: section
color: sky
transition: slide-left
---


# Part 2: Multiplayer matching pennies

---
layout: top-title
color: sky 
transition: slide-left
clicks: 5
---

:: title :: 

# Multiplayer matching pennies task 


:: content ::


<div class="flex justify-center">
  <template v-if="$clicks === 0">
    <img src="/task_animation_1.png" class="opacity-100 w-[50%]" />
  </template>
  <template v-else-if="$clicks === 1">
    <img src="/task_animation_2.png" class="opacity-100 w-[50%]" />
  </template>
  <template v-else-if="$clicks === 2">
    <img src="/task_animation_3.png" class="opacity-100 w-[50%]" />
  </template>
  <template v-else-if="$clicks === 3">
    <img src="/task_animation_4.png" class="opacity-100 w-[50%]" />
  </template>
  <template v-else>
    <img src="/task_animation_5.png" class="opacity-100 w-[50%]" />
  </template>
</div>



---
layout: top-title-two-cols
columns: is-8
align: l-lm-lm
color: sky 
transition: slide-left
---

:: title :: 

# Multiplayer matching pennies traning protocol



:: left :: 


<div class="pt-30">
<img src="/multiplayer_MP_training_stages.svg" class="opacity-100 w-[100%]"/>
</div>


:: right ::


<div class="pt-30">

 - Pair 1 :
 - Pair 2:

</div>






---
layout: top-title
color: sky 
transition: slide-left
---

:: title ::

# BTW: Some mice don't like delays...




---
transition: slide-left 
color: sky 
layout: top-title
---

:: title:: 

# Some example games between J29 and J31

:: content :: 


<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const video = document.getElementById('myvideo')
  if (!video) return

  // Hide controls initially
  video.controls = false

  // When user clicks the video, start playing
  video.addEventListener('click', () => {
    video.play()
  })

  // When it ends: pause, show the last frame, hide controls
  video.addEventListener('ended', () => {
    video.pause()
    video.currentTime = video.duration
    video.controls = false
  })
})
</script>

<video
  id="myvideo"
  src="/animation.mp4"
  controls
  preload="auto"
  class="w-[100%] mx-auto"
/>

---
transition: slide-left 
color: sky 
layout: top-title
class: flex flex-col justify-center
---

:: title:: 

# Who is winning and who is more random?

:: content :: 



<img src="/JOA-M-0029_JOA-M-0033_smoothed_reward_rate_multiplayer.png" class="opacity-100 w-[80%]"/>

<img src="/JOA-M-0029_JOA-M-0033_entropy_multiplayer.png" class="opacity-100 w-[81%]"/>


---
transition: slide-left 
color: sky 
layout: top-title
class: flex flex-col justify-center
---

:: title:: 

# Randomness and rewards when playing agiainst computer vs. mice 

:: content ::


<img src="/JOA-M-0029_reward_and_entropy_during_solo_vs_social.png" class="opacity-100 w-[75%]"/>

<img src="/JOA-M-0033_reward_and_entropy_during_solo_vs_social.png" class="opacity-100 w-[75%]"/>





---
layout: top-title-two-cols
color: sky 
transition: slide-left
---

:: title :: 

# Future plans for mice multiplayer MP



:: left :: 


1. Different shaping before multiplayer matching pennies 
2. Asymmetric payoffs 
3. Matching pennies + ephys recordings


:: right :: 


---
layout: credits 
color: light 
speed: 1 
loop: true
---

<div class="grid text-size-4 grid-cols-3 w-3/4 gap-y-10 auto-rows-min ml-auto mr-auto">
<div class="grid-item text-center mr-0- col-span-3">
  
</div>
<div class="grid-item text-center mr-0- col-span-3">
  <strong>Cast</strong><br> 
  <span class="font-size-3 mt-0">(In order of appearance)</span>
</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Photometry</strong></div>
<div class="grid-item col-span-2">Joanna <i>as PhD student</i>&nbsp;<mdi-open-in-new class="font-size-3 mb-0.5" /><br/>Person 2 <i>as Co-PI</i>&nbsp;<mdi-open-in-new class="font-size-3 mb-0.5" /></div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Multiplayer matching pennies</strong></div>
<div class="grid-item col-span-2">Mehul <i>as Postdoc</i>&nbsp;<mdi-open-in-new class="font-size-3 mb-0.5" /><br/>Joanna <i>as Co-PI</i>&nbsp;<mdi-open-in-new class="font-size-3 mb-0.5" /></div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Mice</strong></div>
<div class="grid-item col-span-2">JOA-M-0020</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Supervision</strong></div>
<div class="grid-item col-span-2">Ann<br/>
Jeff</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Slides</strong></div>
<div class="grid-item col-span-2">
Slidev<br/>
Unocss<br/>
Figma<br/>
Vuejs<br/>
Vite<br/>
</div>
<div class="grid-item col-span-3 text-center mt-180px mb-auto font-size-1.5rem"><strong>Questions?</strong></div>
</div>

