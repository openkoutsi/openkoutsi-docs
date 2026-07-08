# Datasi ja tekoäly

Tämä sivu kertoo, miten openkoutsi käsittelee dataasi ja — jos valitset
valinnaisten tekoälyominaisuuksien käytön — tarkalleen **mitä** kielimallille
(LLM) lähetetään ja **minne** se menee.

## Miten datasi tallennetaan

Kaikki, mitä syötät openkoutsiin, pysyy instanssiasi pyörittävällä palvelimella:

- Jokaisella käyttäjällä on **oma yksityinen tietokantansa**. Aktiviteettisi,
  ohjelmasi, mittarisi ja profiilisi näkyvät vain sinulle — eivät muille
  käyttäjille eivätkä ylläpitäjälle.
- Ladatut **FIT-tiedostot ja profiilikuvat tallennetaan salattuina** palvelimelle.
- Voit **viedä datasi tai poistaa tilisi** milloin tahansa.

openkoutsin tavallinen käyttö — lenkkien lataaminen, synkronointi Stravasta ja
Wahoosta, mittareidesi ja ohjelmiesi katselu — ei koskaan lähetä harjoitusdataasi
minnekään muualle kuin selaimesi ja oman palvelimesi välillä (sekä Stravaan ja
Wahooon silloin, kun *sinä* yhdistät ne).

## Tekoälyominaisuudet ovat valinnaisia

openkoutsissa on neljä ominaisuutta, jotka käyttävät kielimallia:

| Ominaisuus | Mitä se tekee |
|---|---|
| **Aktiviteettianalyysi** | Kirjallista valmennuspalautetta yksittäisestä lenkistä. |
| **Päivittäinen harjoitustilanne** | Lyhyt yhteenveto nykyisestä muodostasi ja seuraavista askelista. |
| **Tekoälyn ohjelmanluonti** | Rakentaa harjoitusohjelman vaatimustesi pohjalta. |
| **Tekoälyn harjoitusten luonti** | Muuntaa suunnitellun päivän strukturoiduksi intervalliharjoitukseksi. |

!!! info "Mitään ei lähetetä ilman suostumustasi"
    Nämä ominaisuudet toimivat vain, kun **molemmat** seuraavista ovat totta:

    1. LLM-päätepiste on **määritetty** (sinun toimestasi tai ylläpitäjän toimesta
       instanssin laajuisesti), ja
    2. **käynnistät ominaisuuden** — esimerkiksi napsautat aktiviteetissa
       *Analysoi* tai ohjelmassa *Luo*.

    Jos LLM:ää ei ole määritetty tai et koskaan käytä näitä toimintoja, **mitään
    dataa ei lähetetä millekään mallille.** Kaikki muut ominaisuudet toimivat
    silti.

## Minne datasi menee

openkoutsi keskustelee minkä tahansa **OpenAI-yhteensopivan** chat-rajapinnan
kanssa. Päätepisteen valitsee se, joka sen määrittää, ja *tuo valinta ratkaisee,
lähteekö mitään dataa palvelimeltasi*:

- **Paikallinen malli** (esimerkiksi samalla koneella pyörivä
  [Ollama](https://ollama.com/), `http://localhost:11434/v1`) — pyyntö ei koskaan
  poistu palvelimeltasi. Mitään ei jaeta kolmannelle osapuolelle.
- **Ulkoinen palveluntarjoaja** (esimerkiksi isännöity OpenAI-yhteensopiva
  rajapinta) — pyyntö lähetetään internetin yli kyseiselle palveluntarjoajalle, ja
  siihen sovelletaan **sen** tietosuojakäytäntöä ja säilytysehtoja.

!!! warning "Tunne päätepisteesi"
    Se, lähteekö harjoitusdatasi palvelimeltasi, riippuu kokonaan määritetystä
    päätepisteestä. Jos haluat datasi pysyvän täysin itse isännöitynä, käytä
    paikallista mallia. Jos ulkoinen palveluntarjoaja on määritetty, käsittele
    kaikkea, mitä ominaisuudet lähettävät (katso alla), kyseisen palveluntarjoajan
    kanssa jaettuna.

Voit asettaa **oman** päätepisteesi kohdassa **Asetukset → Tekoäly / LLM**, mikä
ohittaa instanssin oletusarvon tilillesi. Ylläpitäjä asettaa instanssin
oletuksen; palvelimen globaali asetus on viimeinen varavaihtoehto.

## Mallin valinta

Ylläpitäjä voi tarjota **useita malleja** valittavaksi — esimerkiksi nopean
paikallisen mallin sekä yhden tai useamman isännöidyn palveluntarjoajan. Kun
tarjolla on useampi kuin yksi, **Malli**-pudotusvalikko ilmestyy kohtaan
**Profiili → Analyysi**. Valitse malli, jota haluat tekoälyominaisuuksien
käyttävän, tai jätä se arvoon **Oletus** noudattaaksesi ylläpitäjän valintaa.

!!! warning "Mallin valinta voi muuttaa sitä, minne datasi menee"
    Jokainen ylläpitäjän määrittämä malli osoittaa omaan päätepisteeseensä.
    **Paikallisen** mallin valinta pitää datasi palvelimella; **isännöidyn
    palveluntarjoajan** valinta lähettää pyynnön (ks. *Mitä mallille lähetetään*
    alla) kyseiselle palveluntarjoajalle sen tietosuoja- ja säilytysehtojen
    mukaisesti. Jos et ole varma, missä malli toimii, kysy ylläpitäjältä tai
    valitse malli, jonka tiedät olevan paikallinen.

## Mitä mallille lähetetään

Vain käynnistämääsi ominaisuuteen liittyvä data sisällytetään — tiiviinä
tekstiyhteenvetona, ei koskaan raakatiedostoinasi. Tarkemmin:

=== "Aktiviteettianalyysi"

    Yhteenveto **yhdestä** analysoimastasi aktiviteetista:

    - laji, päivämäärä/aika, kesto, matka, nousumetrit
    - keskiteho / normalisoitu teho, intensiteettikerroin, TSS, keski- / huippusyke
    - FTP:si ja maksimisykkeesi
    - kuntosi/väsymyksesi/muotosi (CTL/ATL/TSB) ennen lenkkiä
    - intervallierittely ja mahdolliset tehdyt ennätykset
    - aktiviteetin **tunnisteet ja muistiinpanosi** (kirjoittamaasi vapaata tekstiä)

=== "Päivittäinen harjoitustilanne"

    Tilannekuva viimeaikaisesta harjoittelustasi:

    - FTP:si ja maksimisykkeesi
    - nykyinen CTL/ATL/TSB:si
    - **viimeiset 28 päivää** aktiviteetteja (päivämäärä, laji, kesto, TSS)
    - aktiivisen ohjelmasi nimi, päivämäärät ja tämän viikon suunnitellut harjoitukset
    - aktiiviset **tavoitteesi** (otsikko, kohde, tila)

=== "Tekoälyn ohjelmanluonti"

    Pyytämäsi ohjelman vaatimukset:

    - pituus, jaksotustyyli, intensiteettitoive, harjoituspäivät viikossa
    - **tavoitteesi/tapahtumasi** ja kirjoittamasi **lisäkuvaus**
    - FTP:si ja nykyinen kuntosi (CTL)

=== "Tekoälyn harjoitusten luonti"

    Laajennettavan suunnitellun päivän kuvaus:

    - harjoitustyyppi ja laji
    - suunniteltu kuvaus, tavoitekesto ja tavoite-TSS
    - FTP:si

## Mitä ei koskaan lähetetä

Riippumatta käyttämästäsi ominaisuudesta openkoutsi **ei** lähetä:

- **nimeäsi, sähköpostiasi tai kirjautumistietojasi**
- **raakatiedostojasi** (FIT) tai mitään **GPS- / reitti- / sijaintidataa**
- kenenkään **muun käyttäjän** dataa
- tallennettua **API-avaintasi** minnekään muualle kuin sille päätepisteelle, jota
  se todentaa (ja avaimet säilytetään **salattuina**)

!!! tip "Vapaan tekstin kentät"
    Ominaisuudet sisältävät *sinun* kirjoittamaasi vapaata tekstiä — aktiviteetin
    **muistiinpanot**, tavoitteiden **otsikot** ja ohjelmien **kuvaukset** — koska
    tämä konteksti parantaa valmennusta. Jos **ulkoinen** palveluntarjoaja on
    määritetty, vältä arkaluontoisen tiedon laittamista näihin kenttiin tai vaihda
    paikalliseen malliin.

## Hallinnassasi

- **Etkö halua tekoälyä lainkaan?** Jätä LLM määrittämättä (tai älä käytä
  tekoälytoimintoja). Kaikki muu toimii täsmälleen samoin.
- **Haluatko sen täysin yksityiseksi?** Osoita **Asetukset → Tekoäly / LLM**
  paikalliseen malliin, tai valitse paikallinen malli **Profiili → Analyysi**
  -pudotusvalikosta, jos ylläpitäjä tarjoaa sellaisen.
- **Muutitko mielesi?** Tyhjennä päätepiste asetuksistasi; tulevat toiminnot eivät
  lähetä mitään. Voit myös viedä tai poistaa datasi milloin tahansa.
