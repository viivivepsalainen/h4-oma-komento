# h4-oma-komento
palvelinten hallinta s22 homework 4

a) Hei komento! Tee järjestelmään uusi "hei maailma" -komento ja asenna se orjille Saltilla. Liitä raporttiisi orjan 'ls -l /usr/local/bin/' tulosteesta ainakin se rivi, jolla näkyy uuden komentotiedostosi oikeudet.

First, I opened the nano -text editor, where I made the script (heimaailma.sh), which looked like this:

![entiiämitäteenp100](https://user-images.githubusercontent.com/118457367/203609904-d80c04e4-232f-4877-a9e1-d22d55b405a5.jpg)
 
And this is the helloworld.sh script: 

![script2](https://user-images.githubusercontent.com/118457367/203610009-2106122f-b162-4d50-8c27-65c29d25b7ef.jpg)

After that I changed both files rights with the command <chmod +x heimaailma.sh, helloworld.sh>, so that I can access them.

I tried to apply the script several times for the slave, but it always gave me this same error:

![bigproblemo](https://user-images.githubusercontent.com/118457367/203610131-b9b2bd54-9891-4fb7-ac0c-57e9fce1b1ca.jpg)

So after many hours of trying to google the answer and configuring some settings I just couldn't apply the command to the slave. 

b) b) whatsup.sh. Tee järjestelmään uusi komento, joka kertoo ajankohtaisia tietoja; asenna se orjille. Vinkkejä: Voit näyttää valintasi mukaan esimerkiksi päivämäärää, säätä, tietoja koneesta, verkon tilanteesta...

So as on the task a, I started with opening the text editor and made the script (which gives you todays date and time, kerner-version and how long has the system been running) there, which looked like thiS:

![script](https://user-images.githubusercontent.com/118457367/203610911-c619cd77-b240-46ee-9958-9c6b905a2a67.jpg)

![HMM](https://user-images.githubusercontent.com/118457367/203611135-686d92e1-5bdf-457b-8018-0782241d766e.jpg)
 
 And then I changed their permissions/rights too, with the command <sudo chmod +x tieto.sh, tieto2.sh>, but I just couldn't apply the state to the slaves, it gave me the same error:
 
 ![nowork](https://user-images.githubusercontent.com/118457367/203611555-c60e36d1-9b6a-4f99-a514-9232d33dfc6f.jpg)
 
 c) hello.py. Tee järjestelmään uusi komento Pythonilla ja asenna se orjille. Vinkkejä: Hei maailma riittää, mutta propellihatut saavat toki koodaillakin. Shebang on "#!/usr/bin/python3". Helpoin Python-komento on: print("Hei Tero!")
 
 
