---
author: "ChocoShell"
title: "Creating a Static Site Hugo Blog"
image: "https://images.pexels.com/photos/577585/pexels-photo-577585.jpeg"
image_caption: "Photo by Kevin Ku from Pexels: https://www.pexels.com/photo/data-codes-through-eyeglasses-577585/"
draft: false
date: 2023-08-18
description: "Logging the process of how I created this blog."
tags: ["hugo", "github actions", "github", "golang"]
archives: ["2023"]
---

Last Updated: 2023-08-19

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I chose hugo since I heard it was great for static site building and I heard about it again on the Talk Python To Me podcast.
I had never used Go before either, so it was nice to see a new technology. I'm hosting it on the github page for my account. Here is the guide for [github pages](https://pages.github.com/).  
Hugo made it very easy to deploy the site via github actions. My `hugo.yaml` workflow is copied directly from the [official hugo example](https://gohugo.io/hosting-and-deployment/hosting-on-github/#.github/workflows/hugo.yaml). The template language reminds me a lot of django, so making some html optional was straightforward.
I tried a few different themes but finally settled on Blonde because of its ease of use to set up and the fact that thumbnails would show up on blog posts. Blog posts should catch people's eyes the moment they see them and it seems more difficult on a home page of all text.


### Technologies Used

- Github for hosting
- Github Actions for site deploying
- Hugo (and Go) for static site creation
- [Blonde Hugo Theme](https://themes.gohugo.io/themes/blonde/)
  - npm as a dependency to the theme
  - tailwind as a dependency to the theme

### Setting up my local environment

I started this project on a new windows machine. These are the tools and dependencies used.

Tools:
- [Visual Studio Code](https://code.visualstudio.com/)
  - [Tailwind Extension](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
  - [Markdown All in One Extension](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [cmder](https://cmder.app/)

Dependencies:
- Git (installed by cmder)
- [Node](https://nodejs.org/en)
- [Go Programming Language](https://go.dev/)
- [Hugo](https://gohugo.io/)


### Creating my Repo

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I started by creating a new repo for the blog.  The github pages guide recommends using this convention `<username>.github.io` for the repo name. Once created, we can initialize it with an empty `README.md` file so that we can change the repo settings to prepare it for the github pages deploy.  We can now go to our repo and click the `Settings` tab at the top, followed by the `Pages` tab under the `Code and Automation` section and finally, changing the `Source` from `Deploy from as branch` to `Github Actions`. Now, github will read from our `.github/workflows/` folder to see how it should deploy the site.

![Github Actions Settings Page](/img/github_pages.png)

### Observations

- config.toml and hugo.toml are the same thing. hugo.toml is newer
- Hugo templating is similar to django. Easy for me to make changes


### Changes made to Blonde theme locally

- Made the Disqus area under every post optional by checking if the `disqusShortname` (unique identifier for each site) was present or not.
- Added a caption under the blog post image so I can add attributions.


### Things I would Revisit

- Spent a lot of time trying to get `nodist` to work on windows but couldn't. It is a node version manager. It kept giving me the latest node version but would never update its version of npm. Might revisit on my next node project.


### Future Work
- :white_square_button: Create a Real Name for the Blog
- :white_square_button: Update About Page
- :white_square_button: Update Contact Page

### Closing Thoughts

This blog is supposed to be for my general projects. I mostly do python with a focus on automation.  My last project was automating a card game mode.  I plan to upload ML/AI focused projects soon, dabbling into NLP and general MLOps.
