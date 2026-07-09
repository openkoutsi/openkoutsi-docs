# Oman tekoälymallin käyttö (BYOK)

openkoutsin [tekoälyominaisuudet](../data-and-ai.md) — aktiviteettianalyysi,
päivittäinen harjoitustila sekä tekoälyn tekemät ohjelmat ja harjoitukset —
toimivat minkä tahansa **OpenAI-yhteensopivan** chat-rajapinnan kanssa. Sen
sijaan että luottaisit siihen, mitä instanssisi ylläpitäjä on määrittänyt, voit
osoittaa openkoutsin **omaan** päätepisteeseesi kohdassa **Asetukset → Tekoäly /
LLM**. Tästä käytetään usein nimitystä **BYOK — "bring your own key"** (tuo oma
avaimesi).

!!! info "Milloin tätä kannattaa käyttää?"
    **Jaetussa/julkisessa instanssissa** — yleisin tapaus. Pyynnön tekee
    openkoutsin palvelin, joten BYOK antaa sinun valita, **mille
    palveluntarjoajalle ja mallille** se menee:

    - Käytä palveluntarjoajaa (ja **aluetta**), johon luotat — esim. pitääksesi
      datasi tietyllä lainkäyttöalueella, kuten **EU:ssa**.
    - Käytä **omaa tiliäsi ja API-avaintasi** hostatulla palveluntarjoajalla
      instanssin avaimen sijaan.
    - Jotkin instanssit **edellyttävät** oman mallin tuomista tekoälyominaisuuksien
      käyttöön.

    **Itse hostatussa instanssissa, jossa olet ylläpitäjä** — voit osoittaa
    **paikalliseen malliin** (Ollama, LM Studio, llama.cpp…), joka toimii samalla
    koneella, jolloin mikään ei poistu omalta laitteistoltasi.

!!! warning "Mistä pyyntö tulee"
    Syöttämääsi päätepistettä kutsuu **openkoutsin taustapalvelu**, ei selaimesi.
    Julkisessa instanssissa taustapalvelu toimii jollakin palvelimella, joten
    omalla koneellasi oleva malli (`http://localhost:11434/v1`) **ei** ole
    tavoitettavissa, ellet altista sitä internetiin. Käytä julkisessa instanssissa
    hostattua palveluntarjoajaa (tai itse hostattua mallia julkisella URL:lla).

## Käyttöönotto

Avaa **Asetukset → Tekoäly / LLM**. Näet kortin, jossa on kolme kenttää:

| Kenttä | Mitä syötetään |
|---|---|
| **Perus-URL** | OpenAI-yhteensopivan palvelimesi päätepiste, esim. `http://localhost:11434/v1` paikalliselle Ollamalle tai `https://api.openai.com/v1` palveluntarjoajalle. |
| **Malli** | Pyydettävän mallin nimi, esim. `llama3.2` tai `gpt-4o-mini`. |
| **API-avain** | Valinnainen. Jätä tyhjäksi avaimettomalle paikalliselle palvelimelle; liitä palveluntarjoajan avain hostatulle palvelulle. |

Napsauta **Testaa yhteys** lähettääksesi pienen "hei"-viestin ja varmistaaksesi,
että malli vastaa, ja sen jälkeen **Tallenna**. Kortin yläreunan ilmoitus
kertoo, käytätkö **omaa LLM-palvelintasi** vai **tämän instanssin LLM:ää**.

!!! tip "Testaa-painike toimii ennen tallennusta"
    *Testaa yhteys* käyttää sitä, mitä lomakkeessa on juuri nyt, joten voit
    tarkistaa URL:n, mallin ja avaimen ennen niiden tallentamista.

