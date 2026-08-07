# Henkilökohtaiset käyttöoikeustunnisteet

Kun kirjaudut openkoutsiin, selaimesi saa istunnon, joka kestää noin tunnin ja
uusiutuu sitten hiljaa itsestään. Se toimii sovellukselle erinomaisesti — ja
kaikelle muulle ei lainkaan: yöllinen varmuuskopiointiskripti, ajastettu työ,
puhelin tai tekoälyavustaja, joka ottaa yhteyttä instanssiisi selaimen
ulkopuolelta, ei voi pitää tunnistetta hallussaan tuntia pidempään.

**Henkilökohtainen käyttöoikeustunniste** on juuri tuo puuttuva tunniste. Luot
sen itse kohdassa **Asetukset → Henkilökohtaiset käyttöoikeustunnisteet**, päätät
tarkalleen mitä se saa tehdä, ja perut sen milloin haluat.

!!! info "Tunniste voi aina tehdä *vähemmän* kuin sinä"
    Se ei ole toinen salasana. Tunniste yltää vain siihen, minkä sille myönnät,
    ja on asioita, joihin se ei yllä **koskaan** myönnätpä mitä tahansa —
    ylläpito, kirjautumisrajapinnat, postilaatikkosi, tekoälyominaisuudet ja itse
    tunnistesivu. Se tuo lisää **kestoa**, ei lisää valtuuksia.

## Tunnisteen luominen

Avaa **Asetukset → Henkilökohtaiset käyttöoikeustunnisteet** ja valitse **Uusi
tunniste**.

| Kenttä | Mitä siihen laitetaan |
|---|---|
| **Nimi** | Mihin tunniste on tarkoitettu, jotta lista on ymmärrettävä vielä puolen vuoden kuluttua — `yöllinen varmuuskopio`, `läppärin synkronointi`, `puhelin`. |
| **Oikeudet** | Vain se, mitä työkalu oikeasti tarvitsee (ks. alla). |
| **Vanhenee** | 7, 30, 90, 180 tai 365 päivän kuluttua. Oletus on 90. |

Kun vahvistat, tunniste näytetään **kerran**:

```
okp_3f0c1e9a-…_Rk9…
```

!!! warning "Kopioi se nyt — sitä ei näytetä uudelleen"
    Palvelimelle jää vain tunnisteen yksisuuntainen sormenjälki, joten kukaan —
    ei ylläpitäjäsi eikä sinä itse — voi hakea sitä jälkikäteen. Jos tunniste
    katoaa, peru se ja luo uusi. Tämä ei ole rajoitus, jota pitäisi kiertää: se
    on syy siihen, ettei vuotanut tietokanta vuoda tunnisteitasi.

Käsittele sitä kuin salasanaa. Sen haltija voi käyttää tietojasi myöntämiesi
oikeuksien rajoissa, kunnes tunniste vanhenee tai perut sen.

## Oikeudet: myönnä vain tarpeellinen

Yksi oikeus tarkoittaa yhtä resurssia ja yhtä toimintoa. Myönnä pienin joukko,
jolla työ hoituu — varmuuskopiointiskripti tarvitsee *lukuoikeuden*, ei
poisto-oikeutta.

| Oikeus | Antaa tunnisteen… |
|---|---|
| `activities:read` | lukea aktiviteettisi, datavirrat, kierrokset ja intervallit |
| `activities:write` | ladata, muokata, käsitellä uudelleen ja poistaa aktiviteetteja |
| `athlete:read` | lukea profiilisi, vyöhykkeesi ja asetuksesi |
| `athlete:write` | muuttaa profiiliasi, vyöhykkeitäsi ja asetuksiasi |
| `metrics:read` | lukea päivittäiset mittarit, kunto/väsymys/muoto sekä teho- ja matkaennätykset |
| `metrics:write` | laskea johdetut mittarit uudelleen tallennetuista aktiviteeteista |
| `goals:read` / `goals:write` | lukea / hallita tavoitteitasi |
| `plans:read` / `plans:write` | lukea / hallita harjoitusohjelmia ja suunniteltuja harjoituksia |
| `workouts:read` / `workouts:write` | lukea / hallita strukturoituja harjoituksia |
| `achievements:read` / `achievements:write` | lukea saavutuksesi / merkitä ne nähdyiksi |
| `integrations:read` / `integrations:write` | nähdä yhdistetyt palvelut / yhdistää, synkronoida ja katkaista yhteys |

