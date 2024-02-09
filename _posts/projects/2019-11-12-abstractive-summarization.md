---
layout: post
title: "Abstractive summarization"
subtitle: ""
category: 'Projects'
---

As a proof of concept, developed a abstractive summarization system to capture data from various sources and generate a brief and comprehensive summary. Worked on PreSumm, which uses a modified BERT encoder and a regular transformer decoder with different optimizers for efficient fine-tuning. While the encoder was able to capture the representations of salient contexts, the decoder lacked in generating cohesive text. Improved it by using GPT-2 as the decoder. The GPT-2 based decoder was fine-tuned to use BERT encoder representations to generate new text. 