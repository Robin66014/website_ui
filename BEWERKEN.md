# De website zelf aanpassen

Deze handleiding legt uit hoe u de website van Senioren Actief Zaltbommel aanpast (ontwerp 2, met iconen). U hoeft niet te kunnen programmeren. U werkt in de webeditor van GitHub, in uw browser.

## Zo past u een bestand aan

1. Ga naar de repository op GitHub en log in.
2. Klik op het bestand dat u wilt aanpassen, bijvoorbeeld `index.html`.
3. Klik rechtsboven op het **potloodje** ("Edit this file").
4. Zoek het blok dat u wilt aanpassen. Alle blokken die u mag aanpassen beginnen met
   `<!-- BEWERKEN: ... -->` en eindigen met `<!-- EINDE BEWERKEN -->`.
   Tip: druk op **Ctrl+F** om te zoeken op het woord `BEWERKEN`.
5. Pas alleen de gewone tekst aan. Laat de tekens tussen `<` en `>` staan.
6. Klik op de groene knop **Commit changes...** en daarna nog een keer op **Commit changes**.
7. Na één à twee minuten staat de wijziging op de website. Ververs de pagina om het te zien.

Iets fout gegaan? Op GitHub kunt u altijd terug naar een eerdere versie (tabblad **History** bij het bestand).

### Iets op alle pagina's tegelijk veranderen

Sommige gegevens staan op meer pagina's, zoals het telefoonnummer. Dat verandert u het makkelijkst in één keer:

1. Open de repository en druk op de **punt-toets** ( `.` ) op uw toetsenbord. Er opent een uitgebreide editor (github.dev).
2. Druk op **Ctrl+Shift+H**. Links verschijnt **Zoeken en vervangen**.
3. Typ bovenaan wat u zoekt (bijvoorbeeld het oude telefoonnummer) en daaronder de nieuwe tekst.
4. Klik op het knopje **Alles vervangen** (rechts naast het vervangvak).
5. Klik links op het pictogram met de vertakking (**Source Control**), typ een korte omschrijving en klik op **Commit & Push**.

## De bestanden

| Bestand | Wat staat erin |
|---|---|
| `index.html` | De homepage |
| `lessen.html` | Lessen, lestijden en het rooster met vakanties |
| `stoelgym.html` | De stoelgymles op woensdag |
| `contact.html` | Lid worden, contributie, route en veelgestelde vragen |
| `404.html` | De pagina die verschijnt als een adres niet bestaat |
| `style.css` | Kleuren, lettergroottes en opmaak voor de hele site |
| `img/` | Foto's, logo en pictogrammen |
| `sitemap.xml` | Lijst van pagina's voor Google |

## Het blok "Actueel" op de homepage

Bestand: `index.html`, blok `BEWERKEN: actueel`.

- **Tekst veranderen:** pas de zin tussen `<p>` en `</p>` aan. Het vetgedrukte begin staat tussen `<strong>` en `</strong>`.
- **Blok leeg laten:** haal alles weg van `<section class="actueel"` tot en met de eerstvolgende `</section>`. Bewaar het voorbeeld uit het commentaar, dan kunt u het later weer terugzetten.
- **Een evenement toevoegen:** zet er een regel bij, zoals:
  `<p><strong>Zaterdag 12 juni: wandeltocht.</strong> We lopen samen een rondje. Opgeven bij Johan.</p>`

## Een les laten vervallen

1. Zet een bericht in het blok **Actueel** op de homepage (zie hierboven), bijvoorbeeld:
   `<p><strong>Donderdag 8 april geen les.</strong> De sportzaal is die dag gesloten.</p>`
2. Wilt u de dag ook in het rooster? Open `lessen.html`, blok `BEWERKEN: rooster`, en voeg een regel toe op de goede plek in de lijst:
   `<li class="geen-les"><svg class="icoon" aria-hidden="true" focusable="false"><use href="img/iconen.svg#calendar-x"></use></svg><span><strong>Donderdag 8 april 2027</strong> Geen les</span></li>`
   Door `class="geen-les"` en het icoon `#calendar-x` krijgt de regel een rode rand en een kalender met een kruisje.

## Het rooster voor een nieuw seizoen

Bestand: `lessen.html`, blok `BEWERKEN: rooster`.

- Elke datum is één regel van `<li>` tot en met `</li>`. Kopieer een bestaande regel en pas de datum en tekst aan.
- Dagen zonder les krijgen `class="geen-les"` en het icoon `#calendar-x`. Gewone data hebben het icoon `#calendar-dots`.
- Oude data mag u weghalen.
- Pas ook de kop aan (bijvoorbeeld "Rooster 2027–2028") en de titel bovenin het bestand, tussen `<title>` en `</title>`.
- Zet in `sitemap.xml` bij `lessen.html` de datum van vandaag tussen `<lastmod>` en `</lastmod>`.