=== "Paikallinen malli (Ollama)"

    Paras **itse hostattuun instanssiin**, jossa openkoutsi ja Ollama toimivat
    samalla koneella (tai samassa verkossa), jotta taustapalvelu tavoittaa
    paikallisen URL:n.

    1. Asenna [Ollama](https://ollama.com/) ja lataa malli, esim.
       `ollama pull llama3.2`.
    2. Aseta kohdassa **Asetukset → Tekoäly / LLM**:
        - **Perus-URL**: `http://localhost:11434/v1` (osoite, jolla *taustapalvelu*
          tavoittaa Ollaman)
        - **Malli**: `llama3.2`
        - **API-avain**: jätä tyhjäksi
    3. **Testaa yhteys** ja sitten **Tallenna**.

    Pyynnöt paikalliseen malliin eivät koskaan poistu koneeltasi — mutta
    julkisessa instanssissa taustapalvelu ei tavoita koneesi `localhost`-osoitetta,
    joten tämä toimii vain, kun palvelin itse tavoittaa URL:n.

=== "Hostattu palveluntarjoaja"

    1. Hanki API-avain ja OpenAI-yhteensopiva perus-URL palveluntarjoajaltasi.
    2. Aseta kohdassa **Asetukset → Tekoäly / LLM**:
        - **Perus-URL**: palveluntarjoajan `/v1`-päätepiste, esim. `https://api.openai.com/v1`
        - **Malli**: palveluntarjoajan tarjoama malli, esim. `gpt-4o-mini`
        - **API-avain**: palveluntarjoajan avaimesi
    3. **Testaa yhteys** ja sitten **Tallenna**.

    Pyynnöt menevät kyseiselle palveluntarjoajalle **sen** tietosuoja- ja
    säilytysehtojen mukaisesti — katso [Datasi ja tekoäly](../data-and-ai.md).

## Kun oma palvelimesi on asetettu

Heti kun tallennat oman **Perus-URL:si**, openkoutsi käyttää **vain** sinun
määrityksiäsi kaikissa tekoälyominaisuuksissa. Instanssin malli ja avain
ohitetaan kokonaan — joten instanssin API-avainta ei koskaan lähetetä
palvelimellesi eikä avaintasi sekoiteta instanssin päätepisteeseen.

Palataksesi instanssin LLM:ään käytä kortin **Tyhjennä**-toimintoa. Tulevat
tekoälytoiminnot käyttävät tällöin sitä, mitä ylläpitäjäsi on määrittänyt (jos
mitään).

## Miten API-avaimesi tallennetaan

API-avaimesi on **salattu levossa** palvelimella (AES-256/Fernet, avaimella joka
johdetaan käyttäjätunnuksestasi), eikä sitä **koskaan palauteta selaimeesi**
tallennuksen jälkeen. Kun tekoälyominaisuus suoritetaan, palvelin purkaa
salauksen vain muistissa tehdäkseen pyynnön puolestasi — kaikki tekoälykutsut
välitetään taustapalvelun kautta, joten avaimesi ja pyyntödatasi eivät poistu
itse hostatusta instanssistasi muuten kuin saavuttaakseen valitsemasi
päätepisteen.

!!! note "Avaimen jättäminen tyhjäksi säilyttää nykyisen"
    Jos olet jo tallentanut avaimen, **API-avain**-kentän jättäminen tyhjäksi
    seuraavalla tallennuskerralla säilyttää sen ennallaan. Käytä **Tyhjennä**
    poistaaksesi sen (esimerkiksi siirtyessäsi avaimettomaan paikalliseen
    malliin).

## Sallitut palvelimet

Jotkin instanssit rajaavat BYOK:n **hyväksyttyjen palveluntarjoajien listaan**.
Tällöin **Perus-URL**-kenttä muuttuu sallittujen palvelinten pudotusvalikoksi
vapaan tekstin sijaan, ja listan ulkopuolisen URL:n tallennus hylätään. Jos
haluamaasi palveluntarjoajaa ei ole listalla, kysy ylläpitäjältäsi.

## Vianetsintä

!!! warning "Yhteys epäonnistui"
    - **Yhteys hylätty / aikakatkaisu** — perus-URL ei ole tavoitettavissa
      palvelimelta. Paikallisen mallin kohdalla varmista, että se on käynnissä ja
      tavoitettavissa sieltä, missä openkoutsi ajetaan (kontissa ajettava palvelin
      ei välttämättä tavoita kannettavasi `localhost`-osoitetta).
    - **Todennus epäonnistui** — tarkista API-avaimesi tai tyhjennä se
      avaimettomalle paikalliselle palvelimelle.
    - **Ei sallittujen listalla** — instanssisi rajaa BYOK-URL:t; valitse jokin
      pudotusvalikosta tai kysy ylläpitäjältäsi.
    - **Vastaus ei ollut odotetussa muodossa** — päätepiste ei ole
      OpenAI-yhteensopiva tai mallin nimi on väärä.

Lisätietoa siitä, mitä kukin tekoälyominaisuus lähettää mallille ja minne se
menee, löydät sivulta [Datasi ja tekoäly](../data-and-ai.md).
