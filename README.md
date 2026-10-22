# Website Senioren Actief Zaltbommel

De website van sportvereniging Senioren Actief Zaltbommel (50+Actief): gym voor senioren in Zaltbommel.
Komt te staan op **https://www.seniorenactiefzaltbommel.nl**.

- Gewone HTML en één stylesheet (`style.css`). Geen framework, geen build-stap en geen JavaScript.
- Geen cookies, tracking of ingesloten kaarten, dus geen cookiebanner nodig.
- Teksten, rooster of contactgegevens aanpassen? Zie **[BEWERKEN.md](BEWERKEN.md)**.

## Over het ontwerp

Het ontwerp is gemaakt met de UI/UX Pro Max-richtlijnen voor een toegankelijke site ("Accessible & Ethical", patroon "Trust & Authority + Conversion"):

- kleuren uit het logo, alle gewone tekst met een contrast van 7:1 of hoger;
- lettertype Atkinson Hyperlegible Next, zelf gehost;
- iconen naast elke menuknop en kop (Phosphor Icons, MIT-licentie);
- kaarten met "Alles op een rij" op de homepage en veelgestelde vragen om open te klappen;
- geen animaties: alleen een korte kleurovergang bij aanwijzen, en die valt weg als iemand in het systeem "minder beweging" heeft ingesteld.

De keuzes staan in `design-system/senioren-actief-zaltbommel/MASTER.md` in de projectmap (niet in deze repository).

## Bestanden

| Bestand | Inhoud |
|---|---|
| `index.html` | Homepage |
| `lessen.html` | Lessen en rooster |
| `stoelgym.html` | Stoelgym op woensdag |
| `contact.html` | Lid worden, contributie, route en veelgestelde vragen |
| `404.html` | Pagina voor adressen die niet bestaan |
| `style.css` | Alle opmaak en kleuren |
| `img/` | Foto's, logo, pictogrammen en `iconen.svg` (alle iconen in één bestand) |
| `fonts/` | Lettertype Atkinson Hyperlegible Next (vrije licentie, zie `fonts/OFL.txt`) |
| `sitemap.xml`, `robots.txt` | Voor zoekmachines |
| `favicon.ico`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `site.webmanifest` | Het logo als pictogram in het tabblad, bij bladwijzers en op het beginscherm van telefoons |
| `CNAME` | Het eigen webadres voor GitHub Pages |
| `.nojekyll` | Zegt tegen GitHub dat de bestanden niet bewerkt hoeven te worden |

## De site online zetten met GitHub Pages

De bestanden staan in de repository `Robin66014/website_ui`. Daarna zijn er nog drie stappen.

### 1. GitHub Pages aanzetten

1. Open de repository op GitHub en klik op **Settings**.
2. Klik links op **Pages**.
3. Kies bij **Build and deployment**, onder **Source**, voor **Deploy from a branch**.
4. Kies bij **Branch** voor `main` en de map `/ (root)`. Klik op **Save**.
5. Bij **Custom domain** staat dan `www.seniorenactiefzaltbommel.nl`, uit het bestand `CNAME`. Staat het er niet? Typ het zelf in en klik op **Save**.

De site staat nu klaar. Hij is pas te zien op het eigen adres als de DNS (stap 2) goed staat.

### 2. DNS instellen bij de registrar

Log in bij het bedrijf waar het domein `seniorenactiefzaltbommel.nl` is geregistreerd, bijvoorbeeld TransIP, Mijndomein, Hostnet, Strato of Versio. Open de **DNS-instellingen** van het domein.

1. **Haal oude records weg** voor `www` en voor het domein zelf (`@`), zoals een parkeerpagina of een oude website. E-mailrecords (MX) laat u staan.
2. **Voeg een CNAME-record toe voor `www`:**

   | Type | Naam | Waarde |
   |---|---|---|
   | CNAME | `www` | `robin66014.github.io.` |

3. **Voeg vier A-records toe voor het domein zelf**, zodat ook `seniorenactiefzaltbommel.nl` (zonder www) werkt:

   | Type | Naam | Waarde |
   |---|---|---|
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |

4. Optioneel, voor IPv6, vier AAAA-records voor `@`:
   `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153` en `2606:50c0:8003::153`.

Sommige registrars willen `@` leeg laten of de volledige domeinnaam invullen. De punt aan het eind van `robin66014.github.io.` mag soms ook weg. Kijk dan in de uitleg van de registrar.

Het duurt een paar minuten tot 24 uur voordat de nieuwe DNS overal werkt.

### 3. HTTPS aanzetten

1. Ga terug naar **Settings** en **Pages** in de repository.
2. Wacht tot daar staat dat de DNS-controle gelukt is ("DNS check successful").
3. Vink **Enforce HTTPS** aan. Lukt dat nog niet, wacht dan een uur en probeer het opnieuw.

### Aanbevolen: domein verifiëren

Zo kan niemand anders uw domein aan een eigen GitHub-site koppelen.

1. Klik op GitHub rechtsboven op uw profielfoto, dan op **Settings** en daarna links op **Pages**.
2. Klik op **Add a domain** en vul `seniorenactiefzaltbommel.nl` in.
3. GitHub geeft een TXT-record (de naam begint met `_github-pages-challenge-`). Zet dat record bij de registrar en klik daarna op **Verify**.

### Controleren

- https://www.seniorenactiefzaltbommel.nl opent de homepage, met een slotje in de adresbalk.
- https://seniorenactiefzaltbommel.nl (zonder www) stuurt door naar het adres met www.
- Een adres dat niet bestaat, zoals `/test`, toont de pagina "Deze pagina bestaat niet".

## Na de livegang

1. **Google Bedrijfsprofiel** aanmaken op https://business.google.com. Gebruik precies dezelfde naam, hetzelfde adres en hetzelfde telefoonnummer als in de voettekst van de site, en vul de lestijden in als openingstijden.
2. **Google Search Console** (https://search.google.com/search-console): voeg het domein toe, bevestig het met een TXT-record bij de registrar en dien de sitemap in: `https://www.seniorenactiefzaltbommel.nl/sitemap.xml`.
3. **Snelheid en toegankelijkheid testen** met https://pagespeed.web.dev.
4. **Vermeldingen vragen** bij het sportaanbod van de gemeente Zaltbommel en bij de lokale welzijnsorganisatie, met een link naar de site.
5. **De link delen:** op de Facebookpagina 50+Actief en op de flyer.

## Lokaal bekijken

Met Python geïnstalleerd: open een terminal in deze map en typ `python -m http.server 8000`. Ga dan in de browser naar http://localhost:8000.
