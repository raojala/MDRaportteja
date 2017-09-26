# Järjestelmätestaus PT-08
Kirjoittaja: Rami Ojala, K8412, TTV16S3
## Tehtäväkuvaus

Projekti tiedon siirtäminen JIRA-työkalun varaan githubissa olevasta opensource repositoriosta.
 - Repositorio: https://github.com/doublespeakgames/adarkroom/

## Tehtävän aloitus

Internettiä selailemalla tulee paljon tietoa eri Python scripteistä, joiden on tarkoitus pullata Githubin API:n lävitse issuet ja tallentaa ne .CSV muotoon, jotta ne voidaan myöhemmin importata JIRA-kantaan, koska jirassa on CSV import.

En saanut internetin Python scriptejä toimimaan, pyörittelin myös Githubin API:a itsekkin, saatoin myös ehkä hieman C#:lla koodata myös omaa scriptiä. Tässä vaiheessa alkoi hieman tuntumaan että pakkohan tähän on olla helpompikin tapa olemassa ja jatkoin tutkimista.

Muutama "pieni" hetki myöhemmin löysin ensimmäisen johtolangan kun luin joltain satunaiselta foorumita "Jiran oma importti suoraan githubista".

## Jiran käyttö

Perus käyttäjätunnuksilla JIRA:n käyttö ei oikeen tahtonut tässä mittakaavassa onnistua, koska Github projektin tuonti JIRA:an, tapahtuu projektin luonnin yhteydessä ja projektin luonti tarvitsee Admin oikeudet.

Admin käyttäjätilin saatuani homma alkoi luistamaan paljon paremmin. JIRA:n käyttö oli paljon intuitiivisempaa, nyt kun kaikki oli siellä missä olettikin.

Aloin tekemään uutta projektia, jonka yhteydessä hain adarkroom repositorion osaksi JIRA kantaa. Prosessi oli aika suoraviivainen, eikä tarvinnut erikoisemmin mitään erikois täppejä tai kikkoja. Koko prosessi oli käytännössä, vain seuraava painikkeen painamista, lukuunottamatta kohtaa missä piti syöttää projektin tiedot ja projekti tyyppi (projektin tiedoissa syötettiin myös github tunnus jonka tarvi tietojen hakemiseen). Tässä kohtaan heitän sivuhuomiona myös sen, että kohde repositorio pitää olla tähdellä merkattu, jotta se näkyy JIRA:n haussa. Kaiken tämän jälkeen koko prosessi oli vaan napin painallusta.

### Vaihtoehtoista

Pienellä lisävaivalla, voit myös manuaalisesti projektin importtauksen yhteydessä määritellä issueiden liput manuaalisesti. Voit kartoittaa Github:in labelit JIRA:n omiin lippuihin per Github:n lippu.

Automaattisesti kartoittuvat flagit saattavat jälkeenpäin aiheuttaa hämmennystä, mahdollisesia sivuvaikutuksia olettaisin, että tehdyt issuet muuttuvat ei tehdyiksi, tai issuet jotka ovat flagattu irrelevantiksi "ei tehdä" flagille, näkyvät open flageina.

Viimeisellä sivulla voi vielä massa antaa joidenki flagien tilan done tai open.

## Loppusanat

Jos jotain suuria ongelmia tästä pitäisi keksiä, niin JIRA:n oma haku githubista, luo jokaiselle issuen tekijälle ja kommentoijalle oman käyttäjätilin JIRA:n tietokannassa, mikä täyttää tietokannan todella nopeasti isoissa opensource projekteissa. Tähänkin on vielä pakko lisätä, että nämä automaattisesti generoidut käyttäjätilit, ovat oletuksena pois päältä, ellei niitä erikseen aktivoida projektin tuonnin yhteydessä. Näiden turhien tilien poisto onnistuu todenäköisesti yhdellä SQL rivillä, sellaiselle joka sen taitaa.
