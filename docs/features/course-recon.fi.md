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
| **Tavoite** *(valinnainen)* | Jätä pois, niin saat tasaisen, kestävän vedon, tai tahdita reitti **maaliintuloaikaan** tai **keskitehoon**. Kumpaakin voi vaihtaa myöhemmin ilman uutta latausta. |
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

!!! note "Jyrkkää pinnanmuutosta ei koskaan sulateta pois"
    Sulattaminen koskee *tahditusrivejä*, eikä se päde lyhyeen pätkään, jossa tie
    muuttuu huonoksi. Jos 130 metriä reitistä on mutaa keskellä 40 kilometrin
    asfalttia, se säilyttää oman rivinsä, omat lukunsa, oman raitansa
    korkeusprofiilissa ja oman lauseensa suunnitelmassa. Siihen ei voi tahdittaa,
    mutta sen tulosta on ehdottomasti syytä tietää.

Taulukon yläpuolella oleva korkeusprofiili on väritetty nousuprosentin mukaan, ja
osuuden valitseminen korostaa sen profiilissa — numerorivi ja kuvaajan muoto ovat
näin sama asia.

!!! info "Miksi luvut eivät ole arvauksia"
    Jokainen nopeus ja väliaika tulee tavanomaisesta pyöräilyn tehotasapainon
    yhtälöstä — painovoima, vierintävastus ja ilmanvastus vastaan se teho, jonka
    poljet. Se on laskentaa, ei mielipide, eikä Koutsi saa tehdä siitä mitään:
    valmentaja saa valmiin taulukon ja kirjoittaa siitä.

## Tavoitteen pyytäminen

Kun annat reitille tavoitteen, openkoutsi jakaa voimat sen yli sen sijaan, että
levittäisi tehon tasaisesti: kovempaa nousuissa, joissa watti ostaa eniten aikaa,
ja kevyemmin laskuissa, joissa se ostaa lähes mitään. Tavoitteen voi kertoa
kahdella tavalla, ja ne ovat vaihtoehtoja — reitti tahditetaan jompaankumpaan,
ei koskaan molempiin.

### Maaliintuloaika

Kerro aika, jossa haluat tulla maaliin, niin suunnitelma lasketaan siitä
taaksepäin. Jos aika ei ole saavutettavissa, **sinulle kerrotaan se** sen sijaan,
että saisit imartelevan luvun:

- **Nopeampi kuin fysiikka sallii** — millään inhimillisellä teholla ei kierretä
  siinä ajassa. Tilalle näytetään nopein mallinnettu ajo.
- **Enemmän kuin jaksaisit ylläpitää** — saavutettavissa paperilla, mutta vain
  sellaisella keskitehotasolla, jota kukaan ei pidä yllä niin kauan. Suunnitelma
  kertoo, mitä se vaatisi ja mikä on tuon mittaiselle ajolle todella kestävää.

Kummassakin tapauksessa saat silti reitin ja sen osuustaulukon. Kieltäytyminen on
vastaus, ei virhe.

### Keskiteho

Kerro sen sijaan watit, niin kysymys kääntyy toisin päin: sinä lyöt lukkoon
vedon ja openkoutsi kertoo, minkä maaliintuloajan se tuottaa. Tämä on se luku,
jonka mittarisi näyttää lopussa — **keskiarvo, ei teho jota pidetään kaikkialla.**
Sama jako pätee yhä, joten nousuissa mennään sen yli ja laskuissa sen alle.

Tehotavoite ei voi olla mahdoton samalla tavalla kuin aika: mikä tahansa
wattimäärä on ajettavissa, kysymys on vain siitä kuinka kauan. Ainoa asia jota se
voi olla, on enemmän kuin jaksaisit tuottamansa ajon ajan — ja silloinkin **saat
koko suunnitelman**: väliajat ovat juuri se mitä pyysit, ja juuri ne näyttävät,
kuinka kauan sinun olisi tuota pidettävä.

!!! tip "Kumpaa kannattaa pyytää"
    Aikatavoite vastaa kysymykseen *”pääsenkö tästä neljässä ja puolessa tunnissa,
    ja mitä se maksaisi?”* Tehotavoite vastaa kysymykseen *”tiedän mitä jaksan
    pitää — minkälainen päivä siitä tulee?”* Ensimmäinen on kysymys ennen
    tapahtumaa, jossa on aikaraja; toinen on se kysymys hyvän testin jälkeen tai
    pitkänä päivänä, jossa hyvin maaliin pääseminen merkitsee enemmän kuin nopeasti.

