---
title: "Personal Website Workshop"
date: 2022-11-02
draft: false
author: ["Lawrence Lim"]
categories: ["UBA"]
tags: ["HTML","CSS"]
ShowToc: true
ShowReadingTime: true
ShowBreadCrumbs: true
---
## Getting Started

1. Install Code Editor: [VScode](https://code.visualstudio.com/)

2. Install Package Manager: [Homebrew](https://brew.sh/)

   ```shell
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

3. Install Static Site Generator [Hugo](https://gohugo.io/)

   ```shell
   brew install hugo
   ```

* Follow the directions on the terminal output

## Create your Website

0. Run the following commands in your terminal

1. Create Hugo Project

   ```shell
   hugo new site quickstart -f yml
   ```

2. Install Theme

   ```shell
   cd quickstart
   git init
   git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
   ```

3. Open the project in VSCode

   ```shell
   open . -a Vscode.app
   ```

4. Copy the following code into your `config.yml`

   ```yaml
   baseURL: ""
   languageCode: en-us
   title: Your New Hugo Site
   theme: PaperMod
   
   menu:
     main:
       - name: Home
         url: /
         weight: 1
       - name: About
         url: /
         weight: 2
       - name: Contact
         url: /
         weight: 3
       # - name: Projects
       #   url: /projects
       #   weight: 3
       # - name: Articles
       #   url: /articles
       #   weight: 4
   
   params:
     profileMode:
       enabled: true
       title: "Your Name"
       subtitle: "👷 Who you are | 💻 Major Student | 📚 NYU Shanghai"
       imageUrl: "img/your_profile_picture.jpg"
       imageTitle: "Profile Picture"
       imageWidth: 200
       imageHeight: 200
       buttons:
         - name: Contact Me
           url: "/contact"
         - name: Github
           url: "https://github.com/larry-lime"
   
     socialIcons:
       - name: email
         url: "mailto:netid@nyu.edu" #Ex: mailto:ll4715@nyu.edu
       - name: twitter
         url: "" #Ex: https://twitter.com/lawrence_lim__
       - name: github
         url: "https://github.com/larry-lime"
       # - name: linkedin
       #   url: "https://www.linkedin.com/in/lawrence-rx-lim/"
       # - name: telegram
       #   url: "https://t.me/larrylime4132"
   ```

5. To start a local server, in the VSCode terminal run:

   ```shell
   hugo server
   ```

   * Copy the web server address and open it in your browser
   * By default it is `localhost:1313`

## Create Content

## Push 

## Resources

* [Hugo Youtube Tutorial (~47min)](https://www.youtube.com/watch?v=hjD9jTi_DQ4&t=913s)
* [Get started with Hugo](https://gohugo.io/getting-started/quick-start/)