### Vientioikeus on oma lajinsa

`athlete:export` esitetään erillään muista, ja tarkoituksella. Yksi kutsu sen
turvin lataa **koko tietueesi** — jokaisen aktiviteetin, ohjelman, tavoitteen ja
mittarin, postilaatikkosi sekä raa'at FIT-tiedostosi — yhtenä zip-pakettina.

Se on täysin järkevä asia varmuuskopiointityökalulle haluta, minkä vuoksi se on
ylipäätään tarjolla eikä kielletty. Se ei silti ole samanlainen "lukuoikeus" kuin
muut, joten sitä ei niputeta niiden joukkoon: rastitat sen tarkoituksella, ja
jokainen käyttökerta kirjataan instanssisi valvontalokiin.

!!! note "Miksi postilaatikko on saavutettavissa näin muttei muuten"
    Tunniste ei voi koskaan kutsua viestirajapintaa — osin siksi, että
    postilaatikkosi on kirjeenvaihtoa palvelun kanssa eikä harjoitusdataa, ja
    osin siksi, että juuri sinne saapuu varoitus tunnisteen vanhenemisesta.
    Tunniste ei saa pystyä lukemaan viestiä, jossa kerrotaan sen pääsyn olevan
    katkeamassa. Vienti on eri asia: erikseen myönnetty, tarkoituksellinen,
    valvontalokiin kirjattu kertalataus omasta tietueestasi — ei postiasi
    tarkkaileva silmukka.

## Mitä tunniste ei voi koskaan tehdä

Tämän valvoo palvelin, ei käyttöliittymä:

| Ulottumattomissa | Miksi |
|---|---|
| **Ylläpitonäkymä** | Vaikka olisit ylläpitäjä. Ylläpitäjän asema ei saa laajentaa sitä, mitä tunniste voi lukea *kenenkään* harjoitusdatasta. |
| **Kirjautumis- ja tilirajapinnat** | Tunniste ei voi koskaan luoda tai uusia toista tunnistetta eikä poistaa tiliäsi. |
| **Tunnisteiden luonti, listaus ja peruminen** | Tunniste ei voi tehdä toista tunnistetta. Ketjua ei synny. |
| **Postilaatikkosi** | Ks. yllä. |
| **Tekoälyominaisuudet** | Ne maksavat instanssillesi rahaa, eikä tunniste saa pystyä kuluttamaan sitä. |

Kaikki muu pätee normaalisti. Jos instanssisi vaatii suostumuksen tietojen
käsittelyyn ennen latausta, tunnisteella tehty lataus hylätään aivan kuten
selaimestakin tehty.

## Vanheneminen

**Jokainen tunniste vanhenee. Pysyvää ei ole**, ja pisin mahdollinen voimassaoloaika
on vuosi.

Tunniste, joka ei koskaan kuole, elää pidempään kuin integraatio, jota varten se
tehtiin, pidempään kuin läppäri, jolle se tallennettiin, ja yleensä pidempään
kuin muistikuvasi sen luomisesta. Vanhenemispäivä on se mekanismi, joka lopulta
siivoaa jälkesi työkalusta, jonka käytön lopetit.

Vanheneminen ei tule yllätyksenä. openkoutsi kertoo siitä:

| Milloin | Missä |
|---|---|
| 7 päivää ennen vanhenemista | [Postilaatikkosi](inbox.md) ja sähköposti |
| 1 päivä ennen | Postilaatikko ja sähköposti |
| Vanhenemispäivänä | Postilaatikko ja sähköposti |

