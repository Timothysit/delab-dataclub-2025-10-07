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
transition: fade
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
transition: fade
layout: default
---

# Brief background on matching pennies

<div class="grid grid-cols-2 gap-8 items-center">

  <div>
    <ul class="space-y-4">
      <li v-click="1">The game "matching pennies" was first formally introduced in the book <em>Theory of Games and Economic Behaviour</em> (1944) by John von Neumann and Oskar Morgenstern<sup>1</sup>.</li>
      <li v-click="2">In this game, two players each have two choices (heads or tails), and one player has to match the choice of the other player, whilst the other player has to "unmatch".</li>
      <li v-click="3">It is one of the simplest game that involves strategy and uncertainty<sup>2</sup>. Widely studied in humans and monkeys, only more recently in rodents.</li>
    </ul>
  </div>

<div>
  <img v-if="$clicks === 1" src="/theory-of-games-sothebys-auction.png" class="w-full" />
  
  <img v-else-if="$clicks >= 2" src="/symmetric_matching_pennies.svg" class="w-[70%]" />
</div>

</div>

<div v-click="1" class="absolute bottom-5 left-12 w-3/4">
  <hr class="border-t-1 border-gray-600 opacity-50 mb-2" />
  <p class="text-sm opacity-75">
    <sup>1</sup> Although the term goes back as early as 1904.
  </p>
  <div v-click="3">
   <p class="text-sm opacity-75">
    <sup>2</sup> There is no pure Nash equilibrium, and the reward-maximising behaviour is either to be random or to predict opponent's future move.
  </p>
  </div>
</div>

---
transition: fade
layout: default
---


# Brief background on the matching pennies project


<img src="/MP_task.png" class="opacity-100 w-[100%]"/>


---
transition: fade
layout: default 
---

# Mice learn to do the task


<div class="ml-20 mt-5">
<img src="/mouse_example_choices_1.svg" class="opacity-100 w-[80%]"/>


<img src="/LearningSummary_cosyneabstract2025_2.svg" class="opacity-100 w-[90%]"/>
</div>


---
transition: fade
layout: default 
---


# Mice behaviour can be broadly divided into three states



<img src="/GLM-HMM-cartoon_v1.svg" class="opacity-100 w-[50%]"/>

<img src="/clustered_glm_weights_cosyneabstract2025.svg" class="opacity-100 w-[60%]"/>


<div v-click class="absolute top-[55%] left-150 w-[70%] -translate-y-1/2">
  <img src="/average_pstate_smooth_cosyneabstract2025.svg" class="opacity-100 w-[50%]"/>
</div>


<div class="absolute bottom-4 left-6 text-sm opacity-70">
GLM-HMM from Ashwoord 2022
</div>


---
transition: fade
clicks: 6
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
  <div class="self-start inline-block" v-mark.box.orange="6">
    <ol start="4" class="list-decimal pl-6 [&>li]:m-0 [&>li+li]:mt-1 -mt-1">
      <li :class="{'opacity-0 pointer-events-none': $clicks < 4}">
        Analysis of photometry data during mouse matching pennies
      </li>
      <li :class="{'opacity-0 pointer-events-none': $clicks < 5}">
        Mouse vs. Mouse matching pennies
      </li>
    </ol>
  </div>

</div>

---
layout: section
color: orange 
transition: fade
---

# Part I: Photometry 


--- 
layout: top-title
color: orange 
transition: fade 
---

:: title ::

# Scientific Questions


:: content :: 

<div class="mt-30">

<v-clicks>

1. How are dopamine and noradrenaline signals different in response to different task events and behaviour? 
2. Do their responses change when the animal changes its state or strategy?
3. Can their responses be explained by arousal measured using pupil signals?

</v-clicks>

</div>




---
layout: top-title
color: orange 
transition: fade
---

:: title ::

# Photometry experiments 

:: content :: 

<div class="flex items-center justify-center gap-4">

<img src="/photometry_set_up_cartoon_v2_plain.svg" class="opacity-100 w-[50%]"/>

