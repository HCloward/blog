---
title: "Deploying a Hugo site to GiHub pages"
date: 2020-05-31
tags: ["SSG", "Git", "Hugo"]
draft: false
---

I am mostly writing this so that I won't forget for the next time I want to deploy a static site to GitHub pages. I should say a static site that is not a Jekyll site because a Jekyll site is different and more of an automated process since <a href="https://pages.github.com/">GitHub Pages are powered by Jekyll</a>. 

With Hugo, there are a few more steps to accomplish to get your site deployed to GitHub pages. 

If you are downloading the repo from another SCM like GitLab, clone the repo onto your local computer. Create a GitHub repo for your content files.  Then update the remote on your local copy of the repo with the git command `git remote set-url origin <repo-url>` so it points to the new GitHub repo. Stage, commit, and push your files to GitHub. 

Create a separate GitHub account using the following naming pattern - <GitHub_username>github.io. 

---
**NOTE**
Fun tip I learned while doing this is that you can add additional text to the end of the repo name pattern and it will still work. For example - <GitHub_username>github.io-blog will work. This is important because you can't have more than one repo with the same name and you may have multiple Hugo sites you want published to GH pages. 

---

Then you will add the <GitHub_username>.github.io repo as a submodule to the repo with the project files using the git command `git submodule add https://<GitHub_username>/<GitHub_username>github.io.git`.

---
**NOTE**
You will get a warning that you are cloning into an empty directory, because it does not have any files as of yet. That is ok because we are going to add them soon enough. 

---

In your `config.toml` file, add a `publishDir` attribute and enter the name of the repo where you are sending your files, "<GitHub_username>.github.io". Also, update the `baseURL` attribute to match the URL for your new site, "https://<GitHub_username>/<GitHub_username>.github.io".

Run a new production build for your site in your outermost directory using the build command for Hugo - `hugo`. Your files should now be in the new <GitHub_username>.github.io folder. Switch into the folder with the bash command `cd <GitHub_username>.github.io`. Stage, commit, and push your files to origin master. 

Once your files have been push up to the correct GitHub repo, you need to turn on the GitHub Pages feature in the Settings tab of your repo. Select the Source as the master branch. GitHub will present you with the new URL where you can visit your site. Then you will need to wait a few minutes for everything to get built. 
