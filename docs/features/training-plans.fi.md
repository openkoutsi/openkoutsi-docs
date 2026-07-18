# Harjoitusohjelmat ja harjoitukset

openkoutsi voi rakentaa sinulle strukturoidun harjoitusohjelman ja muuttaa sen
päivät yksityiskohtaisiksi intervalliharjoituksiksi, joita voit ajaa
pyörätietokoneeltasi.

## Ohjelman luominen

Luo **jaksotettu** ohjelma, joka etenee klassisten vaiheiden läpi:

**Perusvaihe → Rakennusvaihe → Huippuvaihe → Kevennysvaihe**

Annat ohjelmalle nimen, tavoitteen, aloituspäivän ja keston, ja openkoutsi
jakaa harjoitukset viikkojen varrelle.

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

!!! tip "Esimerkki"
    Ohjelmassa on pitkä lenkki, mutta pysäytät tallennuksen vahingossa puolivälissä
    ja saat kaksi keskipitkää lenkkiä. Linkitä molemmat suunniteltuun harjoitukseen,
    niin niiden yhteenlaskettu aika ja kuorma täyttävät sen — tiedostoja ei tarvitse
    yhdistää.

!!! note
    Automaattinen tunnistus linkittää edelleen yksittäisen aktiviteetin, joka
    kattaa päivän harjoituksen yksinään. Kun harjoitus jakautui osiin, jotka kukin
    jäävät vajaaksi, linkitä ylimääräiset aktiviteetit käsin.

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
