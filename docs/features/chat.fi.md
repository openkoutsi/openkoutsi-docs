# Kysy Koutsilta

Muualla openkoutsissa Koutsi päättää, mitä se kertoo sinulle: päivittäinen kortti
etusivulla, analyysi lenkin alla, opastus tavoitteen kohdalla. **Kysy Koutsilta**
kääntää asetelman. Saat tekstikentän, ja Koutsi vastaa hakemalla oikeat tietosi.

Juuri se on olennaista. Koutsi voi lukea aktiviteettisi, ohjelmasi, tavoitteesi,
vyöhykkeesi ja kuntolukusi, joten se voi vastata sellaiseen mihin yleinen
chattibotti ei pysty:

- *"Tapahtumaani on kolme viikkoa ja kuntoni on yhä miinuksella — pitäisikö olla huolissaan?"*
- *"Ensi viikko menee töihin. Mistä harjoituksista kannattaa tinkiä?"*
- *"Kynnysvetoni hajoavat aina viimeisellä toistolla. Mitä sille voi tehdä?"*
- *"Pitäisikö minun tehdä nyt enemmän Z2:ta vai enemmän kovaa?"*

## Käyttöönotto

Kysy Koutsilta ilmestyy sivupalkkiin, kun otat käyttöön asetuksen
**Profiili → Analyysi → Anna Koutsin hakea tietoja**.

Se jakaa saman kytkimen agenttipohjaisen päiväkortin kanssa eikä käytä omaansa,
koska molemmat tarvitsevat samaa: luvan hakea tietoja valmiin yhteenvedon sijaan.
Keskustelu joka ei näkisi harjoitteluasi olisi vain yleinen chattibotti
pyöräilyasussa.

!!! info "Tekoälymallisi täytyy tukea työkalukutsuja"
    Tietojen hakeminen tarkoittaa työkalujen kutsumista, eivätkä kaikki mallit
    osaa sitä. Jos valitsemasi malli ei osaa, sivu kertoo sen ja ohjaa sinut
    tekoälyasetuksiin sen sijaan että antaisi kirjoittaa kysymyksen johon ei
    koskaan olisi tullut vastausta. Katso
    [Oman tekoälymallin käyttö](using-your-own-ai-model.md).

## Mistä Koutsi keskustelee ja mistä ei

Koutsi on pyöräilyvalmentaja ja pysyy sellaisena. Neljä kysymystyyppiä saa neljä
eri käsittelyä:

| Kysyt aiheesta | Mitä Koutsi tekee |
|---|---|
| **Valmennus** — vedot, jaksotus, kunto ja muoto, vauhdinjako, ohjelman muokkaus | Vastaa täysin. Tämä on sen työ. |
| **Lähialueet** — pitkän lenkin ravinto, uni, voimaharjoittelu, ajoasento, taktiikka | Vastaa kuten valmentaja: käytännöllisesti ja yleisellä tasolla, väittämättä olevansa erikoisasiantuntija. |
| **Lääketiede** — oireet, kipu, vammat, sairaudet, lääkitys tai se onko jokin kehossasi vaarallista | **Ei vastaa.** Ohjaa lääkäriin. |
| **Muu** — kaikki mikä ei liity harjoitteluusi | Kieltäytyy lyhyesti ja ohjaa takaisin aiheeseen. |

### Lääketieteellinen raja

Tämä on syytä sanoa suoraan, koska openkoutsi säilyttää sykettä, painoa ja
rasitustietoja, ja se tekee tekoälystä hyvin helposti terveysasioissa
auktoriteetilta kuulostavan.

**Koutsi ei kerro onko oire vakava, ei arvaa diagnoosia eikä kehota harjoittelemaan
oireiden läpi.** Jos kysyt rintakivusta, toistuvasti turpoavasta nivelestä,
huolestuttavasta leposykkeestä tai siitä kuinka paljon syömistä kannattaa vähentää
ennen kisaa, se kertoo että asia on sen avun ulkopuolella ja että sinun kannattaa
puhua lääkärille tai muulle pätevälle ammattilaiselle.

