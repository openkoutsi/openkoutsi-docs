# Aika vyöhykkeillä

openkoutsi laskee yhteen, kuinka kauan vietät aikaa kullakin harjoitusvyöhykkeellä,
ja näyttää sen **viikko viikolta** sekä **teholle** että **sykkeelle**. Se on nopein
tapa nähdä, oliko harjoittelusi niin kevyttä — tai niin kovaa — kuin tarkoitit.

## Viikkokaavio

Kojelaudallasi näkyy **Aika vyöhykkeillä** -kortti, jossa on yksi pinottu palkki
viikkoa kohti valitsemaltasi ajanjaksolta (kojelaudan aikavalitsimella). Vierekkäin
on kaksi kaaviota:

- **Teho** — aika kullakin tehovyöhykkeellä (vaatii tehodataa ja tehovyöhykkeet).
- **Syke** — aika kullakin sykevyöhykkeellä (vaatii sykedataa ja sykevyöhykkeet).

Kukin väri on yksi vyöhyke, viileästä (kevyt) lämpimään (kova), joten yhdellä
silmäyksellä näet, miten viikkosi jakautui — paljon sinistä ja vihreää
peruskestävyysjaksolla, enemmän oranssia ja punaista kun olet tehnyt kovia vetoja.

!!! info "Tarvitset vyöhykkeet käyttöön"
    Aika vyöhykkeillä lasketaan vain määrittelemillesi vyöhykkeille. Aseta syke- ja
    tehovyöhykkeesi **Profiilissa** tai
    [synkronoi ne yhdistetystä palvelusta](activities.md#alueiden-ja-ftpn-synkronointi).

## Miten se mitataan

openkoutsi käy jokaisen aktiviteetin teho- ja syketallennuksen läpi sekunti
sekunnilta ja laskee, kuinka monta sekuntia osuu kullekin vyöhykkeelle. Nämä
aktiviteettikohtaiset summat lasketaan sitten yhteen kunkin kalenteriviikon
(maanantaista alkaen) kaikista (pyöräily)aktiviteeteista.

## Historiasi pysyy paikallaan, kun muutat vyöhykkeitä

Aktiviteetin vyöhykejakauma **tallennetaan aktiviteettia käsiteltäessä** niillä
vyöhykkeillä, jotka sinulla oli sillä hetkellä. Jos myöhemmin muutat vyöhykkeitäsi
— uusi FTP, tuore kynnystesti — vain **tulevat** aktiviteetit käyttävät uusia
rajoja. Menneet viikot säilyttävät ne luvut, joilla ne tallennettiin, joten
historiasi ei muutu joka kerta kun kuntosi muuttuu.

!!! tip "Vanhempien lenkkien päivittäminen"
    Ennen tätä ominaisuutta tallennetuilla aktiviteeteilla ei vielä ole tallennettua
    jakaumaa. openkoutsi täydentää ne ensimmäisellä käyttökerralla nykyisillä
    vyöhykkeilläsi ja lukitsee ne sitten kuten muutkin.

## Aiheeseen liittyvää

- [Kuntomittarit](fitness-metrics.md) — harjoituskuormitus, muoto ja viikkokuormitus.
- [Aktiviteetit ja synkronointi](activities.md) — missä vyöhykejakauma näkyy ensin,
  aktiviteettikohtaisesti.