### Mielen muuttaminen

Tavoite ei ole päätös, joka tehdään kerran latauksen yhteydessä. Millä tahansa
tallennetulla reitillä voit asettaa tavoitteen, vaihtaa ajan tehoksi (tai
toisin päin) tai poistaa sen kokonaan, ja reitti ratkaistaan uudelleen jo
tallennetusta — ilman uutta latausta. Kirjallinen suunnitelma tyhjennetään
samalla, koska vanhoista luvuista kirjoitettu teksti koskee eri ajoa.

## Kirjallinen suunnitelma

Kun taulukko on laskettu, **Hae tahditussuunnitelma** antaa sen Koutsille, joka
kirjoittaa miten päivä ajetaan: tahdit reitin eri vaiheissa, ratkaisevat nousut,
juoma- ja ravinto-ohjelma ennustetun keston ja tehon pohjalta sekä kohdat, joissa
kannattaa tarkistaa oma tilanne ja säätää.

Koutsille annetaan **laskettu taulukko eikä koskaan itse reittiä** — ei
koordinaatteja, koska se ei niitä tarvitse. Näin se ei keksi paikallistuntemusta
tiestä, josta se ei tiedä mitään, ja kaikki sen sanoma juontuu lukuun, jonka näet
itsekin.

!!! warning "Suunnitelma olettaa tyynen ilman"
    Mallissa ei ole tuulta: jokaista reittiä käsitellään tyynenä päivänä.
    Vastatuuli siirtää väliaikoja, ja se voi siirtää niitä paljon. Kohtele aikoja
    tahditusrunkona eikä ennusteena — ja odota, että suunnitelma sanoo tämän
    itsekin. Ellei palvelimesi luokittele tienpintoja (alempana), jokaista
    reittiä käsitellään myös kuivana asfalttina — minkä suunnitelma sanoo ääneen.

    **Myös ryhmäajo voittaa tämän mallin tasaisella.** Fysiikka asettaa sinut
    yksin tuuleen; letkassa istuminen on paljon halvempaa, joten vauhdikas
    ryhmälenkki alittaa ennusteen tasaisilla osuuksilla ja osuu siihen suunnilleen
    heti kun tie kääntyy ylöspäin.

## Tienpinta

Palvelimilla, joilla tämä on kytketty päälle, openkoutsi selvittää **mitä tien
alla on** ja syöttää sen lukuihin. Sora on hitaampaa kuin asfaltti samalla
teholla, joten sen tietäminen muuttaa tehotavoitteen, ennustetun väliajan ja
varsin todennäköisesti myös renkaat, jotka laitat alle.

Jokainen osuus saa pinnan — asfaltti, päällystetty, kova sora, mukulakivi, sora,
maa tai nurmi — ja korkeusprofiilin alle ilmestyy samanvärinen raita, joten
päivän muoto ja tien kunto ovat yksi kuva.

### Vahvistettu vai arvio

**Jokaisella pinnalla on luotettavuus, eivätkä ne ole sama väite.**

OpenStreetMap on vapaaehtoisten kartta, ja se, kuinka tarkasti tiet on kuvattu,
vaihtelee valtavasti — tiheästi Saksassa ja Alankomaissa, ohuesti Pohjois-Amerikan
maaseudulla. Kun joku on kirjannut pinnan, openkoutsi sanoo **vahvistettu**. Kun
kukaan ei ole, luokka tulee tien *tyypistä*, ja openkoutsi sanoo **arvio**.

!!! info "Mitä ”arvio” oikeasti tarkoittaa"
    Se tarkoittaa, että **openkoutsi ei pystynyt vahvistamaan pintamerkintää**
    kyseiselle osuudelle — ei sitä, että tie olisi varmasti merkitsemätön, eikä
    sitä, että vastaus olisi varmasti väärä. Myös aidosti asfaltiksi merkitty tie
    näkyy usein arviona, koska ”nimenomaisesti päällystetty” ja ”kukaan ei
    sanonut” näyttävät ulospäin samalta. Merkintä kallistuu tarkoituksella
    aliarvioimisen puolelle: se kertoo joskus olevansa epävarma ollessaan oikeassa,
    mutta se ei kerro olevansa varma ollessaan epävarma.

    Käytännössä: kohtele **vahvistettua** soraosuutta tosiasiana, jonka ympärille
    suunnittelet, ja **arviota** sellaisena, jonka kannattaa tarkistaa tapahtuman
    omista tiedoista ennen rengasvalintaa.