<v-click>
<img src="/mean_response_ne_and_da_plain.svg" class="opacity-100 w-[80%]"/>
</v-click>

</div>

<div class="absolute bottom-4 left-6 text-sm opacity-70">
5 noradrenaline mice, 4 dopamine mice
</div>




---
transition: fade
layout: top-title
color: orange 
clicks: 3
---

:: title :: 

# What does noradrenaline and dopamine encode?

:: content :: 


<div
  v-motion
  :initial="{ opacity: 0, scale: 1, y: 0, x: -125 }"
  :enter="{ opacity: 1, scale: 2.5, y: 0, transition: { duration: 500 } }"
  :click-1="{ x: -400, y: -125, scale: 1.5, transition: { duration: 500 } }"
  class="absolute top-[40%] left-1/2 -translate-x-1/2 -translate-y-1/2"
>
  <img src="/regression_model_schematic_v2.svg" class="w-64 h-auto" />
</div>

<div
  v-click="1"
  class="absolute top-25 left-100 transition-opacity duration-500 delay-500">
  <img src="/regression_model_example_fits_w_pupil_v5.svg" class="w-300 h-auto" />
</div>


<div
  v-click="2"
  class="absolute bottom-5 left-40 transition-opacity duration-500 delay-500">
  <img src="/regression_photometry_model007_ev_v3.svg" class="w-60 h-auto" />
</div>

<div
  v-click="3"
  class="absolute bottom-0 right-30 transition-opacity duration-500 delay-500">
  <img src="/regression_photometry_delta_ev_state_model008_w_pupil_model005_v6.svg" class="w-100 h-auto" />
</div>





---
layout: top-title
color: orange 
transition: fade
---

:: title :: 
# Can the neuromodulator response be explained by pupil?


:: content :: 

<div class="flex gap-4 justify-center mt-5">

<v-click>
<img src="/pupil-cross-correlation-plain.svg" class="opacity-100 w-[40%]"/>
</v-click>

<v-click>
<img src="/regression_photometry_w_pupil_model005_ev_v3.svg" class="opacity-100 w-[45%]"/>
</v-click>


</div>





---
layout: top-title
color: orange 
transition: fade
---

:: title :: 

# How does noradrenaline and dopamine responses differ across states? 

:: content :: 


<div class="-mt--25"><!-- reduce top margin -->
<div class="flex gap-4 justify-center">
<v-click>
<img src="/NE_DA_response_across_states_plain.svg" class="opacity-100 w-[70%]"/>
</v-click>
<v-click>
<img src="/NE_DA_response_average_dots_plain.svg" class="opacity-100 w-[30%]"/>
</v-click>
</div>
</div>



---
layout: side-title
color: orange 
align: lm-lm
transition: fade 
---

:: title :: 

# Photometry results summary 

:: content :: 

<v-clicks>

- Noradrenaline mostly signal task events, dopamine mostly signal reward
- Noradrenaline, dopamine and pupil have distict difference in temporal dynamics across states
- Before lick, noradrenaline responses are positively correlated with average reward rate. After/during lick, noradrenaline reward responses during switch trials are amplified only during bias states.  

</v-clicks>


---
layout: section
color: sky
transition: fade
---


# Part 2: Multiplayer matching pennies


---
layout: top-title
color: sky 
transition: fade
clicks: 5
---

:: title :: 

# Why multiplayer (mouse vs mouse) matching pennies?

:: content :: 

<div class="mt-15">

<v-clicks>

1. Optimal strategy against a predictive computer is to always be random, whereas playing against an imperfect opponent allows for adaptive strategies (ie. learning and exploiting the choice patterns of the opponent)
2. Allows us to test predictions about what reward-maximising agents will do in variations of the matching pennies game (eg. asymmetric pay-offs, details at the end)
3. Allows us to look at neural dynamics of two interacting animals

</v-clicks>

</div>



---
layout: top-title
color: sky 
transition: fade
clicks: 5
---

:: title :: 

# Multiplayer matching pennies task 


:: content ::


<div class="flex justify-center ml--20">
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
transition: fade
---

:: title :: 

