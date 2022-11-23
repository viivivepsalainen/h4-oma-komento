# h4-oma-komento
palvelinten hallinta s22 homework 4

I started by updating/upgrading my local system's repository list with command **apt update** and then **apt upgrade**. 

a) Hei komento! Tee järjestelmään uusi "hei maailma" -komento ja asenna se orjille Saltilla. Liitä raporttiisi orjan 'ls -l /usr/local/bin/' tulosteesta ainakin se rivi, jolla näkyy uuden komentotiedostosi oikeudet.

First, I opened the nano -text editor, where I made the script (moimaailma). The script basically only says **echo "hei maailma"** (and the #!/bin/bash at the top).

Here are the permissions of the script, which I changed right with the command **sudo chmod 755 moimaailma**:

![newtry1](https://user-images.githubusercontent.com/118457367/203637808-79dea863-bf23-47a6-8a3e-b09f084c28df.jpg)

Then I tried that the command works:

![newtry2](https://user-images.githubusercontent.com/118457367/203638286-8687809d-d306-41dc-ae8c-edc575d4cc5c.jpg)
 
 After that I made the file (**sudo nano /srv/salt/moimaailma/init.sls**) so that we can transfer/copy the command to minions/slaves, which looked like this:
 
 ![newtry4](https://user-images.githubusercontent.com/118457367/203638522-4a1aadd7-43be-499e-aeb6-654f367dd715.jpg)
 
 After that, with the command **sudo salt viivi state.apply moimaailma** I copied the command to my minion, which succeeded: 

![newtry3](https://user-images.githubusercontent.com/118457367/203638546-48c0a925-b7d3-4d65-9c88-b666a15b08c7.jpg)


b) whatsup.sh. Tee järjestelmään uusi komento, joka kertoo ajankohtaisia tietoja; asenna se orjille. Vinkkejä: Voit näyttää valintasi mukaan esimerkiksi päivämäärää, säätä, tietoja koneesta, verkon tilanteesta...

So as on the task a, I started with opening the text editor and made the script (which gives you todays date and time, kerner-version and how long has the system been running) there, which looked like thiS:

![newtry5](https://user-images.githubusercontent.com/118457367/203639898-2b2560ff-89fd-49b0-818d-f407995b88b0.jpg)

And then I changed the scripts rights with the same command that was used in task a. I also moved the script to the /usr/local/bin dictionary. 

Then I checked that the script works: 

![newtry6](https://user-images.githubusercontent.com/118457367/203640096-80e38d3a-72dc-4a3b-a76a-de15aa7bad4f.jpg)

After that, just like in the task a, I made the file (with nano text editor, **sudo nano /srv/salt/tietoa/init.sls**) that will copy the command to minions, which looked like this: 

![newtry7 1](https://user-images.githubusercontent.com/118457367/203641487-2ac7d858-b54e-4fbb-98ee-9dfca2d64a01.jpg)

Then I copied the command/applied the state to the minion, which succeeded: 

![NEWTRY7](https://user-images.githubusercontent.com/118457367/203641692-e48a8beb-2b89-4f3e-ace5-2b33e6ed3320.jpg)


 
 c) hello.py. Tee järjestelmään uusi komento Pythonilla ja asenna se orjille. Vinkkejä: Hei maailma riittää, mutta propellihatut saavat toki koodaillakin. Shebang on "#!/usr/bin/python3". Helpoin Python-komento on: print("Hei Tero!")
 
 First I installed python with command **sudo apt install python3**. 
 
 Then with the command **nano moikku.py** I made a basic script which had the python sheband at the top and said **print("moi viivi")**. I also tested that it worked, and moved it to the /usr/local/bin dictionary and changed the permissions to 755, just like in task a & b. 
 
 Then I made the init.sls file to the /srv/salt/moikku/ dictionary (which I created with the command **mkdir -p /srv/salt/moikku**), that copied the command to the minions, which looked like this: 
 
 ![newtry8 1](https://user-images.githubusercontent.com/118457367/203646155-456262d1-d4d4-4834-813f-c21126defeee.jpg)

Then I moved the moikky.py python file to the /srv/salt/moikku dictionary.

After that I copied the command to minion, which succeeded:

![NEWTRY8](https://user-images.githubusercontent.com/118457367/203646685-5aa7ceca-6df2-459a-afcb-574b8f660c1f.jpg)

 
d) Laiskaa skriptailua. Tee kansio, josta jokainen skripti kopioituu orjille.

 I have no idea how to do this. 

e) Intel. Etsi kolme loppuprojektia joltain vanhalta kurssitoteutukselta. Kuvaile projektit tiiviisti, viittaa ja linkitä alkuperäiseeen raporttin. Tässä alakohdassa ei tarvitse vielä kokeilla mitään koneella, vaan voit kuvailla niitä oheismateriaalin perusteella.

1) The first one was from 2018 fall, written by Silja Gupta. Silja decided to do salt-module which will install 3D-blender and configure the basic settings, so that the user can use the blender more efficiently. It will also run testrender in the "back" and turn that into a picture file. After that it will also set the picture as the computers wallpaper. 
This module is made for new blender users, who want to install it fast and smooth. 
https://siljagupta.wordpress.com/2018/05/10/palvelinten-hallinta-h6-blender-moduli/

2) The second one was also from 2018 fall, written by Juho Isosomppi. Juho decided to do the module about how to setup a Samba-server with the module. First you setup the master-minion architecture, then create passwords, then add the passwords to the pillar, then restart master, running disk for minions, adding samba users through the ssh -connection. After all this you can map the samba dictionaries to windows -computers straight by adding a network drive. Then there were also directions how to connect with linux. 
https://github.com/jisosomppi/mgmt/blob/master/README.md#moduli

3) The last one was from 2017 fall, written by Mikko Hyvärinen. Mikko decided to build a module, that will install a daemon. First Mikko did all the basic commands, then started creating the "real" module. There he created some new dictionaries and gave commands. It seemed like he couldn't push the files to github (because some permissions weren't right (?)). 
https://mikkohyvarinen.wordpress.com/2017/10/29/palvelinten-hallinta-h1-rakenna-moduli-joka-asentaa-demonin/

e) Lukua, ei luottamusta. Kokeile yhtä kohdassa d-Intel löytämääsi modulia koneella. Tämä on infraa koodina, joten luottamusta ei tarvita. Voit lukea koodista, mitä olet ajamassa.

I didn't get what I was supposed to try. In the module projects there wasn't any guide how to try them on my computer, so I'm just gonna try tomorrow at the class to run/try something.