Kyse ei ole siitä että Koutsi olisi avuton. Se ei todella tiedä, eikä sen taustalla
oleva kielimalli tiedä myöskään — sillä on tehotiedostosi, ei sairaushistoriaasi.

!!! warning "Jos jokin tuntuu väärältä, kysy ihmiseltä"
    Chatti-ikkuna on väärä paikka terveyskysymykselle, olipa se kuinka kätevä
    tahansa. Ota yhteyttä lääkäriin.

Myös toinen puoli on tärkeä: neljän tunnin lenkin ravinto on kysymys
valmentajalle, ja Koutsin kuuluu vastata siihen. Jos se kieltäytyy jostain mikä on
selvästi valmennuskysymys, se on vika josta kannattaa ilmoittaa.

## Keskustelu

Kirjoita kysymys ja paina Enter. Koutsilla voi kestää hetki — se tekee usein
useita hakuja ennen kuin kirjoittaa mitään, ja se kertoo mitä on tekemässä
("Koutsi tarkistaa tehokäyrääsi…").

Jokainen haku jää keskusteluun lyhyenä rivinä — "Tehokäyräsi", "Viimeaikaiset
harjoituksesi" — siinä järjestyksessä kuin Koutsi ne teki, heti vastauksen
yläpuolelle. Rivit ilmestyvät yksi kerrallaan työn edetessä, joten näet miten
pitkällä Koutsi on sen sijaan että tuijottaisit pyörivää kuvaketta, ja ne jäävät
näkyviin merkinnäksi siitä mihin vastaus todella perustui.

!!! note "Haut kertovat nimet, eivät tietoja"
    Rivi kertoo *että* Koutsi luki tehokäyräsi, ei sitä mitä se sieltä löysi.
    Löydökset ovat vastauksessa.

Vastaukset ilmestyvät sitä mukaa kun ne kirjoitetaan, ja ne tallennetaan matkan
varrella. Voit ladata sivun uudelleen, sulkea välilehden tai jatkaa keskustelua
puhelimella; vastaus jatkuu ja on siellä kun palaat.

Tarkentavat kysymykset toimivat odotetusti — Koutsi muistaa mitä olette
keskustelleet. Mitä se *ei* säilytä, ovat hakemansa tiedot: joka vuorolla se lukee
harjoittelusi uudestaan. Se on tarkoituksellista ja tarkoittaa että huomisen
vastaus perustuu huomisen lenkkeihin eikä vanhentuneeseen kopioon.

### Keskustelut

Jokainen keskustelu säilyy sivupalkissa, nimettynä aloituskysymyksesi mukaan,
kunnes poistat sen. Poistaminen vie kaiken keskustelussa olleen, myös oman
kirjoituksesi, eikä sitä voi perua.

Yhden keskustelun pituudelle on raja. Kun saavutat sen, aloita uusi — et menetä
mitään, koska Koutsi hakee harjoittelutietosi joka tapauksessa uudestaan joka
kerta.

### Koutsi ehdottaa, sinä päätät

Koutsi voi **ehdottaa** sinulle harjoitusohjelmaa tai muutosta siihen — eikä
muuta.

Pyydä sellaista — *"voisitko tehdä minulle kahdeksan viikkoa lokakuun mäkiseen
gran fondoon?"*, *"siirrä koko juttu viikolla eteenpäin"*, *"tee torstaista
kevyempi"* — niin se luonnostelee ehdotuksensa ja näyttää sen korttina vastauksensa
alla, **Kyllä**- ja **Ei**-painikkeineen. Siinä vaiheessa harjoittelullesi ei ole
tapahtunut mitään. Vain **Kyllä** muuttaa jotain, ja jos et koskaan vastaa,
mikään ei muutu.

Muutama asia kortista kannattaa tietää:

- **Se kertoo mitä hyväksyminen arkistoi.** Uusi ohjelma arkistoi seuraamasi
  ohjelmat, joiden ajanjakso menee sen kanssa päällekkäin, joten kortti nimeää ne
  ennen kuin klikkaat — ei jälkeenpäin. Mitään ei menetetä: voit palauttaa
  arkistoidun ohjelman ohjelmasivulta. Mutta sinun kuuluu tietää sen tapahtuvan.
