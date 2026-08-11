# Tekoälyavustajat (MCP)

Voit antaa tekoälyavustajan — Clauden, GitHub Copilotin VS Codessa tai minkä
tahansa muun **Model Context Protocol** -yhteyskäytäntöä puhuvan — kysyä
harjoittelustasi suoraan openkoutsi-instanssiltasi sen sijaan, että kopioisit
lukuja keskusteluikkunaan.

Kysy *"miltä muotoni näyttää ennen lauantaita?"*, niin avustaja hakee nykyisen
kuntosi, väsymyksesi ja muotosi, tarkistaa missä kohtaa ohjelmaa olet ja vastaa
todellisen datasi pohjalta.

!!! info "Vain luku — ja vain *sinun* tietosi"
    Näin liitetty avustaja voi **lukea** eikä muuta. Se ei voi ladata, muokata
    tai poistaa mitään, ei muuttaa profiiliasi eikä nähdä toisen käyttäjän
    harjoittelua — ei edes silloin, kun ylläpidät instanssia itse.

## Mitä avustaja voi kysyä

Yhdeksän kysymystä, jotka on tarkoituksella muotoiltu sellaisiksi, joita valmentaja
oikeasti haluaa tietää — ei tietokantatauluiksi:

| Avustaja voi kysyä… | Ja saa |
|---|---|
| **Harjoitustilanne** | Kunto, väsymys ja muoto, viimeaikainen kuormitus ja kehityssuunta — tältä päivältä tai miltä tahansa menneeltä päivältä |
| **Viimeisimmät aktiviteetit** | Tuoreimmat lenkkisi tärkeimpine lukuineen |
| **Aktiviteetin haku** | Yksi lenkki päivämäärän tai kuvauksen perusteella |
| **Aktiviteetin tiedot** | Yksittäinen lenkki tarkemmin — intervallit, vyöhykkeet, aerobiset luvut |
| **Ohjelman tilanne** | Missä kohtaa harjoitusohjelmaa olet ja miten toteutuma näyttää |
| **Tavoitteiden edistyminen** | Miten kukin tavoite etenee suhteessa tavoitearvoon ja päivämäärään |
| **Tehoprofiili** | Parhaat tehot vakiokestoilla |
| **Intensiteettijakauma** | Tuliko jaksosta polarisoitunut, pyramidimainen vai kynnyspainotteinen |
| **Vyöhykesummat** | Kertynyt aika kullakin teho- ja sykevyöhykkeellä |

!!! tip "Kysy myös menneestä, älä vain tästä päivästä"
    **Harjoitustilanne** ottaa vastaan päivämäärän, joten *"missä kunnossa olin
    viikkoa ennen viimevuotista gran fondoa?"* on kysymys, johon avustaja
    todella osaa vastata — ja *"onko tämä nousujakso jyrkempi kuin edellinen?"*
    on kaksi tällaista kysymystä rinnakkain. Kaikki siirtyy kysytyn päivän
    mukana: kuntoluvut, kehityssuunta ja neljän viikon volyymisummat, joten
    vastaukset ovat aidosti vertailukelpoisia. Jos kysyt päivää, joka on ennen
    historiasi alkua, avustaja kertoo sen ja nimeää päivän, josta tietosi
    alkavat — se ei raportoi hiljaisesti nollia.

Mitä se **ei** tarkoituksella saa:

- **Raakadatavirtoja.** Kolmen tunnin lenkillä on noin yksitoistatuhatta
  näytettä kanavaa kohti. Avustaja saa laskettuja yhteenvetoja — se on koko
  suunnittelun idea, ei kierrettävä rajoitus.
