---
layout: post
title: "Speech Translation"
subtitle: "End-to-end active speech translation system."
categories: 'Projects'
---

As a proof of concept, developed and deployed a bi-directional Mandarin-to-English active translation pipeline. The pipeline consisted of three components speech-to-text, neural machine translation and text-to-speech.  Worked with Mozilla's DeepSpeech 2 for speech recognition, output of which was processed by Fairseq's convolutional encoder + RNN decoder neural machine translation model and then converted back to audio using Tacotron 2 for speech synthesis.