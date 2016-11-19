# Start using gulp in minutes

### Table of Contents
* [Terminal](#terminal)
* [npm](#npm)
* [Gulp](#gulp)
* [Now what?](#what-now)

## Terminal
You need a terminal to use npm and gulp. Terminal is available out of the box on Linux and OS X. Windows has it as well but cmd and PowerShell is not sustainable for development work. You do not need to be experienced with terminal to function, but learning basics would help.

We'll use cmder as a replacement terminal, however it's a separate software and does not directly replace default terminal.

1. Download and install [cmder](http://cmder.net/).
2. Open cmder. If you have runtime error when starting cmder, you'll probably need to install VS 2015, see [the issue here](https://github.com/cmderdev/cmder/issues/501). If you got different errors, Google/GitHub will get you a fix right away, if not, report it on their repo issues section.
3. Open cmder's settings by right clicking an icon on top-right of window or press `Win+Alt+P`. Navigate to **Startup -> Tasks** on sidebar, select `{cmd::Cmder}` in Predefined tasks and enter `cmd /k "%ConEmuDir%\..\init.bat"  -new_console:d:%USERPROFILE%` as a command, then save. ![Startup -> Tasks](http://i.imgur.com/3bsKj8v.png)
4. Navigate to **Startup** on sidebar and select `{cmd::Cmder}` on *Specified named task* dropdown. [Screenshot](http://i.imgur.com/UAU4bwk.png "Startup settings").
5. You can change background to black like I did in **Colors** or tweak preferences to your liking.
###Deeper look
`cmd /k "%ConEmuDir%\..\init.bat"` is my favorite command application for cmder because it runs linux commands (a little limited though, it's Windows) like [`ls -la`](http://i.imgur.com/xR25Wcq.png), `cat`, `cd`, `touch`, `du`, `cp`, `rm`, and bunch of other commands, obviously with arguments as well. Feels like home right here.

Some people prefer using Powershell as a shell for cmder, which I don't understand, but if you want to, you can set it.

###Basi

If you never used terminal, just learn terminal basics [here](http://cli.learncodethehardway.org/book/), this will help you in long run.

##2. npm
Install [npm](https://nodejs.org/en/download/). This is available for all operating system. During the installation for Windows, be sure 'add to PATH' is included ([image](http://i.imgur.com/lHiNR7p.png)). When installed, restart cmder and enter `npm` in terminal to see if it's working properly, as in it should tell you the usage information. If it does, proceed to the next step.

#####3. gulp
Install gulp globally with this terminal command: `npm install --global gulp`

On completion, download this repo and extract bootstrap-scss-gulp to any folder. Follow the instruction in bootstrap-scss-gulp section on this readme by running `npm install --save-dev` and `gulp`.

#####2. npm
Install [npm](https://nodejs.org/en/download/). This is available for all operating system. During the installation for Windows, be sure 'add to PATH' is included ([image](http://i.imgur.com/lHiNR7p.png)). When installed, restart cmder and enter `npm` in terminal to see if it's working properly, as in it should tell you the usage information. If it does, proceed to the next step.

#####3. gulp
Install gulp globally with this terminal command: `npm install --global gulp`

On completion, download this repo and extract bootstrap-scss-gulp to any folder. Follow the instruction in bootstrap-scss-gulp section on this readme by running `npm install --save-dev` and `gulp`.
