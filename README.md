# House of Waves — website (ontwerp)

Statische website (HTML/CSS/JS), geen build-stap nodig. Gemaakt als ontwerp voor houseofwaves.nl.

## Bestanden
- `index.html` — homepage (hero met bewegende aura, journal essentials, "trek een kaart", ritueel, waves-tijdlijn, verhaal, reviews-carousel, nieuwsbrief)
- `shop.html` — alle producten, filter per collectie via `?c=journal-essentials | waves-of-balance | waves-of-creation | waves-of-energy | nieuwe-collectie`, sorteren op prijs
- `product.html?p=<handle>` — één productsjabloon voor alle producten (galerij, maten, aantal, beschrijving, gerelateerd)
- `waves.html` — tijdlijn van alle collecties
- `verhaal.html` — ons verhaal
- `winkelwagen.html` — winkelwagenpagina
- `contact.html` — contactformulier, FAQ, verzending & retour
- `style.css` — alle opmaak (kleuren/fonts als CSS-variabelen bovenin)
- `app.js` — winkelwagen (localStorage), zijpaneel, productkaarten, scroll-animaties, mobiel menu
- `data.js` — productdata (titels, prijzen, Shopify-variant-ID's, beschrijvingen, foto's, collecties), afkomstig uit houseofwaves.nl/products.json
- `logo.svg` — logo als vector (kleur via `currentColor`)
- `img/` — sfeerfoto's; `img/p/` — productfoto's (van de huidige webshop)

## Online zetten
1. Upload de hele map naar een willekeurige statische host (Netlify, Vercel, GitHub Pages, eigen server). Alle links zijn relatief, dus de map mag in de root of in een submap.
2. De pagina's staan nu op `noindex` (`<meta name="robots" content="noindex, nofollow, noarchive">` in elke HTML-kop). Haal die regel weg zodra de site echt live moet en gevonden mag worden.
3. Lettertypes laden via Google Fonts (Gloock, Figtree, Nanum Pen Script).

## Wat is echt en wat is nog ontwerp
- **Afrekenen werkt echt:** de knop "afrekenen" stuurt naar `https://houseofwaves.nl/cart/<variantID>:<aantal>,...` en opent de echte Shopify-checkout met de gekozen producten.
- **Winkelwagen** wordt alleen in de browser van de bezoeker bewaard (localStorage).
- **Nieuwsbrief- en contactformulier versturen niets** (alleen een melding). Koppel ze aan Shopify (customer/newsletter form), Klaviyo, Formspree of Netlify Forms.
- **Placeholders om in te vullen:** levertijd en retourbeleid in de FAQ (`contact.html`, staan tussen [blokhaken]).
- **De vragen bij "trek een kaart"** (`index.html`, array `Q` in het script) zijn voorbeelden; vervang ze door echte vragen uit het Balance kaartendeck.
- **"Bekend van"-balk** gebruikt tekst, geen officiële logo's.
- Controleer de betaalmethoden in `winkelwagen.html` (iDEAL toegevoegd als aanname).

## Shopify-thema
Wil je dit als Shopify-thema: neem `style.css` als basis, zet de secties om naar Liquid-secties en vervang `data.js` door Shopify's eigen productobjecten. De winkelwagen kan dan via de Shopify AJAX Cart API (`/cart/add.js`) in plaats van localStorage.

## Instructie voor een AI-assistent
"Dit is een kant-en-klare statische website voor House of Waves. Zet de map ongewijzigd online op mijn host, behoud de mapstructuur en relatieve paden. Verwijder de noindex-regels alleen als ik zeg dat de site live mag. Koppel de nieuwsbrief- en contactformulieren aan [mijn dienst]."
