# Reittianalyysi

Jokainen muu openkoutsin tekoälyominaisuus vastaa kysymykseen **menneestä**:
missä kunnossa olet, miten lenkki meni, onko tavoite realistinen. Reittianalyysi
vastaa siihen ainoaan kysymykseen, jolla on takaraja — **miten ajan tämän
lauantaina?**

Lataat GPX-reitin, ja openkoutsi jakaa sen osuuksiin, laskee omalla FTP:lläsi ja
painollasi mitä tehoa kullakin osuudella pidetään ja kauanko se kestää, ja pyytää
Koutsia kirjoittamaan suunnitelman: missä kuluttaa, missä pidätellä ja milloin
syödä.

## Reitin lataaminen

Reitti on sellainen, jonka *aiot ajaa* — tapahtuman järjestäjän julkaisema GPX
tai itse piirtämäsi. Se ei ole jo ajettu lenkki; ne kuuluvat
[Aktiviteetteihin](activities.md).

Pudota **Reitit**-sivulla `.gpx`-tiedosto ja kerro openkoutsille, miten aiot sen
ajaa:

| Syöte | Miksi sitä kysytään |
|---|---|
| **Pyörä** | Renkaan leveys ja ajoasento määrittävät vierintävastuksen ja sen, kuinka paljon ilmaa työnnät. Soratpyörä 45 mm renkailla ja aika-ajopyörä 25 mm renkailla tuottavat aidosti eri suunnitelmat. |
| **Tavoiteaika** *(valinnainen)* | Jätä pois, niin saat tasaisen, kestävän vedon. Aseta se, ja suunnitelma lasketaan maalista taaksepäin. |
| **Aloituspäivä ja -aika** *(valinnainen)* | Antaa suunnitelmalle päivän: milloin aloittaa syöminen, miltä viimeinen tunti näyttää. |
| **Tavoite** *(valinnainen)* | Liittää reitin [tavoitteeseen](goal-guidance.md), jonka olet jo asettanut tapahtumalle. |

**FTP ja paino tulevat profiilistasi**, joten niitä ei kysytä uudelleen. Molemmat
täytyy olla asetettuina — fysiikka ei toimi ilman niitä.

## Osuustaulukko

Reitti jaetaan kohdista, joissa nousuprosentti muuttuu merkittävästi, ja jokainen
osuus saa oman rivinsä:

- **Matka** — mistä osuus alkaa ja kuinka pitkä se on
- **Nousuprosentti** — keskimääräinen kaltevuus ja se, lasketaanko osuus nousuksi,
  laskuksi vai tasaiseksi
- **Teho** — mitä pitää yllä, watteina ja osuutena FTP:stäsi
- **Ennustettu väliaika** — kauanko osuuden pitäisi kestää ja mikä kokonaisaika
  siinä kohtaa reittiä on

Lyhyet pätkät sulautetaan naapureihinsa tarkoituksella. Jatkuvasti aaltoileva tie
tuottaisi muuten satoja rivejä, eikä kukaan tahdita 40 metrin osuuteen.

Taulukon yläpuolella oleva korkeusprofiili on väritetty nousuprosentin mukaan, ja
osuuden valitseminen korostaa sen profiilissa — numerorivi ja kuvaajan muoto ovat
näin sama asia.

!!! info "Miksi luvut eivät ole arvauksia"
    Jokainen nopeus ja väliaika tulee tavanomaisesta pyöräilyn tehotasapainon
    yhtälöstä — painovoima, vierintävastus ja ilmanvastus vastaan se teho, jonka
    poljet. Se on laskentaa, ei mielipide, eikä Koutsi saa tehdä siitä mitään:
    valmentaja saa valmiin taulukon ja kirjoittaa siitä.

## Tavoiteajan pyytäminen

Kun annat reitille tavoitteen, openkoutsi jakaa voimat sen yli sen sijaan, että
levittäisi tehon tasaisesti: kovempaa nousuissa, joissa watti ostaa eniten aikaa,
ja kevyemmin laskuissa, joissa se ostaa lähes mitään.

Jos tavoite ei ole saavutettavissa, **sinulle kerrotaan se** sen sijaan, että
saisit imartelevan luvun:

- **Nopeampi kuin fysiikka sallii** — millään inhimillisellä teholla ei kierretä
  siinä ajassa. Tilalle näytetään nopein mallinnettu ajo.
- **Enemmän kuin jaksaisit ylläpitää** — saavutettavissa paperilla, mutta vain
  sellaisella keskitehotasolla, jota kukaan ei pidä yllä niin kauan. Suunnitelma
  kertoo, mitä se vaatisi ja mikä on tuon mittaiselle ajolle todella kestävää.

Kummassakin tapauksessa saat silti reitin ja sen osuustaulukon. Kieltäytyminen on
vastaus, ei virhe.

## Kirjallinen suunnitelma

Kun taulukko on laskettu, **Hae tahditussuunnitelma** antaa sen Koutsille, joka
kirjoittaa miten päivä ajetaan: tahdit reitin eri vaiheissa, ratkaisevat nousut,
juoma- ja ravinto-ohjelma ennustetun keston ja tehon pohjalta sekä kohdat, joissa
kannattaa tarkistaa oma tilanne ja säätää.

Koutsille annetaan **laskettu taulukko eikä koskaan itse reittiä** — ei
koordinaatteja, koska se ei niitä tarvitse. Näin se ei keksi paikallistuntemusta
tiestä, josta se ei tiedä mitään, ja kaikki sen sanoma juontuu lukuun, jonka näet
itsekin.

!!! warning "Suunnitelma olettaa tyynen ilman ja kuivan asfaltin"
    Mallissa ei ole tuulta eikä vielä pinnan tunnistusta: jokaista reittiä
    käsitellään kuivana asfalttina tyynenä päivänä. Vastatuuli siirtää väliaikoja,
    ja se voi siirtää niitä paljon. Kohtele aikoja tahditusrunkona eikä ennusteena
    — ja odota, että suunnitelma sanoo tämän itsekin.

    **Myös ryhmäajo voittaa tämän mallin tasaisella.** Fysiikka asettaa sinut
    yksin tuuleen; letkassa istuminen on paljon halvempaa, joten vauhdikas
    ryhmälenkki alittaa ennusteen tasaisilla osuuksilla ja osuu siihen suunnilleen
    heti kun tie kääntyy ylöspäin.

## Tallennetut reitit

Reitit säilytetään, ja juuri se tekee niiden lataamisesta kannattavaa:

- **Analysoi uudelleen ilman uutta latausta.** Vaihda pyörää, aseta tai poista
  tavoiteaika — reitti ratkaistaan uudelleen jo tallennetusta. Kirjallinen
  suunnitelma tyhjennetään samalla, koska vanhoista luvuista kirjoitettu teksti
  koskee eri ajoa.
- **Poista mikä tahansa reitti**, jolloin analyysi ja alkuperäinen tiedosto
  poistuvat yhdessä.

## Datasi

Reittianalyysi on ainoa paikka, jossa openkoutsi säilyttää reitin, ja se tekee sen
tarkoituksella — koko kuva löytyy sivulta [Datasi ja tekoäly](../data-and-ai.md):

- Reitti elää **omassa tietokannassasi**, ja lataamasi GPX on **salattuna
  levyllä**, aivan kuten harjoitustiedostosi.
- **Lenkeistäsi riisutaan yhä sijainti.** Reitin lataaminen ei muuta mitään siinä,
  miten aktiviteetteja käsitellään.
- Reitit, niiden osuustaulukot ja alkuperäiset tiedostot sisältyvät kaikki
  **datavientiin**, ja ne poistetaan kun poistat reitin tai tilisi.
- **Valmentaja saa lasketun taulukon, ei koskaan reittijälkeä.**

!!! note "Vaatii tekoälyn käytettävyyden"
    Osuustaulukko ja tahdituslukemat eivät tarvitse tekoälyä lainkaan — ne
    lasketaan omalla palvelimellasi ja toimivat riippumatta siitä, onko mallia
    määritetty. Vain *kirjallinen* suunnitelma käyttää sitä. Palvelimilla, joilla
    tekoälyominaisuudet vaativat tilauksen, sinua pyydetään tilaamaan tai
    [liittämään oma mallisi](using-your-own-ai-model.md).
