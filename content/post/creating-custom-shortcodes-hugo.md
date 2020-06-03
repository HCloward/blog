---
title: "Creating custom shortcodes for Hugo when you are using a theme"
date: 2020-05-31
tags: ["SSG", "Hugo"]
draft: false
---

This is another post I am writing because I want to remember how to do it and the documentation I needed to understand this concept was not easily found, so this is a reference for me for later. :pushpin:  The <a href="https://gohugo.io/templates/shortcode-templates/">Hugo docs covering custom shortcodes</a> is good, but it assumes you are not using a theme and I am for my blog site.

I wanted to create some admonitions in posts for my blog; however, the theme I am using, Minimal, does not include shortcodes for admonitions. I know it is possible to have shortcode admonitions for Hugo, so I decided to see if I could add my own shortcode.

First, I went to the Hugo site and looked in the sample themes to see some examples and determine how the theme creators added them. I looked at <a href="https://themes.gohugo.io/ace-documentation/">Ace documentation</a> and got the basic understanding for how to set up the admonition, but I wanted a different kind of look to my admonitions. Also, Ace documentation depended on Bootstrap and I didn't really feel like adding <a href="https://getbootstrap.com/">Bootstrap to my project</a>.

Afterwards, I found the Hugo <a href="https://themes.gohugo.io/hugo-book/">Book theme</a> and really liked what they called <a href="https://themes.gohugo.io/theme/hugo-book/docs/shortcodes/hints/">"hints"</a>. I decided to use their styling; however, they were using <a href="https://sass-lang.com/">Sass</a>, a CSS preprocessor and while I totally think that is the way to go, I didn't really feel like updating my current normal CSS files to Sass. 

So I needed a way to convert the Sass just for the "hints", but what I found was they were using variables that I had to find the variables first, otherwise I was getting a warning when I attempted to convert the Sass. Eventually, after finding the correct variable, I was able to convert the section of Sass I needed to CSS using a <a href="https://www.sassmeister.com/">Sass play area site</a>, which I then copied to my CSS file located in my static/css folder. 

I also needed to add the layouts/shortcodes folders to my project since I didn't have them yet. I added these folders at the same level as my content folder, being careful to use the exact naming and capitalization as indicated in the Hugo documentation. Then I added an admonition.html file to the layouts/shortcodes folder and pasted in the shortcode that the Hugo Book Theme used, with minor updates since I reworded mine to be "admonitions" instead of "hints".

Then I tested my updates by putting an note admonition into one of my posts and then did a local build using the build command `hugo server`, and it worked!  But I still wasn't satisfied because there were only three choices for admonitions: info, warning, and danger. I wanted an additional admonition for "tips". So I found a good hexidecimal color for my "tips" addition and converted it to rgba for the background, and added the CSS class to my stylesheet. Now I have admonitions I can use in my posts. :sunglasses:
