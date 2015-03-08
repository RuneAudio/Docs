# Getting updates

##Standard updates

Between major releases, which are distributed via disk images, new bugfixes or features are introduced and published on [our official repository on GitHub](https://github.com/RuneAudio/RuneUI), on the **main** branch (the production one).

You can check and get such incremental updates from the UI:

 1. go to the **dev section** of the UI, typing [http://runeaudio/dev](http://runeaudio/dev) or [http://runeaudio.local/dev](http://runeaudio.local/dev) in your browser
 2. set the **Dev Mode** as **enabled**
 3. click the **gitpull** button (*Update RuneUI*)
 4. hard refresh the cache of your browser

or in alternative from the terminal, typing this commands:

    cd /var/www
    git pull

As final step, always remember to hard refresh the cache of your browser.

##Nightly builds

Nightly builds are based on the latest development code, which means they may probably be unstable and not documented. As such, your mileage may vary.

Updating to these builds is better suited for more experienced users and developers, although everyone is welcome to test them and provide feedback.

The development is brought forward on different branches of the RuneUI repository:   
[dev branch](https://github.com/RuneAudio/RuneUI/tree/dev) - closer to the main    
[next branch](https://github.com/RuneAudio/RuneUI/tree/next) - more experimental one

These are the required steps to switch from the main branch to another one (the following example refers to the *dev* branch):

 1. delete all the content of /var/www (including hidden files)   
 **DOUBLE CHECK the path before entering the command!**

    `rm -rf /var/www/{*,.*}`

 2. clone the 'dev' branch on your device

    `git clone -b dev https://github.com/RuneAudio/RuneUI.git/ /var/www`

 3. clear the PHP OPcache
 
    `curl -s http://localhost/clear`
 
 4. reboot your device
 
 As final step, always remember to hard refresh the cache of your browser.
