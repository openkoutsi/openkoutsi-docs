# Tekoälyominaisuudet, tilaukset ja BYOK

openkoutsin [tekoälyominaisuudet](../data-and-ai.md) — aktiviteettianalyysi,
päivittäinen harjoitustila sekä tekoälyn tuottamat ohjelmat ja harjoitukset —
käyttävät tavallisesti mallia, jonka instanssisi ylläpitäjä on määrittänyt. Osa
instansseista **veloittaa tekoälystä**, joka käyttää palvelimen omaa mallia,
pitäen kaiken muun maksuttomana. Tämä sivu selittää, mikä muuttuu tällaisilla
instansseilla ja kuinka tarkistat oman tilasi.

!!! info "Muu openkoutsi pysyy maksuttomana"
    Tilausrajoitus koskee vain **instanssin** mallia käyttäviä
    tekoälyominaisuuksia. Aktiviteettien lataus, Strava/Wahoo-synkronointi,
    kuntomittarit, ohjelmat ja kaikki muu toimivat aivan kuten ennenkin.

## Mikä muuttuu rajoitetulla instanssilla

Kun ylläpitäjä ottaa rajoituksen käyttöön, **instanssin** tekoälymallin käyttö
vaatii **tekoälyn käyttöoikeuden tilauksen** (tilillesi myönnetyn oikeuden). Jos
sinulla ei ole sitä, sinulla on kaksi vaihtoehtoa:

1. **Tuo oma tekoälymallisi (BYOK).** Osoita openkoutsi omaan
   OpenAI-yhteensopivaan päätepisteeseesi kohdassa **Asetukset → AI / LLM**. BYOK
   toimii aina, myös rajoitetulla instanssilla, koska pyyntö menee *sinun*
   palveluntarjoajallesi, ei instanssin — katso
   [Oman tekoälymallin käyttö](using-your-own-ai-model.md).
2. **Tilaa.** Pyydä käyttöoikeutta ylläpitäjältäsi. Kun yrität käyttää
   tekoälyominaisuutta ilman tilausta (ja ilman BYOK:ia), openkoutsi näyttää
   viestin "Tämän palvelimen tekoälyominaisuudet vaativat tilauksen" sen sijaan,
   että se suorittaisi toiminnon.

## Tilasi tarkistaminen

**Asetukset → AI / LLM** näyttää rivin, joka kuvaa nykyisen tekoälyn
käyttöoikeutesi:

| Näet | Mitä se tarkoittaa |
|---|---|
| **Sisältyy** | Instanssi ei rajoita tekoälyä — kaikki toimii. |
| **Tilaus voimassa** (mahdollisesti *… asti*) | Sinulla on tekoälyn käyttöoikeus; instanssin malli on käytettävissä. |
| **Käytät omaa tekoälypalvelintasi** | Olet ottanut BYOK:in käyttöön; omaa mallia käytetään eikä tilausta tarvita. |
| **Ei käytettävissä — tilaa tai lisää oma palvelin** | Instanssi rajoittaa tekoälyä, eikä sinulla ole tilausta eikä BYOK:ia. |

!!! note "Automaattinen analyysi rajoitetulla instanssilla"
    Jos otit käyttöön automaattisen aktiviteettianalyysin tai päivittäisen
    harjoitustilan mutta sinulla ei ole käyttöoikeutta, kytkimet pysyvät
    tallennettuina mutta eivät tee mitään — asetussivu selittää syyn. Ne
    jatkuvat automaattisesti, kun tilaat tai otat BYOK:in käyttöön.

## Ylläpitäjille

Rajoitus on **oletuksena pois päältä**, joten tuore itse isännöity instanssi
toimii täsmälleen kuten ennenkin, kunnes otat sen käyttöön.

### Rajoituksen käyttöönotto

**Hallintakonsolin → instanssiasetuksissa** ota käyttöön **Vaadi tilaus
instanssin LLM:lle**. Tämän jälkeen vain käyttäjät, joilla on tekoälyn
käyttöoikeus (tai oma BYOK-malli), voivat käyttää instanssin
tekoälyominaisuuksia.

### Käyttöoikeuden myöntäminen ja peruuttaminen

**Hallintakonsolin → käyttäjät** -näkymässä jokaisella käyttäjällä on
**LLM-käyttöoikeus** -hallinta. Myönnä käyttöoikeus (halutessasi
päättymispäivämäärällä) tai peruuta se myöhemmin. Myöntäminen on tässä vaiheessa
manuaalista — päätät itse kuka saa käyttöoikeuden, esimerkiksi erikseen sovitun
maksun jälkeen.

### Käyttötilastojen lukeminen

**LLM-käyttö** -kortti kokoaa yhteen, kuinka monta tokenia kukin käyttäjä on
kuluttanut **instanssin** mallilla, näyttäen **syöte- ja tulostetokenit
erikseen** sekä erittelyn **palveluntarjoajittain**. Valitse ajanjakso
(viikko/kuukausi-tarkkuudella) nähdäksesi tokenit käyttäjää kohti kuukaudessa —
hyödyllistä keskimääräisen tekoälykustannuksen laskemiseen käyttäjää kohti.
Käyttäjien **omilla** malleilla (BYOK) tehtyjä kutsuja ei koskaan lasketa, koska
instanssi ei maksa niistä mitään.

Katso mitä kukin tekoälyominaisuus lähettää mallille ja minne, kohdasta
[Datasi ja tekoäly](../data-and-ai.md).
