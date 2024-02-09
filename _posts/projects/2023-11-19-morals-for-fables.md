---
layout: post
title: "Generating Morals for Fables"
subtitle: "Unlocking Wisdom's Codes: Decoding Morals in Fables with NLP"
category: 'Projects'
links: 
---
Fables are short narratives that teach us valuable lessons in the form of morals; understanding these morals is important because they are the central messages of their fables. This thesis explores the challenging task of understanding the morals of fables using natural language processing. We propose features, focused on the characters and events of a fable, that include both semi-structured subject-predicate-object triplets, as well as with the Story Intention Graph; we develop the first fully automated pipeline for building SIGs from narratives. Using the triplet features, we train a neural classification model to label a fable with one of twelve abstract categories of morals, demonstrating that neural networks are capable of extracting moral information. Using SIGs, we tackle the more challenging, open-ended task of generating a fable's moral from scratch. We develop graph-to-sequence models for this task, proposing a novel global meta-node for initializing a sequence decoder from a graph encoder. Our best-performing model achieves state-of-the-art results for the task of moral generation.