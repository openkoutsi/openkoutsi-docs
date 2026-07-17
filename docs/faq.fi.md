# UKK

Muutamia yleisiä kysymyksiä. Tämä lista kasvaa ajan myötä.

### Mikä openkoutsi on?

Itse isännöitävä pyöräilyvalmennusalusta. Lataat tai synkronoit lenkkisi, seuraat
kuntosi kehitystä ja noudatat harjoitusohjelmaa — kaikki hallinnassasi olevalta
palvelimelta pilvipalvelun sijaan.

### Mihin datani tallennetaan?

openkoutsia pyörittävälle palvelimelle. Jokaisella käyttäjällä on **oma
yksityinen tietokantansa** ja tiedostotallennuksensa, joten aktiviteettisi ja
ohjelmasi näkyvät vain sinulle. Voit viedä datasi tai poistaa tilisi milloin
tahansa.

### Voiko joku muu — valmentaja tai ylläpitäjä — nähdä aktiviteettini?

Ei. openkoutsi toimii yhtenä instanssina, jossa jokainen käyttäjä säilyttää oman
yksityisen datansa. Valmentajaroolia tai jaettua tiimidataa ei ole; ylläpitäjä
hallinnoi tilejä ja instanssin asetuksia mutta ei näe harjoitusdataasi.

### Miten rekisteröidyn?

Se riippuu instanssista. Jokainen instanssi tukee **kutsuja** — ylläpitäjä
lähettää sinulle kutsulinkin tilin luomiseksi. Osa instansseista mahdollistaa myös
**itserekisteröinnin**: valitse kirjautumissivulla **Luo tili**, rekisteröidy
sähköpostiosoitteellasi ja avaa sähköpostiisi lähetetty vahvistuslinkki
aktivoidaksesi tilisi. Jos rekisteröitymisvaihtoehtoa ei ole, pyydä ylläpitäjältä
kutsu. Katso [Aloittaminen](getting-started.md).

### Unohdin salasanani.

Napsauta kirjautumissivulla **Unohditko salasanan?**. Jos instanssissa on
sähköposti käytössä, anna sähköpostiosoitteesi, niin lähetämme palautuslinkin (se
vanhenee tunnissa). Muussa tapauksessa sivu näyttää, miten tavoitat ylläpitäjän,
joka voi luoda sinulle palautuslinkin.

### Miten otan yhteyttä instanssin ylläpitäjään?

Jokaista instanssia pyörittää **ylläpitäjä** (operaattori, joka isännöi sitä).
**Unohditko salasanan?** -sivu näyttää ylläpitäjän yhteystiedon, kun sellainen on
määritetty, ja sama yhteystieto löytyy kohdasta **Asetukset → Tietoja**. Käytä
sitä tavoittaaksesi instanssiasi pyörittävän henkilön — tiliapuun,
tietosuojapyyntöihin tai mihin tahansa, mitä sovellus ei itse voi tehdä
puolestasi.

!!! info "Ylläpitäjät: reitittäkää yhteysosoitteenne sovellukseen"
    Jos pyörität instanssia, voit ohjata julkaistuun operaattoriosoitteeseesi
    lähetetyn postin näkymään suoraan ylläpitäjän postilaatikossa. Ominaisuus on
    valinnainen ja oletuksena pois päältä; katso käyttöönotto-opas pääprojektin
    repositoriosta. Julkisessa instanssissa julkaistu yhteystieto on
    `lassi@koutsi.dev`.

### Onko minun pakko yhdistää Strava tai Wahoo?

Ei. Integraatiot ovat valinnaisia. Voit ladata FIT-tiedostot käsin ja käyttää
jokaista analyysiominaisuutta yhdistämättä mitään ulkoista palvelua.

### Miksi Wahoo-yhteyteni ei riittänyt harjoitusten siirtämiseen?

Strukturoitujen harjoitusten siirtäminen vaatii ylimääräisiä Wahoo-oikeuksia. Jos
yhdistit Wahoon ennen kuin tämä ominaisuus oli olemassa, katkaise yhteys ja
yhdistä uudelleen myöntääksesi ne. Katso
[Aktiviteetit ja synkronointi](features/activities.md).

### Onko tämä kehittäjä- tai API-dokumentaatio?

Ei — tämä sivusto on **käyttöopas**. Kehittäjien asennustiedot, käyttöönotto ja
API-yksityiskohdat löytyvät openkoutsin pääprojektin repositoriosta.

### Löysin jotain puuttuvaa tai epäselvää.

Näitä ohjeita laajennetaan aktiivisesti. Avaa issue
[openkoutsi-docs-repositoriossa](https://github.com/openkoutsi/openkoutsi-docs).
