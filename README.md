# DIY-IR

This is a python script for crudely, randomly generating some glitchy [impulse responses](https://en.wikipedia.org/wiki/Impulse_response) for use in convolution reverb plugins. I wrote this code ages ago, and it would benefit from some significant refactoring, commenting, and expansion.

## Quick background:

At the risk of over-explaining, here's a bit of optional reading for context:
Impulse responses are traditionally audio recordings that capture how sound decays within a specific space (or amp or piece of hardware). You feed it a very brief, uniform noise, and treat whatever comes out the other end as "what this space does to sound." This process takes that space and treats it as a [black box](https://en.wikipedia.org/wiki/Black_box) so that you can imitate it without any need to understand _how_ it's happening. A convolution reverb takes the data from that recording (the impulse response) and applies "what this space does to sound" to whatever audio you send it.

But what if we use it the wrong way? In most convolution reverb plugins, _any audio file_ can be loaded in as an impulse response. A recording of a train horn. A cat's meow. Free Bird. None of those are "what a space does to sound," but pretending they are can produce some seriously wacky effects. You can even get into synthesizing your own impulse responses as a way to design the effects you get out of using them.

This python script uses a randomized sequence of noise generation and processing steps to make a weird little garbage .wav file that can be loaded into your convolution verb. These files are generally very harsh if you try to listen to them directly, and their effects in convolution can also vary widely between harsh noise and gentle echoes. I hope you have fun with it, and I hope it inspires you to try making your own "wrong" impulse responses.

## Process

Just run the script from the command line and enter the number of impulse responses you'd like it to generate. The resulting .wav files will be added to the DIY_IR directory. Then just load these into your preferred convolution reverb as impulses and play!

If you're brand new to convolution reverbs, I recommend starting by checking if your DAW has a stock convolution reverb plugin. If not, my next stop would be [the one included in Melda's free effects bundle](https://www.meldaproduction.com/MConvolutionEZ).

## Requirements

scipy, numpy, random, os, re