!!! note "Asfalttia ei koskaan vahvisteta"
    Sileä asfaltti ja tie, jota kukaan ei ole kuvaillut, näyttävät openkoutsille
    **täsmälleen samalta** — kartta antaa molemmille saman vastauksen — joten
    asfaltti voi tulla ulos vain arviona. Sen merkitseminen jokaiselle
    asfalttiriville toistaisi yhtä lausetta satoja kertoja ja hautaisi alleen ne
    rivit, joilla luotettavuus kertoo jotain, joten se sanotaan sen sijaan
    kerran pintakoosteen alla. Ne rivit, joissa **arvio**-merkintä on, ovat
    huomionarvoisia: karkeampi pinta, jonka openkoutsi löysi mutta jota se ei
    pystynyt varmistamaan.

### Osuudet, joista sinua varoitetaan

Kun tie muuttuu jyrkästi huonommaksi — asfaltista mutaan, asfaltista irtosoraan —
reitti listaa kyseisen pätkän etäisyyksineen osuustaulukon yläpuolelle, ja
kirjoitettu suunnitelma mainitsee sen erikseen. **Myös lyhyet.** 130 metrin osuus
on liian lyhyt tahditettavaksi ja liian tärkeä jätettäväksi väriksi, jota et
välttämättä katso.

### Reittisi ei poistu palvelimeltasi

Pinnan luokittelu tarkoittaa reitin sovittamista karttadataan, mikä vaatii
koordinaatit. Tämä sovitus tapahtuu **omalla palvelimellasi**, reitityspalvelua
vasten, jonka palvelimesi ylläpitäjä on pystyttänyt ja jonka karttadatan hän on
rakentanut. Reittiäsi ei lähetetä karttayhtiölle, rajapintaan eikä kenellekään
muulle — katso [Tietosi ja tekoäly](../data-and-ai.md).

### Jos palvelimellasi ei ole tätä

Silloin reittitiedustelu toimii täsmälleen niin kuin muualla tällä sivulla
kuvataan, ja jokainen reitti ratkaistaan kuivana asfalttina — minkä kirjoitettu
suunnitelma sanoo suoraan sen sijaan, että jättäisi sinut olettamaan. Mikään ei
ole rikki eikä mistään puutu osaa, jonka se olisi luvannut; pinta ei vain kuulu
vastaukseen.

Pinnat selvitetään myös **osuustaulukon ilmestymisen jälkeen**, joten reitin
lataaminen ei ole hitaampaa palvelimella, jolla ne ovat. Ja koska reittisi
säilytetään, myöhemmin tämän käyttöön ottava palvelin voi luokitella aiemmin
lataamasi reitit — ei uudelleenlatausta, vain **Lisää pintatiedot** reitillä.

## Tallennetut reitit

Reitit säilytetään, ja juuri se tekee niiden lataamisesta kannattavaa:

- **Analysoi uudelleen ilman uutta latausta.** Vaihda pyörää tai aseta, vaihda
  tai poista [tavoite](#mielen-muuttaminen) — reitti ratkaistaan uudelleen jo
  tallennetusta. Kirjallinen suunnitelma tyhjennetään samalla, koska vanhoista
  luvuista kirjoitettu teksti koskee eri ajoa.
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
- Tienpintojen selvittäminen sovittaa reittisi **omalla palvelimellasi**,
  reitityspalvelua vasten, jota se itse ajaa. Reitti ei mene minnekään muualle.

!!! note "Vaatii tekoälyn käytettävyyden"
    Osuustaulukko ja tahdituslukemat eivät tarvitse tekoälyä lainkaan — ne
    lasketaan omalla palvelimellasi ja toimivat riippumatta siitä, onko mallia
    määritetty. Vain *kirjallinen* suunnitelma käyttää sitä. Palvelimilla, joilla
    tekoälyominaisuudet vaativat tilauksen, sinua pyydetään tilaamaan tai
    [liittämään oma mallisi](using-your-own-ai-model.md).