## Lestijden veranderen

De lestijden staan op meer plekken. Pas ze overal aan:

| Waar | Bestand en blok |
|---|---|
| Homepage, kaart "Wanneer is de les?" | `index.html`, blok `BEWERKEN: lestijden` |
| Lessenpagina, "Lestijden" | `lessen.html`, blok `BEWERKEN: lestijden` |
| Stoelgym (alleen woensdag) | `stoelgym.html`: het blok `BEWERKEN: tijd, adres en kosten` en de twee beschrijvingen bovenin het bestand (`meta name="description"` en `og:description`) |
| Veelgestelde vragen (woensdag) | `contact.html`: de vraag "Ik ben minder goed ter been" en dezelfde vraag in de **gegevens voor Google** bovenin het bestand |
| Gegevens voor Google | `index.html`, bovenin, bij `openingHoursSpecification`. Tijden schrijft u daar zo: `"13:30"`. Dagen staan in het Engels (`Tuesday`, `Wednesday`, `Thursday`) |

## Contactgegevens veranderen

**Tip:** gebruik **Zoeken en vervangen** in github.dev (zie bovenaan). Dan mist u geen enkele plek.

### Telefoonnummer

Het nummer staat op twee manieren in de bestanden:

- zoals u het ziet: `06-50446425`
- in de link waarmee u belt, internationaal en zonder de eerste 0: `+31650446425`

Vervang ze allebei. Ze staan hier:

| Waar | Bestanden |
|---|---|
| Belbalk helemaal bovenaan | alle vijf de `.html`-bestanden, blok `BEWERKEN: telefoonnummer bovenaan` |
| Koraalrode belknop | `index.html` (twee keer), `lessen.html`, `stoelgym.html`, `contact.html` (twee keer), `404.html` |
| Voettekst | alle vijf de `.html`-bestanden, blok `BEWERKEN: voettekst` |
| In de tekst | `contact.html`: stap 1 van "Zo meldt u zich aan" en de vraag "Kan ik eerst een proefles doen?" |
| Gegevens voor Google | `index.html` bovenin (`"telephone"`), `contact.html` bovenin (de vraag over de proefles) |
| Beschrijving voor Google | `contact.html`, de regel `meta name="description"` bovenin |

### E-mailadres

Het adres is een beetje verstopt, zodat spamprogramma's het minder makkelijk vinden. Voor bezoekers werkt het gewoon. Het staat er op twee manieren:

- in de link: `mailto:johannolly%40live.nl` (`%40` betekent @)
- als tekst: `johannolly&#64;live.nl` (`&#64;` betekent ook @)

Typt u een nieuw adres? Gebruik dan ook `%40` en `&#64;` in plaats van @. Het adres staat in de blokken "Liever mailen?" (op alle pagina's), in de voettekst (alle pagina's) en in de contactkaart op `contact.html`.

### Naam van de contactpersoon

Zoek op `Johan van der Meijden`. De naam staat in de voettekst, in de blokken onderaan elke pagina en op `contact.html`.

### Adres van de sportzaal

Zoek op `[HUISNUMMER INVULLEN]` en `[POSTCODE INVULLEN]` en vul het echte huisnummer en de postcode in. Het adres staat hier:

- voettekst: alle vijf de `.html`-bestanden
- `index.html`: blok `BEWERKEN: adres` en de **gegevens voor Google** bovenin (`streetAddress` en `postalCode`)
- `stoelgym.html`: blok `BEWERKEN: tijd, adres en kosten`
- `contact.html`: blok `BEWERKEN: adres en route`

Zet het huisnummer ook in de Google Maps-links (`index.html` en `contact.html`). Verander daar
`query=Klipperstraat%2C+Zaltbommel` in bijvoorbeeld `query=Klipperstraat+12%2C+Zaltbommel`.
Gebruik een `+` in plaats van een spatie.

### Facebook

