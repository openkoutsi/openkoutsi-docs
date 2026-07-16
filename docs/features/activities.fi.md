# Aktiviteetit ja synkronointi

Aktiviteetit ovat lenkkejä, joita openkoutsi analysoi seuratakseen kuntoasi ja
tarkistaakseen harjoitusohjelmasi. Voit lisätä ne käsin tai antaa niiden ilmestyä
automaattisesti.

## FIT-tiedostojen lataaminen

Lataa `.fit`-tiedosto pyörätietokoneestasi tai harjoitussovelluksestasi suoraan
openkoutsiin. Jokainen lataus analysoidaan automaattisesti seuraavien osalta:

- **Harjoituskuormitus**
- **Normalisoitu teho**
- **Aluejakauma** — kuinka kauan vietit aikaa kullakin teho- tai sykealueella

Harjoitukset luokitellaan myös automaattisesti Cogganin tyylisten alueiden
mukaan, ja voit tarvittaessa korvata luokituksen käsin.

## Aktiviteettien lisääminen käsin

Kaikki harjoitukset eivät tule laitteelta. Kun harjoittelet ilman pyörätietokonetta
— tai haluat kirjata suorituksen muistivihkosta tai taulukosta — käytä
aktiviteettisivun **Lisää suoritus** -painiketta ja syötä tiedot käsin.

Jokainen kenttä on valinnainen, joten täytä niin paljon tai vähän kuin muistat:

- **Laji** ja **päivämäärä**
- **Kesto** (minuutteina) ja **matka** (kilometreinä)
- **Keski-** ja **maksimisyke**
- **Keskiteho** ja **keskikadenssi**
- **Nousu**, **nimi** sekä joko **RPE** (1–10) tai eksplisiittinen **harjoituskuormitus**

Jos et anna harjoituskuormitusta, openkoutsi arvioi sen antamiesi tietojen perusteella tässä
järjestyksessä:

1. eksplisiittinen **harjoituskuormitus**-arvo, jos annoit sellaisen;
2. muuten **RPE** (koettu rasitus) skaalattuna kestolla;
3. muuten **keskisyke** käyttäen profiilisi maksimisykettä.

Käsin lisätyt aktiviteetit merkitään **Manual**-lähdemerkinnällä, ja ne otetaan
huomioon kuntomittareissasi ja harjoitusohjelman yhdistämisessä aivan kuten ladatut
tai synkronoidut lenkit.

!!! tip "Riittääkö pelkkä rasituksen kirjaaminen?"
    Pelkän päivämäärän, keston ja RPE:n syöttäminen riittää pitämään kunto-, väsymä- ja muoto-
    kuntokäyräsi ajan tasalla päivinä, jolloin harjoittelit ilman laitetta.

## Synkronointi Stravasta

Yhdistä Strava-tilisi tuodaksesi historiasi ja antaaksesi uusien lenkkien virrata
sisään automaattisesti:

1. Ylläpitäjäsi määrittää Strava-tunnukset instanssiin.
2. Yhdistä ("valtuuta") Strava asetuksistasi.
3. openkoutsi tuo viimeaikaisen historiasi ja pysyy ajan tasalla lenkkeillessäsi.

## Synkronointi Wahoosta

Wahoon yhdistäminen toimii samalla tavalla ja mahdollistaa myös **strukturoitujen
harjoitusten siirtämisen** takaisin Wahoo-tilillesi (katso
[Harjoitusohjelmat ja harjoitukset](training-plans.md)).

!!! info "Uudelleenyhdistäminen uusia oikeuksia varten"
    Jotkin ominaisuudet tarvitsevat lisää Wahoo-oikeuksia. Jos yhdistit Wahoon
    ennen ominaisuuden lisäämistä, saatat joutua katkaisemaan yhteyden ja
    yhdistämään uudelleen myöntääksesi uuden pääsyn.

## Alueiden ja FTP:n synkronointi

Voit synkronoida syke- ja tehoalueesi sekä FTP:si yhdistetystä palvelusta, jotta
profiilisi pysyy yhdenmukaisena sen laitteen kanssa, jolla harjoittelet.

## Aktiviteettien linkittäminen ohjelmaasi

Kun sinulla on [harjoitusohjelma](training-plans.md), ladatut aktiviteetit
yhdistetään automaattisesti kyseisen päivän suunniteltuun harjoitukseen (lajin
mukaan ja kun harjoituskuormitus ja kesto ovat riittävän lähellä). Voit myös linkittää tai
poistaa linkityksen käsin ohjelmakalenterista tai kojelaudan
aktiviteettikalenterista.

!!! note "Lisää yksityiskohtia tulossa"
    Vaiheittaiset kuvakaappaukset palveluiden yhdistämisestä lisätään tähän.
