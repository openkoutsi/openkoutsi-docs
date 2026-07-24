# Harjoitusohjelmat ja harjoitukset

openkoutsi voi rakentaa sinulle strukturoidun harjoitusohjelman ja muuttaa sen
päivät yksityiskohtaisiksi intervalliharjoituksiksi, joita voit ajaa
pyörätietokoneeltasi.

## Ohjelman luominen

Luo **jaksotettu** ohjelma, joka etenee klassisten vaiheiden läpi:

**Perusvaihe → Rakennusvaihe → Huippuvaihe → Kevennysvaihe**

Annat ohjelmalle nimen, tavoitteen, aloituspäivän ja keston, ja openkoutsi
jakaa harjoitukset viikkojen varrelle.

### Rakenneparametrit

Harjoituspäivien ja -tyyppien lisäksi voit säätää, miten ohjelma etenee. Järkevät
oletukset ehdotetaan **kokemustasosi** perusteella, ja voit ohittaa minkä tahansa
niistä:

- **Viikoittainen nousu** — kuinka paljon kuorma ja aika kasvavat joka
  rakennusviikko, yleensä **5–10 %**. Aloittelijat matalammassa päässä, kokeneet
  ajajat korkeammassa.
- **Rakennus : palautus -rytmi** — kuinka monta rakennusviikkoa on ennen jokaista
  palautusviikkoa (**2 : 1** tai **3 : 1** -rytmi). Aloittelijoille sopii yleensä
  2 : 1; keskitason ja kokeneet ajajat kestävät 3 : 1.
- **Viikoittaiset tunnit käytettävissä** — väli, esim. **4–6 tuntia**. openkoutsi
  pitää kunkin viikon kokonaisajoajan tällä välillä: palautusviikot lähellä alarajaa,
  huippurakennusviikot lähellä ylärajaa. Jätä tyhjäksi, jos et halua rajaa.
- **Viikoittainen peruskuorma** — lisäkuorma, jonka saat **muusta kuin
  harjoitusajosta**, kuten työmatkoista. Sitä käsitellään kontekstina (näytetään
  kunkin viikon yhteydessä ja annetaan tekoälylle), eikä sitä lisätä määrättyihin
  harjoituksiin, joten ohjelma pysyy realistisena ilman kaksinkertaista laskentaa.

!!! tip "Aseta tuntisi kerran"
    Tyypillinen viikoittainen harjoitustuntiväli on **profiilissasi**. Uudet
    ohjelmat esitäyttyvät siitä, joten asetat sen vain kerran.

### Rakennus- ja palautusviikot

Jokainen viikko merkitään **rakennus-**, **palautus-** tai **kevennysviikoksi**,
ja ohjelmakalenterissa näkyy lyhyt fokusmerkintä sekä viikon tavoitetunnit ja
-kuorma. Rakennusviikot kuormittavat asteittain enemmän; palautusviikot keventävät,
jotta keho ehtii sopeutua harjoitteluun ennen seuraavaa jaksoa.

!!! info "Järkevät kovat päivät"
    Kynnys- ja VO2max-harjoitukset ovat vaativia — sarja kuten 3×15 min kynnysteholla
    on todella kova oikein tehtynä. openkoutsi ei aseta näitä "kovia" päiviä
    peräkkäisiksi ja rajoittaa niiden määrää viikossa keventäen ylimääräiset
    tempoksi. Kunkin päivän kuvaus vastaa sen todellista kestoa ja tavoitekuormaa.

## Ohjelman muokkaaminen

Ohjelmat eivät ole kiinteitä luomisen jälkeen. Voit:

- muokata ohjelman metatietoja (nimi, tavoite, aloituspäivä, kesto)
- lisätä, muokata tai poistaa yksittäisiä suunniteltuja harjoituksia
  kalenterin päivänäkymästä
- luoda ohjelman harjoitukset uudelleen (sääntöpohjaisesti tai tekoälyllä)

