# Aloittaminen

Tämä sivu käy läpi ensiaskeleesi openkoutsi-instanssin käyttäjänä. Se olettaa,
että joku on jo asentanut openkoutsin palvelimelle — jos olet itse pystyttämässä
palvelinta, katso sen sijaan asennusopas pääprojektin repositoriosta.

## Instanssiisi pääseminen

Avaa openkoutsi-instanssisi osoite verkkoselaimessa (esimerkiksi se URL-osoite,
jonka ylläpitäjäsi antoi). openkoutsi toimii sekä työpöydällä että mobiilissa.

## Ensimmäisen käynnistyksen asetukset

Aivan ensimmäisellä kerralla, kun openkoutsi-instanssi avataan, se näyttää
**ohjatun asennuksen**, joka luo ensimmäisen **ylläpitäjätilin**. Jos olet
pystyttämässä instanssia, suorita tämä ohjattu toiminto luodaksesi ylläpitäjän
kirjautumistietosi. Tiimejä ei ole — yksi asennus on yksi instanssi, jonka sen
käyttäjät jakavat.

Jos instanssi on jo asetettu, näet sen sijaan tavallisen kirjautumissivun.

## Tilin hankkiminen

Tilin hankkiminen riippuu siitä, miten instanssi on määritetty.

**Kutsulla (aina käytettävissä):**

1. Ylläpitäjä lähettää sinulle **kutsun**.
2. Avaat kutsulinkin ja luot tilisi sen avulla.

**Itserekisteröinnillä (vain jos ylläpitäjä on ottanut sen käyttöön):**

1. Valitse kirjautumissivulla **Luo tili** ja rekisteröidy
   **sähköpostiosoitteellasi**.
2. Avaa sähköpostiisi lähetetty vahvistuslinkki vahvistaaksesi osoitteesi ja
   aktivoidaksesi tilisi.

Jos et näe rekisteröitymisvaihtoehtoa, instanssi toimii vain kutsusta — pyydä
ylläpitäjältä kutsu.

Kun tilisi on olemassa, kirjaudut sisään instanssin kirjautumissivulta.
Harjoitusdatasi on kokonaan omaasi — jokaisella käyttäjällä on **yksityinen
tietokanta**, eikä kukaan muu (ei edes ylläpitäjä) näe aktiviteettejasi tai
ohjelmiasi.

!!! info "Roolit"
    Rooleja on kaksi. Useimmat ovat **käyttäjiä**, jotka omistavat ja hallitsevat
    omaa profiiliaan ja harjoitusdataansa. **Instanssin ylläpitäjä** voi lisäksi
    hallita käyttäjiä, lähettää kutsuja ja muokata instanssin laajuisia asetuksia
    (kuten valinnaista tekoälymääritystä).

## Harjoitushistorian tuominen mukanasi

Kunto, väsymys ja muoto rakentuvat siitä, mitä olet jo tehnyt, joten openkoutsi on
heti ensimmäisenä päivänä paljon hyödyllisempi, jos se tuntee viime vuodet eikä
vain tämän päivän lenkkiä. Historian saa mukaan kahdella tavalla, ja ne toimivat
hyvin yhdessä.

### Tiedostoviennistä

Jos harjoittelet jo Stravan kanssa, pyydä siltä datasi **joukkovienti** ja tuo
arkisto sellaisenaan:

1. Mene Stravassa kohtaan **Asetukset → Oma tili → Lataa tai poista tilisi**,
   valitse **Pyydä arkistoasi** ja odota sähköpostia — siinä voi kestää muutama
   tunti.
2. Lataa sen linkittämä `.zip`-tiedosto. **Älä pura sitä.**
3. Avaa openkoutsissa **Harjoitukset** ja pudota `.zip` latausalueelle (tai käytä
   **Valitse tiedostot tai arkisto** -painiketta).

openkoutsi käy arkiston läpi itse, löytää sen sisältä harjoitustiedostot — Strava
pakkaa ne muodoissa `.fit`, `.tcx` ja `.gpx` — ja tuo ne taustalla. Voit käyttää
openkoutsia tuonnin aikana, ja edistymispaneeli näyttää, kuinka pitkällä se on.

Sama toimii mille tahansa joukolle harjoitustiedostoja, ei vain Stravan
vientiarkistolle: valitse niin monta `.fit`-, `.gpx`- tai `.tcx`-tiedostoa kuin
haluat, gzip-pakattuina tai ilman, tai oma `.zip`-arkistosi.

### Mitä näet, kun tuonti on valmis

Tuonti raportoi **jokaisen tiedoston**, ei pelkkää yhteismäärää:

- **Tuotu** — harjoitus on nyt openkoutsissa.
- **Jo täällä** — kyseisestä hetkestä on jo harjoitus, joten tämä tiedosto
  ohitettiin. Tämä on normaalia eikä virhe. Näin käy myös **saman** arkiston
  sisällä: vienti sisältää usein saman lenkin sekä `.fit`- että
  `.tcx`-muodossa, ja openkoutsi säilyttää näistä rikkaamman.
- **Epäonnistui** — syyn kera, joten näet, oliko tiedosto vioittunut, ei
  lainkaan harjoitus vai jotain, mitä openkoutsi ei lue.

Saman arkiston tuominen myöhemmin uudelleen on turvallista: kaikki jo olemassa
oleva ohitetaan ja raportoidaan sellaisena.

!!! note "GPX-lenkeissä ei ole tehoa"
    `.gpx`-tiedosto tallentaa sijainnin, korkeuden ja yleensä sykkeen — mutta ei
    tehoa. Siitä tuoduissa harjoituksissa ei siksi ole keskitehoa eikä painotettua
    tehoa, ei tehoennätyksiä eikä tehoalueaikaa, riippumatta siitä millä
    tehomittarilla ajoit. Niiden **kuormitus lasketaan sykkeestä**, joten ne
    kerryttävät silti kuntoasi ja väsymystäsi. Kun sama lenkki on olemassa myös
    `.fit`- tai `.tcx`-muodossa, openkoutsi valitsee juuri tästä syystä sen.

!!! info "Reittiäsi ei tallenneta"
    GPX- ja TCX-tiedostot rakentuvat GPS-koordinaateista. openkoutsi lukee ne vain
    laskeakseen matkan ja nousumetrit ja hylkää ne sen jälkeen — reittiäsi ei
    koskaan tallenneta, eikä näiden muotojen tuonti muuta sitä. Katso
    [Datasi ja tekoäly](data-and-ai.md).

### Yhdistetystä palvelusta

**Stravan** tai **Wahoon** yhdistäminen tuo viimeaikaisen historiasi
automaattisesti ja pitää uudet lenkit virtaamassa sisään — katso
[Aktiviteetit ja synkronointi](features/activities.md). Tee halutessasi
molemmat: tiedostotuonti kattaa syvän historian, yhteys pitää sinut ajan tasalla,
ja kahdesti saapuva tunnistetaan kaksoiskappaleeksi eikä lasketa kahteen kertaan.

## Urheilijaprofiilisi

Kun olet sisällä, määritä urheilijaprofiilisi (kuten FTP sekä syke- ja
tehoalueet). Näitä arvoja käytetään aktiviteettiesi analysointiin ja
harjoitusohjelmien rakentamiseen. Monet niistä voidaan myös synkronoida
automaattisesti yhdistetystä palvelusta — katso
[Aktiviteetit ja synkronointi](features/activities.md).

!!! tip "Seuraava vaihe"
    Kun profiilisi on kunnossa, tuo muutamia lenkkejä. Jatka kohtaan
    [Aktiviteetit ja synkronointi](features/activities.md).
