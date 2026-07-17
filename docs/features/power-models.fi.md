# Tehomallit

Teho-näkymä voi sovittaa tehokäyrääsi useita **teho–kesto-malleja** ja piirtää ne
todellisten ennätystesi päälle. Malli on kaava, joka kuvaa, miten pisimpään
ylläpidettävä teho laskee suorituksen pidentyessä — muutaman sekunnin spurtista
tasaiseen tuntiin. Mallinnettujen käyrien vertaaminen todellisiin suorituksiin
näyttää, missä olet jo lähellä potentiaaliasi ja missä on varaa parantaa.

## Mallit

openkoutsi sovittaa neljä mallia, joilla kullakin on omat vahvuutensa:

| Malli | Mihin sopii |
|---|---|
| **Kriittinen teho (2 param.)** | Klassinen kynnysmalli noin 2–20 minuutin alueella. |
| **Kriittinen teho (3 param.)** | Lisää realistisen katon lyhyille spurteille, joten se sopii myös noin 30 s suorituksiin. |
| **Eksponentiaalinen** | Seuraa tasaista laskua spurttitehosta kohti kynnystehoa. |
| **Potenssilaki** | Kuvaa hyvin käyrän pitkän, kestävyyspainotteisen osan. |

Kukin malli sovitetaan vain siihen kestoalueeseen, jota se kuvaa hyvin, ja
jokainen malli raportoi **sovitusvirheen** — keskimääräisen eron mallin ja
todellisten ennätystesi välillä. Pienempi sovitusvirhe tarkoittaa, että malli
vastaa sinua tarkemmin.

## Käyrien piirtäminen päälle

Teho-näkymässä valitse haluamasi mallit, niin ne piirretään katkoviivoina
todellisen tehokäyräsi päälle. Voit näyttää malleja niin monta tai vähän kuin
haluat:

- Missä katkoviiva osuu **todellisen** käyräsi päälle, malli on samaa mieltä
  kanssasi.
- Missä todellinen käyräsi jää mallin **alapuolelle**, kyseinen kesto voi olla
  testaamatta — vihje tehosta, jota sinussa saattaa piillä.

!!! info "Vain watteina"
    Mallikäyrät lasketaan watteina, joten ne näkyvät, kun tehokäyrä on
    näkymässä **Watteina**. Vaihda **W/kg**-näkymästä takaisin nähdäksesi ne.

## Arvioitu potentiaali

Käyrän alla **Arvioitu potentiaali** -taulukko muuttaa mallit konkreettisiksi
luvuiksi. Kullekin mallille se näyttää ennustetun parhaan tehosi neljälle
avainsuoritukselle todellisen ennätyksesi vieressä samalla kestolla:

| Ominaisuus | Suoritus | Mitä kuvaa |
|---|---|---|
| **Neuromuskulaarinen teho** | 5 sekuntia | Huippuspurttitehosi. |
| **Anaerobinen kapasiteetti** | 1 minuutti | Lyhyet, kovat suoritukset väsyneenä. |
| **Maksimaalinen aerobinen teho** | 5 minuuttia | Aerobisen moottorisi huippu. |
| **FTP** | ~20 minuuttia | Teho, jonka pystyt pitämään kynnyksellä. |

Taulukko listaa myös kunkin mallin sovitetut parametrit — kriittinen teho (CP),
anaerobinen työkapasiteetti (W′) ja maksimiteho (Pmax) niiltä osin kuin ne ovat
merkityksellisiä.

!!! note "Nämä ovat arvioita"
    Luvut syntyvät mallintamalla historiaasi jo tallentuneet suoritukset — ne
    eivät ole erillisen testin tulos. Mitä enemmän täysillä ajettuja lenkkejä eri
    kestoilla openkoutsi on nähnyt, sitä luotettavampia mallit ovat. Katso
    [tehokäyrä](fitness-metrics.md) siitä, miten ennätyksesi kerätään.
