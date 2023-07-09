---
title: "Website with Hugo"
date: 2023-03-28T18:08:10+05:30
layout: "simple"
summary: "Tips for creating a website the Congo theme on Hugo"
---
{{< katex >}}

The instructions/tips on this blog are specific to using **Hugo v0.111.3 on Windows**, **VS Code**, and hosting on **Github Pages**. I am not an expert at hugo. This website is my first proper web development project. But I hope to teach you everything I learnt while creating this specific personal/research/blog website. I am not writing out all the exact instructions here. But I have linked all the websites and tutorials I have used to create my website. I hope this saves your time (because I had to watch a lot of pointless tutorials). Also, if this is your first website project, don't be intimidated by this. It can be pretty painful initially, but after setting up everything, you only need to add stuff to your page. 

## Installing Hugo and Git

- **Hugo**
    - Check the latest released version here: [Hugo Releases](https://github.com/gohugoio/hugo/releases)
    - There is an excellent playlist on YouTube by Mike Dane called [Hugo - Static Site Generator | Tutorial](https://youtube.com/playlist?list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3). For installing Hugo on windows, watch [Tutorial 2](https://youtu.be/G7umPCU-8xc).
    - Make sure to do the "Modify path variable step" given in the tutorial. 
- **Git**
    - [Download for Windows](https://git-scm.com/download/win). I downloaded "64-bit Git for Windows Setup"

## Why the Theme Congo?

- There are a bunch of [Themes on Hugo](https://themes.gohugo.io/) you can choose from. I chose Congo because I really liked the style.
- [Congo](https://github.com/jpanther/congo) is a simple, elegant, and powerful theme and has a lot of [documentation](https://jpanther.github.io/congo/docs/). You can find almost everything you'll need here.
- It supports things like \\(\LaTeX\\) using \\(\KaTeX\\) ([Documentation for \\(\KaTeX\\)](https://katex.org/docs/supported.html)). This was important for me since I need it for posts about my research. I don't know if this is easy to implement on websites, but I didn't want bother. I like the convenience of congo.
- For documentation about \\(\LaTeX\\), see [Mathematical Noatation](https://jpanther.github.io/congo/samples/mathematical-notation/) and [Shortcodes](https://jpanther.github.io/congo/docs/shortcodes/#katex). To write stuff in \\(\LaTeX\\), simply write {{</* katex */>}} at the top of the page (or anywhere for that matter). Use the following syntax:

   ```
    {{</* katex */>}}                                   % This has to be written, but can be written anywhere within the document
    \\(\LaTeX\\)                                    % This is the same are writing things enclosed by $ $ in LaTeX
    \\(f(a,b,c) = (a^2+b^2+c^2)^3\\)                
    $$G_{\mu\nu} = 8\pi G T_{\mu\nu}$$              % This produces an equation aligned at the center
    ```
    **Output:**

    \\(f(a,b,c) = (a^2+b^2+c^2)^3\\)
    $$G_{\mu\nu} = 8\pi GT_{\mu\nu}$$

## Creating your website project
- To use the theme Congo, after downloading Hugo, follow the instructions in [Congo Installation](https://jpanther.github.io/congo/docs/installation/)
    - Watch [Tutorial 4](https://youtu.be/sB0HLHjgQ7E) to understand what each folder means. For a general set of instructions, check out [Hugo quickstart](https://gohugo.io/getting-started/quick-start/). 
- The step called [Set up theme configuration files](https://jpanther.github.io/congo/docs/installation/#set-up-theme-configuration-files) might feel weird because you are deleting the config.toml file, but you have to do it this way. 
- Before I go into the specifics of creating a website like this, I want to give you a few tips for using VS Code. This might be obvious to a lot of you, but I want to share them anyway.

## General Tips for VS Code

- Press **Ctrl + Shift + v** to open a preview of the markdown page. Then drag that window to the right to open it. Now you can preview the website in real-time without starting the hugo server. Also, VS Code synchronizes the markdown file and the preview. If you scroll on the markdown file, the preview page also scrolls accordingly.

- If you have multiple markdown files open and a preview page open to the right side, you can press **Ctrl + Tab** to switch between the different markdown files and the preview will automatically change to the preview of the new markdown file.

- To get more more screen space, press **Ctrl + b** to hide the file explorer. You can also close the terminal for now using **Ctrl + `**. Just open it (using the same shortcut) when you want to create a new file or to start/stop the hugo server.

## Tips for Creating the Website

- The amazing thing about Congo is that the documentation has everything. Just follow the steps in [Getting Started](https://jpanther.github.io/congo/docs/getting-started/)

- To get your homepage like mine, Go to the params.toml file and change layout = 'profile'. 

- The most important folder for you is the content folder. A very nice explanation is given in [Tutorial 6](https://youtu.be/0GZxidrlaRM).

- Create a _index.md file in the content folder. You can do this in the terminal by typing 
    ```
    hugo new _index.md
    ```
    You don't have to write hugo new content/_index.md as it is already understood by hugo that _index.md should be made inside the content folder. But if you want to make an _index.md file inside a folder in the content folder, then you have to specify the path. See the CV section later in this blog.

- The stuff you write in this _index.md file is what is going to be displayed on the page. For example, the code for my homepage is written in the _index.md file in the content folder (content/_index.md). The stuff on my CV page is written in the _index.md file inside the content/cv folder (content/cv/_index.md). 

- The best reference page is the [exampleSite](https://github.com/jpanther/congo/tree/dev/exampleSite) on the Congo github. I understood so much about the layout of congo from the [content](https://github.com/jpanther/congo/tree/dev/exampleSite/content) folder over there because guess what, this content folder contains all the markdown files for the actual [congo website](https://jpanther.github.io/congo/). (Except for one thing which I have discussed later)

- Say you want to learn how make a website similar to the [Users](https://jpanther.github.io/congo/users/) page. Well now you can go to [Users page on Github](https://github.com/jpanther/congo/tree/dev/exampleSite/content/users) and see all the additions you need to make!

- If you are feeling lazy, you can just copy the code from my github too. I have also copied code from other congo users. Other people's code is actually a great source to learn from. 

- Have a look at how other people have organized everything in the content folder. Look at the things they have written in the _index.md files, and the other markdown files and compare it with the actual website. This helped me out a lot.

- If you ever need to write html code for something and don't want to google the syntax, an easy method is use a markdown to html website (or ChatGPT)

## Some weird things about Hugo and Congo

**Hugo Pluralizes Titles**

- On my website, I have a page called 'Research' which you can find in the menu at the top. When I first clicked on it, the title of that page was 'Researches'. Like any other programmer, you first assume that you did something wrong, and not the actual software. It took me a long time to think that maybe hugo is messing this up somehow. Thankfully, I found this [Stackoverflow question](https://stackoverflow.com/questions/55951933/why-hugo-makes-nav-items-plural). Yes, for some weird reason, Hugo pluralizes titles.
- To fix this, go to the config.toml file and type:
    ```
    pluralizelisttitles = false
    ```
**Congo Article Thumbnails**

- Say you want to learn how to display your articles on your blog page the same way congo has done for their [Samples](https://jpanther.github.io/congo/samples/) page with thumbnails. As I mentioned before, I went to the [Samples page on Github](https://github.com/jpanther/congo/tree/dev/exampleSite/content/samples) and added a jpg file in the correct location, the same way they have done. And guess what, the thumbnails didn't appear.

- This one is pretty stupid because I was not able to find anything about it in the documentation. After searching this issue on the [congo discussions page](https://github.com/jpanther/congo/discussions), I found this [comment](https://github.com/jpanther/congo/discussions/315#discussioncomment-4103266) by jpanther, the creator of Congo. Turns out, the name of that jpg file must have the word `thumb` at the beginning.



## Tips for making my CV page

- To get the button at the top, check out [Button Documentation](https://jpanther.github.io/congo/docs/shortcodes/#button).
  ```
  {{/* button href="/cv.pdf" target="_self" >}}
  Download CV
  {{</* /button */>}}
  ```
- The biggest problem I faced when I made this CV website was aligning   parts of the same line to left and right. For example, look at this line: 

  <p style="text-align:left;"><strong>Bachelor of Technology - Engineering Physics<span style="float:right;">2018 - 2022</strong></span></p>

     I wanted the years to be written nicely to the right side. But apparently, there is no simple way to do this. Markdown does not have a function like \hfill in \\(\LaTeX\\). And of course, \\(\KaTeX\\) does not support only this one space-fill function of \hfill, yet. For me, the best way to tackle this was to write an html code for this:

    ```
    <p style="text-align:left;">
        <h3 id="bachelor-of-technology-engineering-physics">Bachelor of Technology - Engineering Physics
        <span style="float:right;">
            2018 - 2022</h3>
        </span>
    </p>
    ```
    Yes. I wrote this ugly html code everywhere in my CV page. Please help me if you of a more elegant method to do this.