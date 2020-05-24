---
title: "Rubiks Cube Gym"
layout: post
date: 2020-05-24 15:52
tag:
- reinforcement learning
- openai gym
- python
image: /assets/images/posts/rubiks-cube-gym/twitsy-puzzles.jpg
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "An OpenAI Gym environment for various twisty puzzles"
category: project
author: kavishhukmani
externalLink: false
---
After my internship ended prematurely due to the COVID-19 pandemic, I decided to use my newfound free time to learn new things and hone my skills. On the programming side of things, this has been reinforcement learning. I have been fascinated by reinforcement learning and OpenAI since I first read about it. OpenAI has led to some significant breakthroughs in recent years. From [Gym](https://gym.openai.com/), which standardised environments and can be used with all major RL libraries to the [OpenAI Five](https://openai.com/blog/openai-five/), a team of five individual bots which beat the reigning champions OG at DotA2 to [GPT-2](https://openai.com/blog/better-language-models/) which completely revolutionised the NLP field.

I am also a big fan of the Rubik's Cube and various twisty puzzles. Combining these two, I have created an OpenAI Gym environment for twisty puzzles. Currently, it supports the 2x2 Rubik's Cube with more puzzles such as the Pyraminx and Skewb to come in the near future. I had initially intended to create one for the 3x3 Rubik's Cube which everyone knows and loves, but the number of possible states is far too large, 43 quintillion or 4.3 x 10^19, making it impractical to use.

The 2x2 Rubiks Cube is available in three different environments, each for different reward methods. These include [layer by layer](https://www.speedsolving.com/wiki/index.php/Layer_by_layer), a beginners method and the [Ortega](https://www.speedsolving.com/wiki/index.php/Ortega_Method) method, which is commonly used by speedcubers.

This project has been a fantastic learning experience, and I plan to use it to do some Reinforcement Learning using it in the near future(stay tuned for that).

The code is available on my [Github](https://github.com/DoubleGremlin181/RubiksCubeGym) along with some more technical information in the README file.

I would love to see how anyone ends up using it. As always, I am open to suggestions and feedback.


Photo Credits: [Gerwin Sturm](https://www.flickr.com/photos/scarygami/4214513596/in/photostream/)
