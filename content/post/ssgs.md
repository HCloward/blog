---
title: "Using an SSG for Technical Documentation"
date: 2019-02-21
tags: ["SSG", "Git", "Jekyll"]
draft: false
---
Recently my team has been looking to update our tooling for a couple of reasons. The main reason is our current tool, <a href="https://www.madcapsoftware.com/products/flare/">MadCap Flare</a>, has become difficult to work with since our project has greatly increased in size. We have well over 2,000 topics and because of our hefty project size, sometimes Flare will time out and adding things like links can become cumbersome. We had discussed simply breaking the project into several Flare projects and then somehow merging the projects upon build time, but since we use Git as our source control and we use conditional text throughout the project, that process could get very complicated.

<img src="../../pages.jpg" class="article">

Around the time we started discussing our Flare issues, I had started transferring our standards and process documents from a Microsoft Word document on OneDrive into a Static Site Generator (SSG) on GitHub pages. Initially we were going to move the files into Flare, but I had been following <a href="https://idratherbewriting.com/">Tom Johnson's blog</a>  and noticed he had used <a href="https://idratherbewriting.com/about-jekyll/">Jekyll</a> to create a <a href="https://idratherbewriting.com/documentation-theme-jekyll/">technical documentation theme</a> and I was curious to give an SSG a try.

<img src="../../jekyll.png" class="article" id="penguin">

At first I was overwhelmed by all of the things that were involved that I had not spent much time using before like command line tools, node packages, markup, templating languages, and yaml configuration files. I spent a lot of time simply looking over Tom Johson's project files on GitHub to see how everything was structured and to understand how things were linked. I read through his thorough documentation and finally began the conversion process. While a bit of a struggle at first, eventually I started to really enjoy using Jekyll and I especially liked how quickly I could view my updates and how seamlessly it integrated with Git and GitHub (<a href="https://heathercloward.github.io/process-standards/index.html">my process/standards doc project on GitHub pages</a>).

<img src="../../octKittyJekyll.jpg" class="article" id="penguin">

Since I had enjoyed the process so much I recommended our team look into converting our main documentation files to an SSG. My boss's boss was intrigued so I started doing some research. Unfortunately, Jekyll, the SSG I had been using and was familiar with was <a href="https://www.youtube.com/watch?v=2RCqk-nEn90">known for being slow</a> when it included a large amount of files. This problem was the very problem we were trying to solve with Flare, so I started looking into alternatives and was flabbergasted to discover there are <a href="https://www.staticgen.com/">100s of SSGs</a> available.

<img src="../../overwhelmed.jpg" class="article">

I tried to narrow down the choices and ran into several issues. Since there are not many SSGs that were made for technical documentation as a primary use case, often the features we rely on are not available. Features like conditonal text, variables, versioning, and nested navigation are just not standard on many of the more popular SSGS. Furthermore, the documentation for many of the SSGs is highly technical and my team members were intimidated and expressed concerned about link management and context sensitive help.

<img src="../../questioning.png" class="article" id="penguin">

Not one to give up easily, I persevered with the assumption that there had to be an SSG that would meet our needs. At this time I did a proof-of-concept with <a href="https://docusaurus.io/">Docusaurus</a> and fell in love with all of its documentation-centric features (<a href="https://heathercl.gitlab.io/manuals-site/">my sample site on GitLab pages</a>). However, heartbreakingly, I found that without an integrated templating language like <a href="https://shopify.github.io/liquid/">Liquid</a>, there was not an easy way to use conditional text. Furthermore, my team were still very reluctant to use a text editor as their main tool for writing the help.

<img src="../../docusaurus.png" class="article" id="penguin">

At this time I have narrowed the field down to two products I'd like to try. First, I started looking into flat-file CMSes and ran across <a href="https://getgrav.org/">Grav</a>, which I will probably try out next, though it seems a bit more complicated than an SSG, and will not offer all of the benefits, it does offer a user-friendly admin GUI. I am also planning to look into <a href="https://antora.org/">Antora</a>, an SSG written specifically for technical documentation that has a lot of great features for technical writers including the ability to use conditional text and add versions easily. More to come in my next blog article.

<img src="../../grav.png" class="article" id="penguin">