- **Luonnostelu vie hetken.** Koutsi kirjoittaa viikot kunnolla eikä vain hahmottele
  niitä, joten odota muutamaa sekuntia. Toisinaan se ei saa yhteyttä tekoälymalliin
  tähän osaan, jolloin viikot kirjoittaa openkoutsin oma ohjelmageneraattori;
  kortti kertoo, kun näin käy.
- **Tarjous on voimassa vuorokauden.** Nuku yön yli, jos haluat. Vuorokauden
  jälkeen se vanhenee ja pyydät uuden.
- **Voit jatkaa keskustelua ensin.** Jatkokysymyksen esittäminen ei peru tarjousta
  — voit palata hyväksymään sen myöhemmin. *Uusi* tarjous korvaa vanhan.
- **Vastaus on painike, ei kirjoitettu "kyllä".** Tämä on tarkoituksellista:
  päätöksen on oltava keskustelun ulkopuolella, jotta mitään keskustelussa
  sanottua ei voi erehtyä pitämään suostumuksenasi.

Jos harjoittelusi on ehtinyt muuttua sen jälkeen kun Koutsi luonnosteli jotain —
loit toisen ohjelman, aloituspäivä on mennyt, muutettava harjoitus on jo tehty —
hyväksyminen hylätään sen sijaan että se toteutettaisiin, ja Koutsi luonnostelee
uuden kun pyydät.

Kaikki muu on edelleen neuvoja. Koutsi ei voi merkitä harjoitusta tehdyksi, ei voi
liittää lenkkiä suunniteltuun harjoitukseen eikä voi rakentaa ohjelman loppuviikkoja
uudelleen. Kun vastaus koskee ohjelmaasi, mukana on linkki jolla voit avata sen ja
tehdä muut muutokset itse.

## Rajat

Kysy Koutsilta on ainoa tekoälyominaisuus jonka voit käynnistää niin usein kuin
haluat, ja jokainen kysymys maksaa useita tekoälykutsuja yhden sijaan. Siksi
kysymyksille on päivittäinen raja. Et yleensä huomaa sitä; kun olet lähellä, sivu
alkaa näyttää montako on jäljellä.

Palvelimella jolla tekoälyominaisuudet vaativat tilauksen, keskustelu kuuluu saman
tilauksen piiriin kuin kaikki muukin — katso
[Tekoälyominaisuudet, tilaukset ja BYOK](ai-subscriptions.md).

## Jos jokin menee pieleen

Koska Koutsin täytyy hakea tietoja vastatakseen, keskustelukysymys ei voi turvautua
yksinkertaisempaan vastaukseen kuten päiväkortti voi. Siksi epäonnistuessaan se
kertoo syyn:

- **Koutsi oli varattu** — palvelimellasi oli muita tekoälytöitä eikä se ehtinyt
  sinun kysymykseesi ajoissa. Yritä hetken kuluttua uudelleen.
- **Mallisi ei osaa käyttää työkaluja** — valitsemasi mallin pysyvä rajoitus, ei
  ohimenevä häiriö. Valitse toinen malli.
- **Tekoälypalvelimella oli ongelma** tai **siihen ei saatu yhteyttä** — kannattaa
  yrittää uudelleen; jos toistuu, tarkista palvelin tekoälyasetuksista.

Kaikki mitä on järkevää yrittää uudelleen tarjoaa **Yritä uudelleen** -painikkeen.

## Minne sanasi menevät

Kirjoittamasi lähetetään sille tekoälymallille jonka palvelimesi on määritetty
käyttämään, tai omallesi jos käytät sellaista. Keskustelusi tallennetaan omaan
tietokantaasi muiden tietojesi rinnalle, sisältyvät tietojen vientiin nimellä
`chat.json`, ja poistetaan tilisi mukana.

Jos käytät omaa malliasi (BYOK), se mitä kyseinen malli tekee viesteillesi on
sinun ja sen välinen asia — katso [Datasi ja tekoäly](../data-and-ai.md) ja
[Tietosuoja ja suostumus](../privacy.md).