!!! info "Suoritetut harjoitukset on suojattu"
    Jo suorittamasi harjoitukset on lukittu muokkaamiselta ja ne säilytetään, kun
    luot ohjelman uudelleen.

## Harjoituskalenteri

Kojelautasi kalenteri näyttää sekä **suoritetut** että **suunnitellut**
harjoitukset eri merkinnöin (suoritettu, odottava, ohitettu). Päivästä voit
merkitä suunnitellun harjoituksen **tehdyksi** tai **ohitetuksi** avaamatta koko
ohjelmaa.

Kun ohitat harjoituksen, voit kirjata syyn (sairaus, vamma, väsymys, matkustus,
sää ja niin edelleen). Tämä pitää harjoituspäiväkirjasi tarkkana ja antaa
tekoälyvalmennuksen ominaisuuksille hyödyllistä kontekstia.

### Yksi harjoitus, useita aktiviteetteja

Joskus yksi harjoituskerta päätyy tallentumaan useampana aktiviteettina — pysäytit
tallennuksen vahingossa, pidit kahvitauon tai teit pari virtuaalilenkkiä peräkkäin.
Voit linkittää **jokaisen** näistä aktiviteeteista samaan suunniteltuun
harjoitukseen, jolloin niiden kestot ja kuormat lasketaan yhteen tavoitetta
kohti.

Avaa suunniteltu harjoitus kalenterista, linkitä ensimmäinen aktiviteetti ja lisää
loput painikkeella **Linkitä toinen harjoitus**. Jokainen linkitetty aktiviteetti
näytetään ja sen voi poistaa linkityksestä erikseen.

!!! tip "Päivän tai parin heitto?"
    Kun linkität käsin, valikko tarjoaa kaikki aktiviteetit, jotka olet tallentanut
    **kahden päivän** sisällä suunnitellusta päivästä molempiin suuntiin, kukin
    varustettuna täydellä päivämäärällä. Ohjelmat elävät usein hieman, joten
    keskiviikkona ajettu lenkki voi silti täyttää tiistain suunnitellun harjoituksen.

!!! tip "Esimerkki"
    Ohjelmassa on pitkä lenkki, mutta pysäytät tallennuksen vahingossa puolivälissä
    ja saat kaksi keskipitkää lenkkiä. Linkitä molemmat suunniteltuun harjoitukseen,
    niin niiden yhteenlaskettu aika ja kuorma täyttävät sen — tiedostoja ei tarvitse
    yhdistää.

!!! note
    Automaattinen tunnistus linkittää edelleen yksittäisen aktiviteetin, joka
    kattaa päivän harjoituksen yksinään. Kun harjoitus jakautui osiin, jotka kukin
    jäävät vajaaksi, linkitä ylimääräiset aktiviteetit käsin.

## Toteutumapisteet

openkoutsi muuttaa kysymyksen "noudatanko suunnitelmaani?" kahdeksi konkreettiseksi
prosenttiluvuksi, jotka päivittyvät jatkuvasti aktiviteettien saapuessa — ei vasta
suunnitelman lopussa. Ne ovat **aina saatavilla** eivätkä vaadi tekoälytilausta.

**Harjoituskohtaiset osumapisteet.** Jokainen suoritettu harjoitus saa pisteet
0–100 % sen mukaan, kuinka tarkasti se osui suunnitelmaan. Pyöräilyharjoituksissa
tarkastellaan sekä **kuormaa** että **kestoa**, ja — tärkeää — liian kovaa tai liian
pitkää suoritusta rangaistaan yhtä lailla kuin vajaaksi jäämistä: rauhallinen
palautusajo raakana intervalliharjoituksena ei ole täydellinen osuma. Tavoitteeseen
osuminen antaa 100 %; 20 % ohi kumpaan tahansa suuntaan jää noin 80 %:iin.
Muut kuin pyöräilyharjoitukset ("täydentävät" — voima, jooga, uinti) pisteytetään
yksinkertaisesti tehty/tekemättä. Kun yksi sessio jakautui useaan linkitettyyn
aktiviteettiin, niiden kuorma ja kesto lasketaan yhteen ennen pisteytystä.

