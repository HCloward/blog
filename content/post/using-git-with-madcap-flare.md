---
title: "Using Git with MadCap Flare"
date: 2019-01-06
tags: ["git", "MadCap Flare"]
draft: false
---

When I first started at my current job, the documentation team was using Subversion as the source control for their MadCap Flare projects. To access Subversion they used a graphical user interface(GUI) called TortoiseSVN. The MadCap Flare project was very large and so checking out the project to make updates took about half an hour. Furthermore, while one person on the team was making updates, the other people on the team could not. This was not the most ideal situation. 

<img src="../../frustrated.jpg" class="article">

Within the first few weeks of my new job my boss informed me that her boss wanted our team to eventually begin using Git and store our repository on GitHub, where the developers were storing the product's code base. I had a little experience with Git since I had been investigating it for my team at my last position. We had tried to use a GUI, SourceTree, but because MadCap Flare adds metadata/XML markup updates to topics behind the scenes that are not displayed in the wysiwyg editor we kept having merge conflicts. So, I tried using the interface Flare provides, but there were too many issues so we stopped the investigation.

<img src="../../download.png" class="article">

Since I had some experience, my boss appointed me the job of creating a plan for switching from SVN to Git and I was happy to accept the challenge. This time I did not want to use SourceTree, but GitHub had created it's own GUI, the <a href="https://desktop.github.com/">GitHub Desktop App</a>, so I created a plan using the GitHub Desktop App. However, as I found out later this application would not work because it was decided that our repo was to be a folder added to the main code base. Because of this we would each need to fork the main repo and then clone that repo to our local machines. The reason this was a problem is that at the time the GitHub Desktop App did not have an option for changing upstreams. So we were unable to pull from each others' forks for peer reviews. So I needed a different way for us to access the repos.

<img src="../../octocat.jpg" class="article" id="octocat">

It was at this time that the Git guru at our company told me that it was better to use the command line to avoid things happening behind the scenes with a GUI. I was resistant as my colleagues were not likely to enjoy using the command line, but eventually I realized this was the only solution. So I wote up a plan using Git Bash. Git Bash is a BASH emulation used to run Git from the command line. The BASH emulation behaves just like the "git" command in LINUX and UNIX environments. As it turned out this plan ended up being the go-to plan for our team. I wrote up a series of commands for forking the repo, cloning the repo, then pulling branches from different upstreams, and pushing up to the remotes. These commands worked for quite a while, but the complication of having our code tied into the main product code became too cumbersome. Eventually, it was decided that the documentation team should have a separate GitHub repo.

<img src="../../linuxPenguin.png" class="article" id="penguin">

So I rewrote our instructions with the same command line interface, since it was working before. The team adjusted just fine and we now use Git Bash to pull down branches and review updates. There is a lot of fear around using the command line, and I can understand that fear since it is very powerful. However, if you know the right commands and you are careful with the more destructive ones, it is a much less complicated way to use Git. If you are using MadCap Flare and looking into using Git, I have written some <a href="https://docs.google.com/document/d/15RSIg3iOaKLIylv1DeQ0cDWDS_5yIYOrPv5DiPrDnIs/edit?usp=sharing" >instructions for forking, cloning and pulling from the remote repo using Git Bash</a>. Please use what you can and email me with any questions.

