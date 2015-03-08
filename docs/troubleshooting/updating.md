# Getting updates

##Standard updates

Major releases are distributed via [downloadable disk images](http://www.runeaudio.com/download/). In between major releases, we publish bugfixes and new features to [our official repository on GitHub](https://github.com/RuneAudio/RuneUI). They are located on the **main** branch (the production one). 

You can check for and install these updates from the UI:

 1. go to the **dev section** of the UI, typing [http://runeaudio/dev](http://runeaudio/dev) or [http://runeaudio.local/dev](http://runeaudio.local/dev) in your browser
 2. set the **Dev Mode** to **enabled**
 3. click the **gitpull** button (*Update RuneUI*)
 4. hard refresh the cache of your browser (ctrl + F5)

Alternatively, you can do this from the terminal:

    cd /var/www
    git pull

As final step, always remember to hard refresh the cache of your browser. (ctrl + F5)

##Nightly builds

Nightly builds are based on the latest development code, which means they are probably unstable and definitely not documented. As such, your mileage may vary.

Updating to these builds is better suited for more experienced users and developers, although everyone is welcome to test them and provide feedback.

Currently, development is progressing along different branches in the RuneUI repository:
[dev branch](https://github.com/RuneAudio/RuneUI/tree/dev) - closer to the main branch, this is likely to be merged with main on a regualr basis
[next branch](https://github.com/RuneAudio/RuneUI/tree/next) - a more experimental one, typically intended to be the next version of RuneAudio

These are the required steps to switch from the main branch to another one (the following example refers to the *dev* branch):

 1. delete the contents of /var/www (including hidden files)   
 **DOUBLE CHECK the path before entering the command!**

    `rm -rf /var/www/{*,.*}`

 2. clone the 'dev' branch on your device (notice the `-b dev`)

    `git clone -b dev https://github.com/RuneAudio/RuneUI.git/ /var/www`

 3. clear the PHP OPcache
 
    `curl -s http://localhost/clear`
 
 4. reboot your device
 
 As final step, always remember to hard refresh the cache of your browser. (ctrl + F5)