Zoek op `https://www.facebook.com/INVULLEN` en vervang dit door het echte adres van de Facebookpagina. Het staat in de voettekst (alle pagina's), op `contact.html` en in de **gegevens voor Google** in `index.html` (`"sameAs"`).

## Contributie veranderen

Zoek op `€120`. Het bedrag staat hier:

- `index.html`: blok `BEWERKEN: contributie` en de beschrijving bovenin (`meta name="description"`)
- `stoelgym.html`: blok `BEWERKEN: tijd, adres en kosten`
- `contact.html`: blok `BEWERKEN: contributie`, de vraag "Wat kost het?" (op de pagina én bij de **gegevens voor Google** bovenin) en de twee beschrijvingen bovenin (`meta name="description"` en `og:description`)

Op de homepage staat het bedrag ook bij "Waarom Senioren Actief?" ("€10 per maand" en "€120 per jaar"). Op de homepage en de contactpagina staat ook "Dat is €10 per maand". Pas dat mee aan.

## Een foto toevoegen of vervangen

1. Maak de foto eerst kleiner, liefst ongeveer 1024 pixels breed en kleiner dan 200 KB. Dat kan gratis op [squoosh.app](https://squoosh.app). Daar kunt u de foto ook als WebP opslaan, dat laadt sneller.
2. Geef de foto een duidelijke naam met kleine letters en streepjes, zoals `stoelgym-zaltbommel-oefeningen-op-stoel.jpg`.
3. Ga op GitHub naar de map `img`, klik op **Add file** en daarna op **Upload files**. Sleep de foto erin en klik op **Commit changes**.
4. Zet de foto op de pagina. Plak dit blok op de plek waar de foto moet komen (bijvoorbeeld bij `BEWERKEN: foto van de stoelgym` in `stoelgym.html`):

```html
<figure class="foto">
  <img src="img/stoelgym-zaltbommel-oefeningen-op-stoel.jpg" width="1024" height="768" loading="lazy" alt="Leden doen oefeningen zittend op een stoel in de sportzaal">
  <figcaption>Oefenen op en bij de stoel.</figcaption>
</figure>
```

- `width` en `height`: de breedte en hoogte van de foto in pixels. Op Windows ziet u die met de rechtermuisknop: **Eigenschappen**, tabblad **Details**.
- `alt`: beschrijf in een zin wat er op de foto te zien is. Mensen die slecht zien, laten deze tekst voorlezen. Ook Google leest hem.
- `loading="lazy"`: laat dit staan, behalve bij de grote foto bovenaan de homepage.

Vraag altijd toestemming aan de mensen die herkenbaar op de foto staan.

## Lettertype

De site gebruikt het lettertype **Atkinson Hyperlegible Next**. Het is gemaakt voor mensen die slecht zien. De bestanden staan in de map `fonts` en worden vanaf de eigen site geladen. Er gaat dus niets naar Google of een ander bedrijf. De licentie (vrij te gebruiken) staat in `fonts/OFL.txt`.

U hoeft hier niets aan te doen. Haal de map `fonts` niet weg.

## Veelgestelde vragen aanpassen

Bestand: `contact.html`, blok `BEWERKEN: veelgestelde vragen`. Elke vraag is één blok:

```html
<details>
  <summary>Hier de vraag?<svg class="icoon icoon-plus" aria-hidden="true" focusable="false"><use href="img/iconen.svg#plus"></use></svg><svg class="icoon icoon-min" aria-hidden="true" focusable="false"><use href="img/iconen.svg#minus"></use></svg></summary>
  <div class="antwoord"><p>Hier het antwoord.</p></div>
</details>
```

- Een vraag toevoegen: kopieer een heel blok (van `<details>` tot en met `</details>`) en pas de vraag en het antwoord aan.
- Zet dezelfde vraag en hetzelfde antwoord ook in de **gegevens voor Google** bovenin `contact.html`, bij `"mainEntity"`. Let op de komma's tussen de vragen.

## Iconen

De kleine plaatjes (telefoon, klok, kaart enzovoort) komen uit één bestand: `img/iconen.svg`. Een icoon zet u zo neer:

`<svg class="icoon" aria-hidden="true" focusable="false"><use href="img/iconen.svg#phone"></use></svg>`

Verander alleen het woord na `#`. Deze iconen zijn er: `phone` (telefoon), `envelope-simple` (mail), `house` (huis), `barbell` (halter), `armchair` (stoel), `hand-waving` (zwaaiende hand), `clock` (klok), `calendar-dots` (kalender), `calendar-x` (kalender met kruisje), `map-pin` (locatie), `currency-eur` (euro), `question` (vraagteken), `users-three` (groep mensen), `certificate` (diploma), `megaphone-simple` (megafoon), `smiley` (lachend gezicht), `facebook-logo`, `caret-right` (pijltje), `plus`, `minus` en `arrow-square-out` (andere website).

De iconen komen van Phosphor Icons (vrije MIT-licentie, zie `img/iconen-LICENSE.txt`).

## Kleuren veranderen

Alle kleuren staan bovenaan in `style.css`, bij `:root`. Elke kleur heeft een naam, zoals `--kleur-primair` of `--kleur-cta`. Verandert u daar de code (bijvoorbeeld `#1e54b4`), dan verandert de kleur overal. Let op: tekst moet goed leesbaar blijven. Kies bij twijfel een donkerder kleur.

## Wat u beter niet verandert

- De tekens tussen `<` en `>`, zoals `<p class="...">`, behalve waar deze handleiding dat zegt.
- De bestandsnamen van de pagina's (`index.html`, `lessen.html` enzovoort). Google en links van andere sites gebruiken die namen.
- Het bestand `CNAME`, als dat er is. Daarin staat het webadres van de site (zie README.md).
