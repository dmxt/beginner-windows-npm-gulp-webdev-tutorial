![Gulp logo](http://i.imgur.com/RptJM5Q.png)

# Start using Gulp in minutes

Gulp is a terminal software and using it on Windows can be challenging. This guide will help you to start using Gulp, however this guide is not limited to Windows, it also applies to Linux and macOS users. _The installation process, Step 1, is for Windows users only. Linux and macOS users can go straight to Step 2, because they have the required installation process pre-installed on their system._

### _~ Introduction_

_Do you want your life to be easier and to have more free time? No? Get out and continue being miserable. Oh, was that a yes? Good - please proceed. In thirty minutes to a couple hours (depending on how slow you are) you'll have task automation set up to work for you while you work._

_While you code and hit CTRL+S on one of your file that is watched by Gulp, depending on file format that got modified and saved, if the file format, which got modified and saved, was:_
* **SCSS** - Gulp will compile your SCSS file to CSS, clean unused CSS, add missing css prefixes, optimize your CSS file, minify it then rename it it *.min.css for browser to read (browser cannot read SCSS, hence CSS preprocessor).
* **JS** - Gulp will compress all JS files to one file, beautify it, minify it then rename it to *.min.js
* **Images** - Gulp will optimize your images to smallest possible filesize without quality loss (similar to [Optimizilla](http://optimizilla.com/))

_All only would be done if files are modified and all of these tasks would be done in few milliseconds, then finally refresh your browser so you can see changes you just made on your computer, tablet, phone and other devices. All will be outputted on console so you can watch what just happened. And there's thousands more plugins that are not mentioned in this tutorial, but only for you to find for your own type of workflow, you can find them on [this site](https://www.npmjs.com/), Google or articles by authors who recommend plugins._

_Gulp is configurable, you can add less or more features. Gulp has no task on default. After configuring it to your liking, you'll eventually can't live without it. [You can learn more about how Gulp is useful](#useful-gulp-plugins) and take a look at some of their plugins that could help you in web development._

### Table of Contents
* [Step 1 - Terminal (Windows)](#step-1---terminal-windows)
* [Step 2 - Install npm](#step-2---install-npm)
* [Step 3 - Install Gulp](#step-3---install-gulp)
* [Step 4 - Configuring your own `gulpfile.js`](#step-4---configuring-your-own-gulpfilejs)
* [Can I just test it?](#can-i-just-test-it)

### Context

It will teach you how to:

* What is gulp and why you should start using it?
* Install a proper terminal with syntax highlighting on Windows to replace default cmd.exe (Not required for Linux and macOS)
* Install npm, a package manager. Then install gulp globally.
* Test run a pre-made gulp script for you to test and have a good idea of what gulp does.
* Suggestions and recommendations for gulp plugins if you would like to build your own gulp script that is tailored for your own front-end development workflow.

## Step 1 - Terminal (Windows)
**⚠️ Note: If you do not use Windows, you can go straight to Step 2.** Step 1 is for Windows users to install a UNIX-like terminal that is usable for work - Linux and macOS already have one.

Ok, Windows users, you need a terminal to use npm and Gulp. A functional terminal is available out of the box on Linux and macOS, and Windows has it as well but cmd and PowerShell is not sustainable for in comparison with UNIX console. You do not need to be experienced with terminal to use it properly, but learning some basics would help, such as a few commands like `cd`, `ls`, `mkdir`, `rm`, highlight to copy, and right-click to paste. You can learn it [here](https://www.codecademy.com/learn/learn-the-command-line). It will help you in long run so you won't get stuck at a terminal for minutes to hours over a small mistake. If you don't like this site, [this alternative](https://linuxjourney.com/lesson/less-command) might work.

We will use cmder as a replacement terminal. However, it is a separate software and does not directly replace default terminal, so I make a shortcut to it in Start menu and use a .reg file (to be mentioned later in "Can I just test it?" chapter) to enable context menu feature.

> _Cmder is a software package created out of pure frustration over the absence of nice console emulators on Windows. It is based on amazing software, and spiced up with the Monokai color scheme and a custom prompt layout, looking sexy from the start._

1. Download and install [cmder](http://cmder.net/). I use the full version because it comes with git. Ensure to check the checkbox labelled "Add to PATH" during the installation.

2. Open cmder. If you have runtime error when starting cmder, you will probably need to install VS 2015, see [the issue here](https://github.com/cmderdev/cmder/issues/501). If you got different errors, Google/GitHub will get you a fix right away, but if not, report it on their repo issues section.

3. Go to cmder settings by right-clicking an icon on top-right of window or press `Win+Alt+P`. Navigate to **Startup -> Tasks** on sidebar, select `{cmd::Cmder}` in Predefined tasks and enter `cmd /k "%ConEmuDir%\..\init.bat"  -new_console:d:%USERPROFILE%` as a command, then save. ![Startup -> Tasks](http://i.imgur.com/3bsKj8v.png)

4. Navigate to **Startup** on sidebar and select `{cmd::Cmder}` on *Specified named task* dropdown. [Screenshot](http://i.imgur.com/UAU4bwk.png "Startup settings").

5. You can change the background to black like I did in **Colors** or tweak preferences to your liking.

### Deeper look
`cmd /k "%ConEmuDir%\..\init.bat"` is my favorite command application for cmder because it runs linux commands (a little limited though, because it is a port) such as [`ls -la`](http://i.imgur.com/xR25Wcq.png), `cat`, `cd`, `touch`, `du`, `cp`, `rm`, and more, with arguments. It feels like home.

Some people prefer using Powershell as a shell for cmder, which I don't understand, but if you want to, you can set it.

### Basics

As mentioned previously, if you have never used terminal, you should learn terminal basics [here](https://www.codecademy.com/learn/learn-the-command-line). If you do not like this site, this [alternative](https://linuxjourney.com/lesson/less-command) may be better.

If you have never used cmder before, learning few hotkeys will help you in long run. It may share hotkeys with other terminals. The image below is information about cmder that can be found on their site.

![Screenshot from cmder.net](http://i.imgur.com/XXLp3tn.png)

*[Source: http://cmder.net/](http://cmder.net/)*

## Step 2 - Install npm

We need npm to install Gulp, so we're going to do that.

1. Download and install [npm](https://nodejs.org/en/download/). During the installation, be sure 'add to PATH' is included ([image](http://i.imgur.com/lHiNR7p.png)). 

2. When installed, restart cmder and enter `npm` in terminal to see if it's working properly, i.e it should look like [this](http://i.imgur.com/ef2INPb.png). If it does, proceed to the next step.

## Step 3 - Install Gulp
Finally we reach the Gulp section. This isn't going to be quick and short. Installation will be quick, but configuration for your web development workspace... not really. Trust me, it will be worth it in long run, I will convince you of that.

1. Open a terminal (cmder) and install Gulp globally with this terminal command: `npm install --global gulp`. It should look something like [this](http://i.imgur.com/nLfKlVv.png).

2. Congratulations! You installed Gulp!

Good job. Maybe it was easy, maybe it was not, but you made it. You installed Gulp using a terminal on *Windows*!

## Step 4 - Configuring your own `gulpfile.js`

**You already have Gulp installed, you're set. All you have to do is set it up for your particular work environment, as everyone has different workflow and configurations! Go to Google and find some half-decent Gulp tutorial for beginners to start learning how to configure gulpfile.js, install plugins and make it work for your workflow. You can try [this tutorial](https://css-tricks.com/gulp-for-beginners/) or just use [Google](https://www.google.com/search?q=gulp+tutorial+beginner).**

Try to familiarze yourself with Gulp and gulpfile.js configuration with tutorials, then you can create your own configuration for your development workflow. I listed some useful Gulp pugins below you can use as a reference, however you wouldn't need every single of plugins listed below. Just get plugins that will be useful for your own typical workflow. Most of these plugins have a basic tutorial expecting that you already know how to configure gulpfile.js, that's why knowing how to configure Gulp is important, by referring to above paragraph "Start learning how to configure gulpfile.js".

_**⚠️ Note:** If you have trouble with one of these plugins, ensure that it's not an issue our end. If you can't figure out on what's going on, just check the plugin GitHub repo (rarely, if GitHub repo is not available, try using their available discussion tool) and search or open an issue about the problem. If the plugin is active, you should get responses with solutions quickly._

Gulp is an automatic tool that help you out with several web development related tasks such as: 

* **[browser-sync](https://www.browsersync.io/)** — fires up a local web server for all local devices and browsers to access. `localhost:3000 for own computer, 192.168.x.x:3000/10.0.x.x, etc (ROUTER IP ADDRESS:GULP PORT). If you run another gulp task, it will provide you new port like 3001, 3002, 3003, etc` It auto-refreshes on any file save (and can be configured to watch certain folders), even when you replace an image with new one. You can view your website on your computer, tablet, mobile device and other devices while coding. You can use dev tool freely, while Brackets' live preview would crash if you do that.
* **[gulp-sass](https://www.npmjs.com/package/gulp-sass)** — compiles SCSS to CSS files before BrowserSync loads, highly configurable. You'll need [gulp-plumber](https://www.npmjs.com/package/gulp-plumber) to stop Gulp from crashing if SASS produces any error.
* **[gulp-concat](https://github.com/contra/gulp-concat)** — it is normal to have several separated external dependencies files like jQuery, Modernizr, and more, along with linking them all in HTML/PHP files. With concat, it can compile all of these js files to one vendor.js file.
* **[gulp-uglify](https://github.com/terinjokes/gulp-uglify)** — remember how we compiled several js files to one vendor.js file? Let us minify it, too! Remember, it is all done automatically. Every time you edit one of js file, gulp-concat and gulp-uglify will repeat the procedure and make it ready.
* **[gulp-rename](https://www.npmjs.com/package/gulp-rename)** — instead of having minified vendor.js, let's rename it to vendor.min.js. Automatically, of course.

Here's a list of some more Gulp's plugins that can be useful for you. Any more than that, you will need to use a search engine or [npmjs.com](npmjs.com).

### HTML
* **[gulp-htmlmin](https://www.npmjs.com/package/gulp-htmlmin)** — minifies HTML files
* **[htmlhint](https://www.npmjs.com/package/gulp-htmlhint)** — HTML linter/hinter

### CSS
* **[cssbeautify](https://www.npmjs.com/package/cssbeautify)** — CSS beautifier
* **[gulp-uncss](https://www.npmjs.com/package/gulp-uncss)** — cleans unused CSS files (run before CSS autoprefixer, optimizer, minifier and renamer if you have these)
* **[gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer)** — CSS autoprefixer
* **[gulp-csslint](https://www.npmjs.com/package/gulp-csslint)** — CSS linter

#### CSS optimizer, minifier and renamer
**[gulp-csso](https://github.com/ben-eb/gulp-csso)** — this is an advanced CSS optimizer that optimize from

```
a {
font-family: Arial;
font-style: italic;
font-size: 14px;
line-height: 18px;
font-weight: bold;
background-image: url('example.png');
background-color: red;
background-size: cover;
background-repeat: no-repeat;
}
```
to

```
a {
font: italic bold 14px/18px Arial;
background: red url('example.png') no-repeat / cover;
}
```

Impressive, especially for newer developers who don't know all shortified CSS .

_Notice: If you choose to add the above `gulp-csso` plugins, the following plugins below are meant to be run after this plugin, in order._
* **[gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css)** — minifies chosen CSS files.
* **[gulp-rename](https://www.npmjs.com/package/gulp-rename)** — if you minified CSS files, use this plugin to rename your minified files from `*.css` to `*.min.css`.

### Images
* **[gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin)** — compresses images to lower filesize without quality loss
* **[gulp-spritesmith](https://www.npmjs.com/package/gulp-spritesmith)** — converts images to a spritesheet and outputs CSS variables

### Others
* **[gulp-watch](https://www.npmjs.com/package/gulp-watch)** — a task that watch files, and when a file get modified or updated, it will run specified Gulp tasks. It is an essential Gulp plugin and the tutorial you find will probably mention it.
* **[gulp-notify](https://www.npmjs.com/package/gulp-notify)** — sends system error notification when Gulp task fails.

## Can I just test it?

Sure, I have a repo for you to see what happens when you run Gulp.

1. Download this folder in [my repo](https://github.com/dmxt/bootstrap-scss-gulp-starter-kit/tree/master/bootstrap-scss-gulp).

This repo has standard bootstrap CSS and JS, minimal index.html, blank main.scss and configured gulpfile.js with following Gulp plugins:
* **BrowserSync** — automatically refresh in browser when the watched file is saved.
* **SCSS compiler** — automatically compiles SCSS to CSS on save. It compiles `/scss/main.scss` to `/css/main.css` so HTML file can read it.
* **Plumber** — prevents Gulp crash on SCSS error.

2. Navigate to this folder /gulp/ with your terminal with `cd` (Windows only: instead of navigating, you can add cmder to context menu [with a .reg file](https://gist.github.com/jojobyte/66c8346ed8948b9b395f). Of course, you need to edit paths to your path to cmder.exe file in a .reg file before running it.)

3. Install dependencies by running `npm install --save-dev` in terminal. It reads gulpfile.js, then downloads and installs necessary files for Gulp to run. (You need to be in 'gulp' folder to do this)

4. Finally, run `gulp`. It will take several seconds to boot up a web server, boot up these scripts and then it will be up and running. You also need to be in Gulp folder to do this.

5. Any changes you make will be auto-refreshed and applied to the site. You can write regular CSS in .scss file and SCSS compiler will compile it to other CSS file and BrowserSync fires again and browser reloads to display the change. If Gulp crashed, just run `gulp` again.

If you use Bootstrap, you can use [my repo](https://github.com/dmxt/bootstrap-scss-gulp-starter-kit/tree/master/bootstrap-scss-gulp) as a base to start a new website. 

### Configure and embrace Gulp! 💪