Harjoitus, jonka **suoritit**, ei koskaan jää alle **50 %:n**, olipa se kuinka
kaukana tavoitteesta tahansa — suunnitellun 85 minuutin peruskestävyysajon
muuttaminen neljän tunnin rauhalliseksi ajoksi on silti parempi kuin harjoituksen
väliin jättäminen. Vain väliin jääneet ja ohitetut harjoitukset voivat mennä
alemmas.

**Suunnitelman toteutumapisteet.** Harjoituspisteesi kootaan yhdeksi "tähän
mennessä" -prosentiksi koko suunnitelmalle, kattaen jo kuluneen osan. Se on
**kuormapainotettu**, joten suuren avainharjoituksen väliin jättäminen laskee sitä
enemmän kuin kevyen palautusajon. Väliin jäänyt harjoitus lasketaan nollaksi.

Ohitettuja harjoituksia kohdellaan lempeästi, ja syy vaikuttaa:

| Ohituksen syy | Vaikutus pisteisiin |
|---|---|
| Sairaus, loukkaantuminen | Lähes täysin anteeksiannettu |
| Väsymys, matkustus | Kohtalainen vähennys |
| Sää | Lievä vähennys |
| Muu / ei syytä | Lähes täysi väliin jääminen |

!!! info "Tätä päivää arvioidaan lempeästi"
    **Tälle päivälle** ajoitettua harjoitusta, jota et ole vielä tehnyt, pidetään
    armonajassa — sitä ei lasketa väliin jääneeksi ennen kuin päivä on ohi. Heti kun
    linkität aktiviteetin, se pisteytetään tähän mennessä tehdyn perusteella.
    Lepopäivät ja tulevat harjoitukset eivät koskaan ole sinua vastaan.

Näet nykyisen "tähän mennessä" -prosentin suunnitelman otsikossa, värikoodatun
merkin jokaisessa harjoituksessa sekä toteutuman trendikaavion kojelaudallasi, joten
voit seurata luvun liikettä suunnitelman edetessä.

## Strukturoidut harjoitukset

Rakenna intervalliharjoituksia ja vie ne laitteellesi:

- **Zwift** — vie `.zwo`-tiedostona.
- **Pyörätietokoneet** — vie FIT-harjoitustiedostona. Toistolohkot tasoitetaan
  yksittäisiksi peräkkäisiksi vaiheiksi, jotta ne näkyvät luotettavasti Wahoo- ja
  Garmin-laitteissa.

### Harjoitusten siirtäminen Wahoolle

Jos olet yhdistänyt Wahoon, voit lähettää strukturoidun harjoituksen suoraan
tilillesi ajastettuna suunniteltuna harjoituksena. Se ilmestyy sitten kohtaan
**Planned Workouts** ELEMNT- / RIVAL-laitteessasi.

- Ajasta se tästä päivästä kuuteen päivään eteenpäin.
- Saman harjoituksen uudelleensiirtäminen päivittää sen sen sijaan, että loisi
  kaksoiskappaleen.

### Harjoitusten luominen ohjelmasta

openkoutsi voi yhdellä toiminnolla automaattisesti syntetisoida strukturoituja
intervalliharjoituksia ohjelman tuleville päiville (käyttäen määritettyä
LLM:ää). Luodut harjoitukset tallennetaan välimuistiin suunniteltuun
harjoitukseen, joten jo luodut päivät ja lepopäivät ohitetaan eikä ylimääräistä
työtä toisteta. Päiväkohtainen yhteenveto näyttää, mitä luotiin, ohitettiin tai
epäonnistui. Tulokset ilmestyvät **Workouts**-välilehdelle, jossa voit tarkastella,
muokata ja ladata niitä Wahoolle yksitellen.

!!! note "Lisää yksityiskohtia tulossa"
    Täydellinen läpikäynti intervalliharjoituksen rakentamisesta alusta lisätään
    tähän.
