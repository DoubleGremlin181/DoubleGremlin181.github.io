---
title: "How to create an interactive README for your GitHub profile"
layout: post
date: 2020-07-17 12:37
tag:
- tutorial
- github
- readme
- python
image: /assets/images/posts/github-profile-interactive-readme/gray-metal-cubes-decorative-1005644.jpg
headerImage: true
description: "A tutorial on how to make your GitHub profile standout by having an interactive README"
category: blog
author: kavishhukmani
externalLink: false
---

This is a **NO BS** tutorial on how to create interactive READMEs for your GitHub Profile.

I implemented an interactive game of Tic-Tac-Toe on my [profile](https://github.com/DoubleGremlin181/) and will be using that as an example for this tutorial while keeping it open enough to let you implement your ideas.

### Prerequisites
 - A GitHub account
 - Intermediate knowledge in any scripting language. I will be using Python.
 - Basic Markdown and HTML for formatting your README.
 - Basics of GitHub Actions.

### Let the games begin
1) Create a new GitHub repo with the same name as your username.
`https://github.com/username/username`


2) Create an account on [Link Click Counter](https://www.linkclickcounter.com/) using a (temporary) email ID. This is a free service which will track any clicks on the URLs in realtime. Create as many links as needed.


3) Create a new file in the language of your choice and scrape the results from `https://www.linkclickcounter.com/userAccount.php`. Store the values in a JSON file. The number of new clicks between two runs of the program is the difference between the old and new values. Don't forget to store your email ID and password as environment variables.

<details>
<summary>
  Expand gist
</summary>
<script src="https://gist.github.com/DoubleGremlin181/674da407cfc6feedfcf2210caf558644.js"></script>
</details>


4) The next thing to do is to implement your idea. Use the values calculated from the previous step to make your program interactive.

<details>
<summary>
  Expand gist
</summary>
<script src="https://gist.github.com/DoubleGremlin181/280ef9af0b01996d6df85b2644ba5791.js"></script>
</details>


5) The last part of the program is to create the template for your README file. The magic lies in using hyperlinks for Link Click Counter URLs behind images

`[![Alt Text](Image link)](Link Click Counter URL)`

<details>
<summary>
  Expand gist
</summary>
<script src="https://gist.github.com/DoubleGremlin181/7fbe5ec91465c60d45e4b28d4d9cf7ba.js"></script>
</details>


6) Create a `.yml` file in `.github/workflows/` to automatically run your code as desired. For scheduling runs use cron jobs. I would also recommend caching any dependencies.

<details>
<summary>
  Expand gist
</summary>
<script src="https://gist.github.com/DoubleGremlin181/2c8e9f73bdc0820eed8dde70522429ba.js"></script>
</details>



7) Commit and push all your files
```
git add -A
git commit -m "Your commit message"
git push origin master
```


8) Add your email ID and password as Secrets to your repo on GitHub
>Settings -> Secrets -> New Secret


### And you're done.

<!-- Place this tag where you want the button to render. -->
<a class="github-button" href="https://github.com/DoubleGremlin181/DoubleGremlin181" data-icon="octicon-star" aria-label="Star DoubleGremlin181/DoubleGremlin181 on GitHub">Star</a> my repo if you found this tutorial helpful.

<a href="https://twitter.com/intent/tweet?screen_name=2gremlin181&ref_src=twsrc%5Etfw" class="twitter-mention-button" data-show-count="false">Tweet to @2gremlin181</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> with your profiles and ideas


<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>
