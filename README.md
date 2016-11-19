![Gulp logo](http://i.imgur.com/RptJM5Q.png)

# Start using gulp in minutes

**Note: If you don't use Windows, you can skip Step 1 and proceed from Step 2.**

*~ Introductionary ~*

*Are you a web developer that use Windows? Do you want your life to be easier and have more free time? No? Get out and continue being miserable. Is that yes? Good, please proceed, in 30 minutes to couple hours (depending how slow you are) you'll have automatic task all set up that will work for you while you work. It will help you to finish projects much faster and more effectively. [You can learn more about how gulp is useful](#why-gulp-is-useful) and take a look at some of their plugins that would help you in web development.*

### Table of Contents
* [Terminal](#terminal)
* [npm](#npm)
* [gulp](#gulp)
* [Why gulp is useful?](#why-gulp-is-useful)
* [Can I just test it?](#can-i-just-test-it)

## Terminal
You need a terminal to use npm and gulp. Terminal is available out of the box on Linux and OS X. Windows has it as well but cmd and PowerShell is not sustainable for development work. You do not need to be experienced with terminal to function, but learning basics would help. Just few commands like `cd`, `ls`, `mkdir`, `rm`, and stuff, you can learn it [over here](https://www.codecademy.com/learn/learn-the-command-line), it will help you in long run so you won't get stuck in terminal for minutes to hours over a stupid `ls` command. If you don't like this site, this [alternative](https://linuxjourney.com/lesson/less-command) might work.

We'll use cmder as a replacement terminal, however it's a separate software and does not directly replace default terminal.

> *Cmder is a software package created out of pure frustration over the absence of nice console emulators on Windows. It is based on amazing software, and spiced up with the Monokai color scheme and a custom prompt layout, looking sexy from the start.*

1. Download and install [cmder](http://cmder.net/). I use full version because I use git. Ensure to check a checkbox "Add to PATH" during the installation.

2. Open cmder. If you have runtime error when starting cmder, you'll probably need to install VS 2015, see [the issue here](https://github.com/cmderdev/cmder/issues/501). If you got different errors, Google/GitHub will get you a fix right away, if not, report it on their repo issues section.

3. Go to cmder settings by right clicking an icon on top-right of window or press `Win+Alt+P`. Navigate to **Startup -> Tasks** on sidebar, select `{cmd::Cmder}` in Predefined tasks and enter `cmd /k "%ConEmuDir%\..\init.bat"  -new_console:d:%USERPROFILE%` as a command, then save. ![Startup -> Tasks](http://i.imgur.com/3bsKj8v.png)

4. Navigate to **Startup** on sidebar and select `{cmd::Cmder}` on *Specified named task* dropdown. [Screenshot](http://i.imgur.com/UAU4bwk.png "Startup settings").

5. You can change background to black like I did in **Colors** or tweak preferences to your liking.

### Deeper look
`cmd /k "%ConEmuDir%\..\init.bat"` is my favorite command application for cmder because it runs linux commands (a little limited though, it's Windows) like [`ls -la`](http://i.imgur.com/xR25Wcq.png), `cat`, `cd`, `touch`, `du`, `cp`, `rm`, and bunch of other commands, obviously with arguments as well. Feels like home right here. I suspect it's because I installed full version that included git, and of course, git includes linux commands.

Some people prefer using Powershell as a shell for cmder, which I don't understand, but if you want to, you can set it.

### Basics

Like mentioned before, you never used terminal, just learn terminal basics [here](https://www.codecademy.com/learn/learn-the-command-line). If you don't like this site, this [alternative](https://linuxjourney.com/lesson/less-command) could work out.

I assume that you've never used cmder before, learning few hotkeys will help you in long run. It may resemble other terminals. Image below is information for cmder that can be found on their site.

![Screenshot from cmder.net](http://i.imgur.com/XXLp3tn.png)

*[Source: http://cmder.net/](http://cmder.net/)*



## npm

We need npm to install gulp, so we're going to do that.

1. Download and install [npm](https://nodejs.org/en/download/). During the installation, be sure 'add to PATH' is included ([image](http://i.imgur.com/lHiNR7p.png)). 

2. When installed, restart cmder and enter `npm` in terminal to see if it's working properly, i.e it should look like [this](http://i.imgur.com/ef2INPb.png). If it does, proceed to the next step.

## gulp
At last, we're on gulp section. This isn't going to be quick and short. Installation would be quick, but configuration to configure for your web development workspace... not really. Trust me, it will worth it in long run, I'll convince you.

1. Open a terminal (cmder) and install gulp globally with this terminal command: `npm install --global gulp`. It should look something like [this](http://i.imgur.com/nLfKlVv.png).

2. Congratulations! You've installed gulp!

Good job. Maybe it was easy, maybe it wasn't, but you made it. You installed gulp on terminal on *Windows*!

## Why gulp is useful?
Gulp is an automatic tool that help you out with several web development related tasks such as: 

* **[BrowserSync](https://www.browsersync.io/)** — fires up a local web server `(localhost:3000 for own computer, 198.168.1.7:3001 for other devices, etc)` for all local devices and browsers to access. It auto refresh on any file save (configurable of what folder to watch), even when you replace an image with new one. You can view your website on your computer, tablet, mobile device and other devices while coding. You can use dev tool freely because Brackets' live preview would crash if you do that.
* **[gulp-sass](https://www.npmjs.com/package/gulp-sass)** — compiles SCSS to CSS files before BrowserSync load, very configurable to your preference. You'll need [gulp-plumber](https://www.npmjs.com/package/gulp-plumber) to stop gulp from crashing if SASS threw any error or any other type of error.
* **[gulp-concat](https://github.com/contra/gulp-concat)** — it's usual to have several separated external dependencies files like jQuery, Modernizr, and more, plus you have to link them all in HTML/PHP files. With concat, it can compile all of these js files to one vendor.js file.
* **[gulp-uglify](https://github.com/terinjokes/gulp-uglify)** — remember how we compiled several js files to one vendor.js file? Let's minify it, too! Remember, it's all done automatically. Every time you edit one of js file, gulp-concat and gulp-uglify will repeat the procedure and make it ready.
* **[gulp-rename](https://www.npmjs.com/package/gulp-rename)** — instead of having minified vendor.js, let's rename it to vendor.min.js. Automatically, of course.

There is many more useful plugins you can use to make your web development life easier. Remember, it doesn't only apply to js files, it also apply to css files, image files (auto image minifier, auto sprint, etc) and other files. 

**You already have gulp installed, you're set. All what you have to do is set it up for your work environment since everyone else have it different! Go to Google and find a gulp tutorial for beginners to start learning how to configure gulpfile.js, install plugins and make it work for your workflow.**

## Can I just test it?

Sure, I have a repo for you to see what happens if you run gulp. It has BrowserSync and SCSS compiler. 

1. Grab my [repo](https://github.com/dmxt/bootstrap-scss-gulp-starter-kit/tree/master/bootstrap-scss-gulp). It's a standard bootstrap CSS + JS, nearly blank index.html, SCSS file and configured gulpfile.js in /gulp/.

2. Navigate to this folder /gulp/ with your terminal with `cd` (or instead of navigating, you can add cmder to context menu [this way](https://gist.github.com/jojobyte/66c8346ed8948b9b395f). Of course, you need to edit out path to your cmder.exe file in these .reg files before running it.)

3. In terminal, go to folder gulp in this repo and type down `gulp`. It will take several seconds to boot up a web server, boot up these scripts and then it will be up and running. 

4. Any changes you make will be auto-refreshed and applied to the site. You can write regular CSS in .scss file and SCSS compiler will compile it to other CSS file and BrowserSync fires again and browser reloads to display the change.
