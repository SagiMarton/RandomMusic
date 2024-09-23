Hogyan használd a modot
1. Klónozd le a repot a documents/Europa Universalis IV/mod mappába.
2. Másold be a RandomMusic mappából a RandomMusic.mod filet a documents/Paradox Interactive/Europa Universalis IV/mod mappába.
3. Módosítsd a path-et a .mod fileban. A USERNAME részt cseréld ki a sajátodra. Ha kell módosítsd az elérési út többi részét, a lényeg hogy a RandomMusic mappára mutasson. **NE** a Windows Explorerből másold ki az utat.
4. Add hozzá a paradox launcherben egy playsethez.

Hogyan adj hozzá zenét

1. Forkold a repot.

2. Töltsd le a zenét és konvertáld .ogg formátumba. A konvertálás **44100Hz**(44.1kHz) és **192 kbps** (Audacityben kb. 6-os qualitz) kell legyen. Csak olyan zenét válaszz, ami se a Code Geass, se a másik Anime Music modba nincs benne. https://sites.google.com/view/euiv-anime-music-re/strona-g%C5%82%C3%B3wna

3. Másold a .ogg filet a RandomMusic/music mappába. A filet értelmesen nevezd el, lehetőleg a szám címe csupa kis betűvel, egybe írva. Ez minimalizálja az esélyét annak, hogy későbbi lépésekben elírd a nevét és könnyű eldönteni, hogy az a szám szerepel-e már a modban.

4. Egészítsd ki a RandomMusic/music/random_music.asset filet. A file végére minden számhoz csinálj egy ilyen blokkot:
```
music = {
    name = "Shikairo Days"
    file = "shikairodays.ogg"
}
```
A name mező legyen a szám címe, szépen leírva, ne poénos nevekkel. A file mező a 2. lépésben bemásolt .ogg file.

5. Egészítsd ki a RandomMusic/music/random_music.txt filet. A file végére minden számhoz csinálj egy ilyen blokkot:
```
song = {
    name = "Shikairo Days"
    chance = {
        modifier = { factor = 1 }
    }
}
```
A name mező egyezzen meg a 3. pontban a name mezővel. A chance konfigurációját ajánlott ezen hagyni, ha valami advancedebbet akarsz csinálni akkor a paradox wikin van hozzá leírás: https://eu4.paradoxwikis.com/Music_modding. Ha egyszerre több zenét adsz hozzá, akkor a két fileban **azonos sorrendben** kövessék egymást.

6. Teszteld le a zenéid. In-game a music playerben a Random Music alatt találod meg a zenéket. A zenére rákattintva el kell hogy induljon. Ha a zene hiányzik onnan, vagy 0:00 a hossza, akkor elírtad a file nevet, vagy nem egyezik a 2 fileban a name mező, vagy valamelyik filet nem egészítetted ki, esetleg a .ogg konvertálás volt hibás. Ha valami extrább a chance blokkot tettél bele, azt is teszteld le.

7. Küldj pull requestet és szólj róla, majd megnézem és approveolom. A commit message tartalmazzon linket minden hozzáadott zenéhez.

Mit csinálj ha nem működik a mod

0. Ha windows explorerből copy patheztél ügyelj a "/" jelekre. A Windows "\\" jeleket használ, ezekkel nem jó a path.

1. Töröld a modot az összes playsetből.

2. Töröld a .mod filet.

3. Zárd be és nyisd meg újra a paradox launchert.

4. Ha nem tűnt el a mod, akkor az all installed mods-on belül kattints a reload installed mods gombra jobb felül (refresh ikon).

5. Zárd be a launchert.

6. Tedd vissza a .mod filet (ne felejtsd el a path-et árírni).

7. Nyisd meg újra a launchert.