# Multiplayer matching pennies traning protocol


:: left :: 


<div class="pt-30">
  <div class="relative w-full">

  <img src="/multiplayer_MP_training_stages.svg" class="opacity-0 w-full" />

  <div class="absolute top-0 left-0 w-full h-full" style="clip-path: inset(0 75% 0 0);">
    <img src="/multiplayer_MP_training_stages.svg" class="w-full h-full object-cover" />
  </div>

  <div v-click class="absolute top-0 left-0 w-full h-full" style="clip-path: inset(0 50% 0 25%);">
    <img src="/multiplayer_MP_training_stages.svg" class="w-full h-full object-cover" />
  </div>

  <div v-click="2" class="absolute top-0 left-0 w-full h-full" style="clip-path: inset(0 25% 0 50%);">
    <img src="/multiplayer_MP_training_stages.svg" class="w-full h-full object-cover" />
  </div>

  <div v-click="3" class="absolute top-0 left-0 w-full h-full" style="clip-path: inset(0 0 0 75%);">
    <img src="/multiplayer_MP_training_stages.svg" class="w-full h-full object-cover" />
  </div>

  </div>
</div>


:: right ::


<div v-click="4" class="pt-30">

 - Pair 1 : Trained with computer for a few days, then play against each other
 - Pair 2 : Trained to MP experts, will play against each other

</div>




---
layout: top-title
color: sky 
transition: fade
---

:: title ::

# BTW: Some mice don't like delays...

:: content ::


<img src="/solo_MP_rt_per_day.svg" class="opacity-100 w-[90%]"/>



---
layout: top-title-two-cols
color: sky 
transition: fade
---

:: title :: 

# But maybe we can learn something from what they do during the delay


:: left :: 

<div class="-mt-4"><!-- reduce top margin -->
<v-click>
Early in training
<img src="/JOA-M-0033_session_87317_individual_licks.png" class="opacity-100 w-[98%]"/>
</v-click>
</div>

:: right ::

<div class="-mt-4"><!-- reduce top margin -->
<v-click>
Late in training
<img src="/JOA-M-0033_session_90848_individual_licks.png" class="opacity-100 w-[98%]"/>
</v-click>
</div>


---
layout: top-title
color: sky 
transition: fade
clicks: 1
---

:: title :: 

# Perhaps mice become more "committed" to their choices over learning?


:: content :: 

<div
  v-motion
  :initial="{ opacity: 0, scale: 1, y: 0, x: -125 }"
  :enter="{ opacity: 1, scale: 3.5, y: 0, transition: { duration: 500 } }"
  :click-1="{ x: -350, y: -125, scale: 1.75, transition: { duration: 500 } }"
  class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
>
  <img src="/JOA-M-0033_lick_commitment_and_entropy_over_sessions.png" class="w-64 h-auto" />
</div>

<div
  v-click="1"
  class="absolute top-25 left-125 transition-opacity duration-500 delay-500">
  <img src="/JOA-M-0029_lick_commitment_and_entropy_over_sessions.png" class="w-180 h-auto" />
</div>


<div
  v-click="1"
  class="absolute bottom-10 left-5 transition-opacity duration-500 delay-500">
  <img src="/JOA-M-0030_lick_commitment_and_entropy_over_sessions.png" class="w-120 h-auto" />
</div>

<div
  v-click="1"
  class="absolute bottom-10 right-0 transition-opacity duration-500 delay-500">
  <img src="/JOA-M-0031_lick_commitment_and_entropy_over_sessions.png" class="w-120 h-auto" />
</div>



---
transition: fade 
color: sky 
layout: top-title
---

:: title:: 

# First game between J29 and J31

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

<div class="mt-20 ml--30">

<video
  id="myvideo"
  src="/animation.mp4"
  controls
  preload="auto"
  class="w-[100%]"
/>

</div>

---
transition: fade 
color: sky 
layout: top-title
---

:: title ::

# Some more games between J29 and J31

:: content :: 


