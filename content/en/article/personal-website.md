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
## Prerequisites
1. Basic Unix terminal commands
2. Basic Git knowledge (add, commit, main, submodules)
3. Familiarity with Markdown syntax

## Resources
* [Git Tutorial (~15min)](https://www.youtube.com/watch?v=USjZcfj8yxE)
* [Git Tutorial (~1h)](https://www.youtube.com/watch?v=8JJ101D3knE)
* [Markdown Basic Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [Basic Terminal Commands](https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/)
* [Papermod Documentation](https://github.com/adityatelange/hugo-PaperMod)

## Getting Started

1. Install Code Editor: [VScode](https://code.visualstudio.com/), [Pycharm](https://www.jetbrains.com/pycharm/) 

2. Install Package Manager: [Homebrew](https://brew.sh/)

   ```shell
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

3. Install Static Site Generator [Hugo](https://gohugo.io/)

   ```shell
   brew install hugo
   ```
   
   * Follow the directions on the terminal output
   
4. Install Github [CLI](https://cli.github.com/manual/installation) (if you want to deploy your website)

   ```shell
   brew install gh
   ```

   * Once installed, run `gh auth login` and follow the directions on the terminal

## Create your Website

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

2. Open the project in VSCode

   ```shell
   open .
   ```

   * This will open the current folder in finder
   * Right click on `config.yml` and open it in VScode
   * Then open the folder in VScode

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
         url: /about
         weight: 2
       - name: Projects
         url: /projects
         weight: 3
       # - name: Contact
       #   url: /contact
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
   hugo server -D
   ```

   * Copy the web server address and open it in your browser
   * By default it is `localhost:1313`

## Creating Content

1. Run this command in the VScode Terminal

   ```shell
   hugo new about.md
   ```

   * Here you are creating a new [markdown](https://www.markdownguide.org/getting-started/) file that you can edit in VSCode or another code/markdown editor

2. Copy and paste the following markdown into your `about.md` after the front matter to get familiar with the basic syntax

   ```markdown
   # Heading 1
   ## Heading 2
   ### Heading 3
   #### Heading 4
   
   Normal Text
   
   *italic text*
   
   **bold text**
   
   ### Unordered List
   1. first
   2. second
   3. third
   
   ### Unordered List (bullets)
   - first
     - level 2
       - level 3
   - second
   - third
   
   ### Task list
   - [ ] Task 1
   - [ ] Task 2
   - [ ] Task 3
   
   ### Table
   | Column1    | Column2    | Column3    |
   |---------------- | --------------- | --------------- |
   | Item1.1    | Item2.1    | Item3.1    |
   | Item1.2    | Item2.2    | Item3.2    |
   ```

3. Creating a project

   ```shell
   hugo new projects/first-project.md
   ```
   
   * Here, you are creating a new folder called `projects` in your `content` folder.
   * Within the `projects` folder, you are creating a file called `first-project.md`
   * So now, the *Projects*

### Adding Images to Homepage

1. Create a new folder named `img` in the `static` folder in your website directory

2. Search and save as an image from the internet

3. Drag the image into your `img` folder

4. In your `config.yml`, edit the value of your `imageUrl` on line 29

   ```yaml
   params:
     profileMode:
       enabled: true
       title: "Your Name"
       subtitle: "👷 Who you are | 💻 Major Student | 📚 NYU Shanghai"
       imageUrl: "img/your-image-name.jpeg" # <--- TODO: Edit This
       imageTitle: "Profile Picture"
       imageWidth: 200
       imageHeight: 200
       buttons:
         - name: Contact Me
           url: "/contact"
         - name: Github
           url: "https://github.com"
   ```

### Adding Images to Content

1. Save as a new image into your `static/img` directory using the steps listed above

2. Open `first-project.md`

3. Edit the front matter so that it looks like this

   ```yaml
   ---
   title: "First Project"
   date: 2022-11-04T13:20:02+08:00
   draft: true
   cover:
       image: img/nyu_shanghai.jpeg
       alt: 'NYU Shanghai Qiantan Campus'
       caption: 'This is the caption'
   ---
   ```

   * You are editing the frontmatter to add a cover photo to your content

## Build and Deploy Your Website

### Build Your Site

1. Run the Hugo build command in terminal simply by running

   ```
   hugo
   ```

   * This will create a `public` folder which will contain a "condensed" version of the website which will be important later

### Push Your Website to Github

1. Create a new Github repository

2. Connect your local project with your remote repository

3. Git add, commit, and push to your remote repository

   ```shell
   git add .
   git commit -m "first commit"
   git branch -M main
   ### You will want to copy the following part from github ###
   git remote add origin https://github.com/your-account/uba-website-workshop.git
   git push -u origin main
   ```

### Deploy Your Website with Netlify

1. Go to [netlify.com](https://www.netlify.com/) and create an account with your Github credentials
1. Configure the following setttings before deploying your site
   * Branch to deploy: `main`
   * Build Command: `hugo`
   * Publish directory: `public`
1. Then click on *Site Settings* and click *Change site name* to change the site name to a name of your choice
1. Then click on the site link, and now your website is live!

## Additional Resources
* [Get started with Hugo](https://gohugo.io/getting-started/quick-start/)
* [Hugo Youtube Tutorial (~47min)](https://www.youtube.com/watch?v=hjD9jTi_DQ4&t=913s)
* [Github CLI Installation Guide](https://cli.github.com/manual/installation)