Jokainen näistä lähetetään tasan kerran, joten tästä ei tule päivittäistä
jankkausta. Sovelluksen sisäinen viesti lähetetään aina; sähköposti vaatii
vahvistetun osoitteen ja instanssin, jolle sähköposti on määritetty, ja voit
kytkeä sen pois kohdasta **Profiili → Analyysi** ("Lähetä sähköpostia ennen
käyttöoikeustunnisteen vanhenemista") säilyttäen silti sovelluksen sisäisen
ilmoituksen.

!!! tip "Tunnisteita ei voi jatkaa"
    Vanhenemisaika, kuten oikeudet ja nimikin, lyödään lukkoon tunnistetta
    luotaessa — muokkausnäkymää ei ole. Kun tunniste on loppumassa, luo uusi,
    osoita työkalusi siihen ja peru vanha. Näin merkintä siitä, mihin kukin
    tunniste milläkin hetkellä kykeni, pysyy rehellisenä.

## Peruminen

Valitse tunnisteen kohdalta **Peru** ja vahvista. Se lakkaa toimimasta
**välittömästi** — välimuistia tai siirtymäaikaa ei ole, joten sitä yhä käyttävä
työkalu saa hylkäyksen heti seuraavalla pyynnöllään.

Käytä sitä heti, kun tunniste on saattanut vuotaa: liimattu julkiseen
koodivarastoon, tallennettu läppärille jota sinulla ei enää ole, tai palvelun
hallussa johon et enää luota.

!!! note "Perutut ja vanhentuneet tunnisteet jäävät listaan"
    Niitä ei poisteta, ja se on tarkoituksellista. Lista on oma merkintäsi
    siitä, mitä olet luonut ja milloin kutakin viimeksi käytettiin — ja
    palvelimella sormenjäljen säilyttäminen tarkoittaa, että *perumasi*
    tunnisteen esittäjä tunnistetaan yhä juuri siksi, eikä hän huku
    satunnaisten arvausten joukkoon.

Kaksi asiaa perua tunnisteita myös ilman käyntiä tällä sivulla:

- **Salasanan vaihtaminen** perii kaikki tunnisteesi. Se, mikä sai vaihtamaan
  salasanan, koskee myös tilisi jakamia tunnisteita.
- **Tilin poistaminen** vie ne mukanaan kaiken muun ohella.

## Tunnisteen käyttö

Lähetä se `Authorization`-otsakkeessa, täsmälleen siellä missä selaimen
istuntotunnistekin kulkisi:

```bash
curl https://oma-instanssi.example/api/activities \
  -H "Authorization: Bearer okp_3f0c1e9a-…_Rk9…"
```

Muutama käytännön huomio:

- **Pidä se poissa komentohistoriasta ja versionhallinnasta.** Laita se
  ympäristömuuttujaan tai tiedostoon, jota vain sinä voit lukea.
- **Rajoitukset lasketaan tunnistekohtaisesti**, ei konekohtaisesti, joten yksi
  vilkas skripti ei hidasta selailuasi (eikä kenenkään muun).
- **403 tarkoittaa puuttuvaa oikeutta**; vastaus kertoo, mitä oikeutta se
  odotti. **401** tarkoittaa, että tunniste on tuntematon, vanhentunut tai
  peruttu — tai että ylläpitäjäsi on kytkenyt ominaisuuden pois.

Esimerkiksi täyden varmuuskopion lataamiseen tarvitaan tunniste, jolla on
`athlete:export`:

```bash
curl -fL https://oma-instanssi.example/api/athlete/export \
  -H "Authorization: Bearer $OPENKOUTSI_TOKEN" \
  -o openkoutsi-varmuuskopio-$(date +%F).zip
```

## Jos korttia ei näy

Henkilökohtaiset käyttöoikeustunnisteet ovat oletuksena käytössä, mutta
itsemajoittaja voi kytkeä ne pois omalta instanssiltaan — täysin järkevä valinta,
jos hän ei halua koneellaan olevan lainkaan pitkäikäisiä tunnisteita. Silloin
korttia ei näy, ja aiemmin luodut tunnisteet lakkaavat toimimasta. Kysy
ylläpitäjältäsi.

## Ylläpitäjille

Instanssisi ylläpitäjä voi **listata ja perua** tunnisteesi, mutta ei koskaan
luoda niitä puolestasi eikä nähdä niiden **nimiä** (ne kirjoitat sinä, ja nimi
voi kertoa paljonkin). Tämä on olemassa tilannetta varten, jossa tunniste on
selvästi vaarantunut eikä sen omistajaa tavoiteta — silloin sen pysäyttäminen on
velvollisuus, ei mukavuus.

Jos näin käy, **saat siitä tiedon**: ylläpitäjän tekemä peruminen saapuu
postilaatikkoosi kuten mikä tahansa muu viesti ja kirjataan instanssin
valvontalokiin.
