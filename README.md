# Framtid – digitalt produktionsstöd

En webbaserad prototyp för monteringsinstruktioner, ERP-materialstatus och avvikelsehantering.

## Demo-inloggning

- `9829` – montör
- `1357` – administratör
- `1202` – administratör

Andra numeriska anställningsnummer kan logga in som montör i prototypen.

## Testdata

Sök eller skanna någon av följande koder:

- `WO-2026-1042` eller `LE-1001` – L-element
- `WO-2026-1088` eller `HE-2002` – Hörnelement

En QR-kod eller streckkod på arbetsordern kan alltså innehålla arbetsordernumret eller artikelnumret. När kameran läser värdet matchas det mot rätt instruktion.

## Funktioner

### Montör
- Inloggning med anställningsnummer.
- Svenska/engelska. Senast valda språk sparas lokalt.
- Ljust/mörkt läge. Senast valda läge sparas lokalt.
- Sökning på artikelnummer, namn eller arbetsorder.
- Kamera för QR-kod och streckkod när webbläsaren stöder BarcodeDetector.
- Materiallista från simulerad ERP-källa med behov, lagersaldo och röd markering vid brist.
- Röd säkerhetsruta som måste kvitteras med samma anställningsnummer som är inloggat.
- Start/stopp av monteringstid och måltid.
- Stegvisa instruktioner med text, bildyta, framåt/bakåt, videomarkering och webbläsarens talsyntes.
- Orange information om aktiva avvikelser på vald instruktion.
- Rapportering av ny avvikelse med maskin/arbetsstation, prioritet och beskrivning.

### Administratör
- Behörighetsstyrd adminvy.
- Översikt med antal öppna/avslutade avvikelser, högprioriterade avvikelser och instruktioner.
- Lista med aktiva avvikelser och prioritet.
- Kvittering/avslut av avvikelse kräver åtgärd eller plan samt administratörens anställningsnummer.
- Historik och statistik per instruktion.
- Redigering av befintliga instruktioner.
- Skapa nya instruktioner.

## Viktigt om prototypen

ERP, pushnotiser och företagsautentisering är simulerade integrationspunkter. I en skarp version bör systemet ha en backend och databas samt kopplas till företagets riktiga ERP-API, identitets-/behörighetssystem och notistjänst. Produktionsdata bör inte lagras enbart i `localStorage`.

För riktig ERP-integration bör arbetsordern vara nyckeln. Systemet skickar arbetsordernumret till ERP och får tillbaka artikel, operationsdata, materialbehov, aktuellt lager/reservationer och eventuellt planerad tid. Instruktionssystemet använder sedan artikel/operation/revision för att öppna korrekt instruktion.

## GitHub Pages

`index.html` ligger i repositoryts rot och är byggd för statisk publicering. Aktivera GitHub Pages för `main` / root i repositoryts Pages-inställningar. Därefter kan sidan användas från mobil, surfplatta eller dator. Kamera kräver normalt HTTPS, vilket GitHub Pages ger.
