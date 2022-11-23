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

![script](https://user-images.githubusercontent.com/118457367/203610911-c619cd77-b240-46ee-9958-9c6b905a2a67.jpg)

![HMM](https://user-images.githubusercontent.com/118457367/203611135-686d92e1-5bdf-457b-8018-0782241d766e.jpg)
 
 And then I changed their permissions/rights too, with the command **sudo chmod +x tieto.sh, tieto2.sh** but I just couldn't apply the state to the slaves, it gave me the same error:
 
 ![nowork](https://user-images.githubusercontent.com/118457367/203611555-c60e36d1-9b6a-4f99-a514-9232d33dfc6f.jpg)
 
 c) hello.py. Tee järjestelmään uusi komento Pythonilla ja asenna se orjille. Vinkkejä: Hei maailma riittää, mutta propellihatut saavat toki koodaillakin. Shebang on "#!/usr/bin/python3". Helpoin Python-komento on: print("Hei Tero!")
 
 First I installed python with command **sudo apt install python3**. 
 
 Then with the command **nano testi.py** I made the script that looked like this: 
 
 ![scriptpyttoni](https://user-images.githubusercontent.com/118457367/203624902-b1ff177a-a2b4-4e94-b6d1-7dd48ef849ec.jpg)

 And the outcome of the script looked like this (I checked out that it works with the command **python3 testi.py** ):
 
 ![pytonulos](https://user-images.githubusercontent.com/118457367/203624962-455fe09a-0b7f-4cf5-9f17-8cd365d274e4.jpg)

Again I couldn't apply it, it gave the same error.

d) Laiskaa skriptailua. Tee kansio, josta jokainen skripti kopioituu orjille.

First I copied (with **command sudo cp testi.py /srv/salt/scripts**) some old scripts from the previous tasks to this new dictionary (that I created with command **sudo mkdir /srv/salt/scripts**):

![SKRIPTULIT](https://user-images.githubusercontent.com/118457367/203628351-2b47c2e5-0bf5-437a-bde0-f756c07782aa.jpg)

But once again, I couldn't apply the script to the slave. I'm figuring out tomorrow why. 

e) Intel. Etsi kolme loppuprojektia joltain vanhalta kurssitoteutukselta. Kuvaile projektit tiiviisti, viittaa ja linkitä alkuperäiseeen raporttin. Tässä alakohdassa ei tarvitse vielä kokeilla mitään koneella, vaan voit kuvailla niitä oheismateriaalin perusteella.



e) Lukua, ei luottamusta. Kokeile yhtä kohdassa d-Intel löytämääsi modulia koneella. Tämä on infraa koodina, joten luottamusta ei tarvita. Voit lukea koodista, mitä olet ajamassa.
 