- **Sijaintiasi.** GPS-koordinaatteja ei palauteta koskaan.
- **Postilaatikkoasi, tiliäsi tai mitään ylläpitoon liittyvää.**
- **Täyttä vientiä.** Oikeutta `athlete:export` ei voi käyttää tätä kautta. Yksi
  kutsu, joka lataa koko tietueesi, on täsmäkysymyksen vastakohta — ks.
  [Henkilökohtaiset käyttöoikeustunnisteet](personal-access-tokens.md#vientioikeus-on-oma-lajinsa).

!!! warning "Tietosi päätyvät sille, joka avustajaa pyörittää"
    Tämä kannattaa pysähtyä lukemaan. Kun Claude tai Copilot hakee kuntolukusi,
    ne kulkevat kyseisen avustajan palveluntarjoajalle täsmälleen kuten kaikki
    muukin, mitä siihen kirjoitat. Se on oma tietoinen valintasi ja täysin
    järkevä — mutta se on eri tietosuoja-asetelma kuin openkoutsin tavallinen
    käyttö, jossa harjoitustietosi eivät poistu omalta palvelimeltasi. Ks.
    [Datasi ja tekoäly](../data-and-ai.md).

## Ennen kuin aloitat

Kolmen asian on oltava kunnossa:

1. **Instanssisi julkaisee rajapinnan.** Se on oletuksena päällä; ylläpitäjä voi
   kytkeä sen pois kohdasta **Ylläpito → Asetukset → Salli MCP-palvelin**.
2. **Saat siihen yhteyden.** Osoite on instanssisi API-osoite, jonka perässä on
   `/mcp` — esimerkiksi `https://api.oma-instanssi.example/mcp`. Jos käytät
   openkoutsia internetin yli, asennuksen tehneen on pitänyt reitittää tuo polku
   läpi.
3. **Sinulla on henkilökohtainen käyttöoikeustunniste** oikeilla oikeuksilla. Se
   on seuraava vaihe.

## Vaihe 1 — Luo tunniste

Mene kohtaan **Asetukset → Henkilökohtaiset käyttöoikeustunnisteet → Uusi
tunniste**. Anna nimi, jonka tunnistat myöhemmin (`claude desktop`, `vs code`),
valitse vanhenemisaika ja myönnä nämä viisi oikeutta:

| Oikeus | Tarvitaan mihin |
|---|---|
| `metrics:read` | Harjoitustilanne, tehoprofiili, intensiteettijakauma, vyöhykesummat |
| `athlete:read` | Harjoitustilanne ja tehoprofiili — molemmat tarvitsevat tämän **lisäksi** oikeuden `metrics:read` |
| `activities:read` | Viimeisimmät aktiviteetit, aktiviteetin haku, aktiviteetin tiedot |
| `plans:read` | Ohjelman tilanne |
| `goals:read` | Tavoitteiden edistyminen |

Myönnä vähemmän, jos haluat rajata enemmän: pelkillä oikeuksilla `metrics:read`
ja `athlete:read` avustaja näkee kuntokuvasi eikä mitään yksittäisistä lenkeistä.
Jätä `athlete:export` rastittamatta — mikään avustajan työkalu ei voi käyttää
sitä.

Tunniste näytetään **kerran**. Kopioi se ennen ikkunan sulkemista. Kaikki muu
tunnisteista — vanheneminen, peruminen ja se, mihin ne eivät koskaan yllä — on
sivulla [Henkilökohtaiset käyttöoikeustunnisteet](personal-access-tokens.md).

## Vaihe 2 — Osoita avustaja siihen

Useimmat MCP-asiakasohjelmat tarvitsevat samat kaksi tietoa: osoitteen ja
tunnisteen `Authorization`-otsakkeessa. Yleinen asetusmuoto näyttää tältä:

```json
{
  "mcpServers": {
    "openkoutsi": {
      "url": "https://api.oma-instanssi.example/mcp",
      "headers": {
        "Authorization": "Bearer okp_…"
      }
    }
  }
}
```

**VS Codelle** kannattaa käyttää alla olevaa ohjetta — se pitää tunnisteen poissa
asetustiedostosta.

!!! tip "Ei kauttaviivaa loppuun"
    Osoite päättyy muotoon `/mcp`, ei `/mcp/`. Ne ovat eri polkuja, eikä
    jälkimmäinen vastaa.

## Vaihe 3 — VS Code

VS Code keskustelee MCP-palvelimien kanssa **Copilot Chatin agenttitilassa**.
Tarvitset tuoreen VS Coden, johon Copilot Chat on asennettu ja kirjauduttu.

### Lisää palvelin

Avaa komentopaletti (`Ctrl+Shift+P` / `Cmd+Shift+P`) ja suorita **MCP: Open User
Configuration**. Se avaa henkilökohtaisen `mcp.json`-tiedostosi, joka on voimassa
kaikissa työtiloissa. Lisää:

```json
{
  "inputs": [
    {
      "type": "promptString",
      "id": "openkoutsi-pat",
      "description": "openkoutsi-käyttöoikeustunniste",
      "password": true
    }
  ],
  "servers": {
    "openkoutsi": {
      "type": "http",
      "url": "https://api.oma-instanssi.example/mcp",
      "headers": {
        "Authorization": "Bearer ${input:openkoutsi-pat}"
      }
    }
  }
}
```

Tallenna. VS Code kysyy tunnisteen ensimmäisellä yhdistämiskerralla ja säilyttää
sen omassa salaisuusvarastossaan — joten juuri muokkaamassasi tiedostossa ei
koskaan ole tunnistettasi.

!!! warning "Käytä *käyttäjän* asetuksia, älä työtilan"
    VS Code lukee myös projektikansion `.vscode/mcp.json`-tiedostoa. Sellainen
    päätyy vahingossa versionhallintaan hyvin helposti. Harjoitustietosi ovat
    henkilökohtaisia ja tunniste on tunnistautumisväline, joten pidä tämä
    käyttäjän asetuksissa, joissa se kuuluu sinulle eikä projektille.

### Käynnistä ja kokeile

1. Komentopaletti → **MCP: List Servers** → **openkoutsi** → **Start Server**.
2. Avaa Copilot Chat ja vaihda tilavalitsin **Agent**-tilaan.
3. Tarkista työkalukuvake — openkoutsin työkalujen pitäisi näkyä listassa. Poista
   rasti niistä, joita et halua sen käyttävän.
4. Kysy jotain:

    > Miltä harjoitustilanteeni näyttää ja olenko ohjelmassa aikataulussa?

Avustaja kutsuu ensin **Harjoitustilannetta** — se ei tarvitse syötteitä ja
kertoo, koskeeko kiinnostava kysymys kuormitusta, palautuneisuutta vai ohjelman
toteutumaa — ja jatkaa siitä.

## Jos yhteys ei muodostu

| Mitä näet | Mitä se yleensä tarkoittaa |
|---|---|
| Asiakasohjelma ei tavoita palvelinta lainkaan | Osoite on väärä tai `/mcp` ei ole reititetty openkoutsiin ulkopuolelta. Kokeile osoitetta selaimessa: sinun pitäisi saada lyhyt virhe pyyntötavasta, ei "ei löydy" -sivua. |
| Viesti siitä, että MCP-palvelin on poissa käytöstä | Ylläpitäjäsi on kytkenyt sen pois kohdasta **Ylläpito → Asetukset**. |
| Avustaja yhdistää, mutta jokainen työkalu torjutaan | Tunniste on tuntematon, vanhentunut tai peruttu. Tarkista sen tila kohdasta **Asetukset → Henkilökohtaiset käyttöoikeustunnisteet**. |
| Osa työkaluista toimii, osa ilmoittaa puuttuvasta oikeudesta | Tunnisteelle myönnettiin vähemmän oikeuksia kuin työkalu tarvitsee. Oikeuksia ei voi muokata — luo korvaava tunniste ja peru vanha. |
| Kaikki on hidasta tai torjutaan ajoittain | Olet osunut pyyntörajaan, joka lasketaan henkilöä eikä tunnistetta kohti. Odota hetki. |

!!! note "Puuttuva oikeus ei ole virhe"
    Avustajat näkevät **kaikki** työkalut, myös ne joita tunnisteesi ei voi
    kutsua, ja torjunta tulee takaisin luettavana selityksenä eikä
    virhetilanteena. Työkalujen piilottaminen saisi myöntämättä jääneen oikeuden
    näyttämään ominaisuudelta, jota instanssissasi ei ole. Jos avustaja kertoo
    tarvitsevansa oikeuden `plans:read`, järjestelmä toimii juuri niin kuin
    pitääkin.

## Yhteyden katkaiseminen

Mikä tahansa näistä pysäyttää avustajan välittömästi — valitse sopivin:

- **Peru tunniste** (**Asetukset → Henkilökohtaiset käyttöoikeustunnisteet →
  Peru**). Astuu voimaan heti seuraavalla pyynnöllä, ilman siirtymäaikaa. Tätä
  kannattaa käyttää, jos tunniste on voinut vuotaa.
- **Poista palvelin** asiakasohjelmasi asetuksista, jos haluat vain irrottaa
  yhden työkalun.
- **Pyydä ylläpitäjää kytkemään rajapinta pois** koko instanssista. Huomaa, että
  se vaikuttaa kaikkiin sen käyttäjiin.

Tunnisteesi katoaa myös itsestään aikanaan — jokainen tunniste vanhenee, ja saat
siitä ennakkovaroituksen [postilaatikkoosi](inbox.md).
