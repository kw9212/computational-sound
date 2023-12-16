# computational-sound

[Video Link](https://youtu.be/E8ASgE1CrDc)

## Why Did I Choose Live Coding for My Final Project?
This live coding performance is also the final project for my Computational Sound class, which I am particularly passionate about. Before delving into the final project details, I want to explain why I chose live coding as my project theme. From my perspective, Digital Sound Processing (DSP) seems to be the mainstream in computer music, with live coding appearing more as an applied study. DSP feels foundational, whereas live coding, to me, embodies the creative application of these principles. My initial, somewhat vague, fantasy about computer music equated it with live coding, imagining the creation of music through unique computer-generated sounds, distinct from traditional instruments. The first class of Live Coding introduced me to [Sam Aaron's impressive performance with Sonic Pi](https://www.youtube.com/watch?v=0dgZf3Com44&t=1355s), solidifying my decision to focus on this theme for my final project.

## Challenges

However, choosing Live Coding posed two challenges: First, how could I infuse my creative methodology into Live Coding? Second, how could I compensate for my limited knowledge of music theory?

To address the first challenge, I decided to use media sound effects as samples. This idea was partly inspired by Stephen Spielberg's 'Ready Player One.' In this virtual world, a plethora of familiar characters and elements come together harmoniously, despite originating from disparate works. This led me to ponder: **If samples from various media are meticulously arranged and tuned to live performance sounds, could they not blend seamlessly into a cohesive musical piece?** This thought was the genesis of my final project. After discussing it with my professor during office hours and receiving positive feedback and valuable advice, I felt confident in my chosen direction.

My lack of formal training in music, primarily focusing on singing, acting, and dancing, posed the second challenge. I struggled with understanding chord progressions, melodic shifts, and compositional elements. Live coding, being performance-centric, does not necessitate deep musical knowledge, but a good ear for sounds, beats, rhythms, and melodies is essential. My approach was hands-on: watching numerous videos, observing how performers crafted sounds and beats, and experimenting with structures and samples. This became the cornerstone of my practice, dedicating 1-2 hours daily since the project's inception.

During the Final Proposition Presentation, I showcased three works-in-progress, featuring themes from Indiana Jones, Terminator 2, and Age of Empires 2. However, technical issues prevented me from playing the samples during the presentation. Post-class, the professor's feedback led to two significant project modifications: focusing on beat- or rhythm-oriented samples and limiting sample lengths to 0.5 to 1 second. These changes allowed greater flexibility in sample selection, compensating for my limited music theory knowledge.

## Choosing Samples

The heart of my project revolved around three selected samples: [the cannon sound](https://www.youtube.com/watch?v=zYJSoLNj_iA) from Age of Empires 2's Cannon Galleon, [the whip sound](https://www.youtube.com/watch?v=joMQ4A1n4NU) from Indiana Jones, and [the magic wand sound](https://www.youtube.com/watch?v=cEsKCVaOsWM) from Harry Potter. These were creatively incorporated into various parts of the performance, such as using the cannon sound as a kick drum, the whip as a hi-hat, and the wand sound as both melody and effect.

Live coding's beauty lies in its improvisational nature. While performers might have stylistic preferences or musical inclinations, the essence of live coding is creating on-the-spot performances. My performance comprised various elements, starting with the kick drum and weaving through the samples, bassline, chords, synth, pad, and melody, culminating in additional effects and a secondary pad.

Rather than explaining each line, I'd like to focus on parts that I want to emphasize more. For instance, I'll delve into how I implemented class concepts in a live coding context and utilized samples.

## Composition of the Performance
My performance comprised the following elements: 
- kick drum
- sample 1 (cannon)
- snare
- hi-hat
- sample 2 (whip)
- bassline 
- chord
- synth
- pad
- melody
- sample 3 (wand)
- additional effects
- an additional pad.

The **kick drum** forms the foundation of the music. I'm fond of the robust bass sound it produces.

- **LFO Effect Creation:** I used the **`range`** and **`mirror`** methods for this. The **`range(50, 80, 0.5)`** creates values that modulate a sound parameter, similar to an LFO. The **`.mirror`** method makes these values oscillate back and forth, creating dynamic changes in the sound's character over time. For instance, it generates a sequence like 50, 50.5, 51, ..., 79.5, 80, 79.5, ..., 50.

This modulation is applied to the **cutoff parameter** of the kick drum:

```ruby
sample :bd_tek, amp: fade_in.look * kick_vol, cutoff: kick_cutoffs.look
```

The **first sample**, the cannon sound from "Age of Empires 2," was added alongside the kick drum. When I stumbled upon this sound, I realized it could serve as a bass element akin to a kick drum.

For the **snare part**, I aimed for a spatial and echoing effect by adding reverb and echo to the break loop.

In the **hi-hat part**, I used a resonant high-pass filter (**`:rhpf`**) to shape the sound. The **`noise_hats`** section employs slicer and high-pass filter effects to create a rhythmic noise pattern, mimicking a hi-hat.

The **whip sound** from "Indiana Jones" was chosen for its unique effect and its similarity to a hi-hat's crisp sound. Surprisingly, it blended well, adding a distinct character to the performance.

The **bassline** was challenging due to my limited musical knowledge. I invested a lot of time practicing and researching live coding performances. The use of an FM Synth provided a rich, expressive sound.

As I developed the bassline, I aimed to evoke a funky feel. Similarly, the **chord part** was a process of trial and error, ultimately leading to a funky sound.

The **synth and pad** sections were crafted using **`:saw`** and **`:dpulse`** synths for a bright and punchy sound. The effects were fine-tuned to blend harmoniously with the rest of the music.

For the **melody part**, I chose higher-pitched notes to complement the high pitch of the third sample, adding a bitcrusher effect for a unique, retro feel.

The **third sample** was the magical sound from "Harry Potter: The Prisoner of Azkaban," used during Lumos Maxima spell practice. Combined with the melody, it brought a touch of mystery to the performance.

To enhance this mysterious ambiance, I introduced another effect using the **`ambi_runner_land`** sample, complemented by a reverse effect and a pad sound using the **`:hollow`** synth.

Finally, I organized the samples and instrument layers for clarity. I developed an on/off control for each sample and a volume control, akin to a boolean variable, allowing for independent management of each sample.

## Computational Sound, Live Coding, and My Journey in Computer Music

Interestingly, my journey into computer science was initially sparked by music. When the pandemic curtailed live performances, my interest in composition grew, leading me to explore how computers create sound, and eventually to studying computer science. Revisiting computer music through live coding felt like a return to my roots and reignited my passion for computer science. This experience reminded me of my initial foray into this field and the excitement of discovery. Just as I cherish the moment I entered computer science through computer music, I believe this project, and my encounter with live coding, will remain a significant milestone in my ongoing journey in the field.