<div class="grid grid-cols-2 gap-4 mt-5">
  <v-click>
  <img src="/JOA-M-0029_vs_JOA-M-0033_game_1.png" class="w-full"/>
  </v-click>
  <v-click>
  <img src="/JOA-M-0029_vs_JOA-M-0033_game_7.png" class="w-full"/>
  </v-click>
  <v-click>
  <img src="/JOA-M-0029_vs_JOA-M-0033_game_11.png" class="w-full"/>
  </v-click>
  <v-click>
  <img src="/JOA-M-0029_vs_JOA-M-0033_game_13.png" class="w-full"/>
  </v-click>
</div>



---
transition: fade 
color: sky 
layout: top-title
class: flex flex-col justify-center
---

:: title:: 

# Who is winning and who is more random?

:: content :: 

<div class="ml-20">

  <img src="/JOA-M-0029_JOA-M-0033_smoothed_reward_rate_multiplayer.png" class="opacity-100 w-[90%]"/>

  <img src="/JOA-M-0029_JOA-M-0033_entropy_multiplayer.png" class="opacity-100 w-[90%]"/>

</div>

---
transition: fade 
color: sky 
layout: top-title
class: flex flex-col justify-center
---

:: title:: 

# Randomness and rewards when playing against computer vs. mice 

:: content ::


<img src="/JOA-M-0029_reward_and_entropy_during_solo_vs_social.png" class="opacity-100 w-[75%]"/>

<img src="/JOA-M-0033_reward_and_entropy_during_solo_vs_social.png" class="opacity-100 w-[75%]"/>


<div v-click class="absolute top-[60%] left-180 w-[40%] -translate-y-1/2">
  <img src="/entropy_reward_correlation.svg" class="opacity-100 w-[60%]"/>
</div>




---
layout: top-title-two-cols
color: sky 
transition: fade
---

:: title :: 

# Future plans for mice multiplayer MP

:: left :: 

<div class="mt-30">

<ol class="list-decimal list-inside space-y-2">
  <li v-click="1">Different shaping before multiplayer matching pennies</li>
  <li v-click="2">Asymmetric payoffs</li>
  <li v-click="5">Matching pennies + ephys recordings</li>
</ol>

</div>


:: right :: 




<img v-click="1" src="/solo_two_armed_bandit_to_multiplayer.svg" class="w-[90%]"/>

<div v-click="2" class="flex items-center justify-center gap-4">
  <img src="/symmetric_matching_pennies.svg" class="w-[40%]"/>
  <img src="/asymmetric_matching_pennies.svg" class="w-[40%]"/>
</div>

<SpeechBubble v-click="3" position="t" color="sky" shape="round" maxWidth="210px">
  Nash equilibrium: both play &lt;1/2, 1/2&gt;
</SpeechBubble>

<SpeechBubble v-click="4" class="absolute top-[-380px] left-[200px]" position="b" color="amber" shape="round" maxWidth="200px">
  Nash equilibrium is P1 &lt;1/2, 1/2&gt; <br> P2 &lt;2/3, 1/3&gt;
</SpeechBubble>


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
<div class="grid-item col-span-2">Joanna <i>did all the recordings</i>&nbsp;&nbsp;</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Multiplayer MP</strong></div>
<div class="grid-item col-span-2">Mehul <i>for setting up the multiplayer game</i>&nbsp;<br/>Joanna <i>as mouse whisperer</i>&nbsp;</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Mice</strong></div>
<div class="grid-item col-span-2">JOA-M-0020<br/>JOA-M-0022<br/>JOA-M-0023<br/>JOA-M-0024<br/>JOA-M-0025<br/>JOA-M-0026<br/>JOA-M-0027<br/>JOA-M-0028<br/>JOA-M-0029<br/>JOA-M-0030<br/>JOA-M-0031<br/>JOA-M-0033<br/>JOA-M-0036</div>
<div class="grid-item text-right mr-4 col-span-1"><strong>Supervision</strong></div>
<div class="grid-item col-span-2">Ann<br/>
Jeff</div>
<div class="grid-item col-span-3 text-center mt-80px mb-auto font-size-1.5rem"><strong>The end</strong></div>
</div>

