# Teknisk dokumentation for Tema 7 gruppeprojekt

Når man er flere der bidrager til en kodebase, lærer man hurtigt, at ens sædvanlige måder at gøre tingene på ikke nødvendigvis er logisk for alle.

Skriv derfor jeres fælles retningslinjer for punkterne herunder(tilføj gerne flere selv), sådan som det giver bedst mening for jer som gruppe. Dokumentationen sikre, at jeres fælles kodebase forbliver overskuelig, er let at arbejde med og til at forstå for alle, og at I undgå konflikter, og har nemmere ved at hjælpe hinanden undervejs.

## Projektstruktur

Vi har organiseret vores projekt i forskellige mapper for at holde filer og ressourcer struktureret og nemme at finde.

### Organisering af ressourcer

For at holde vores billeder samlet et sted har vi oprettet en mappe til dem, som liiger i public.

- **img/** – indeholder alle billeder, der bruges på hjemmesiden (fx produktbilleder og grafik).

Det gør det nemmere for os at finde rundt i de billeder vi skal bruge til vores hjemmeside.

## Hvor placerer I boilerplate?

_(fx CSS- og JavaScript-filer der bruges på tværs af projektet)_

Vi laver en fælles mappe til styles, som bruges på alle sider i projektet. Denne mappe kalder vi **global CSS**, og her placerer vi vores fælles styling som fx typografi, farver og generelle layoutregler.

Derudover lavede vi 3 JavaScript-filer, som håndterer forskellige funktioner på siden:

- **burger.js** – håndterer vores navigation i top baren

Vi opretter også separate **HTML-filer for hver side**, så strukturen på hjemmesiden er overskuelig og nem at vedligeholde.

---

## Opdeling

Vi kommer til at skrive her, hvem der koder hvad:

### Komponenter:

Card.astro - Josefine
Footer.astro - Laila
Navigationbar.astro - Denzel
CTA - Josefine

### pages:

Forsiden - Laila
Artist - Josefine
ArtisterProgram - Laila
Frivillige -Denzel
OmOs - Denzel

## Database struktur

vi kommer til at bruge superbase til at holde styr på vores data. det er josefine som styrer vores superbase.

## Hvor placerer I HTML, CSS og JavaScript til fx detaljevisning og listevisning?

vi kommer til at dele det op i forskellige folders så vi kan holde styr på hvor vores filer ligger.

---

## Eksempel på mappestruktur

/project
│ └── global.css
│ ├── produkt.js
│ ├── produktliste.js
│ └── burger.js
│
├── /images
│
├── index.html
├── produkt.html
└── produktliste.html

## Navngivning

For at sikre en ensartet struktur og undgå forvirring i projektet har vi aftalt nogle regler for, hvordan vi navngiver filer og mapper.

### Filnavne

Til navngivning bruger vi en kombination af **camelCase**.

### Sammenhæng mellem filer

For at gøre det nemt at se hvilke HTML-, CSS- og JavaScript-filer der hører sammen, bruger vi **samme navn eller prefix**.

---

### Placering af script-referencer

Vores script-referencer placeres i **`<head>`** i vores HTML-sider, hvor vi bruger **`defer` attributten**.  
Det sikrer, at JavaScript først bliver kørt efter HTML'en er indlæst.

---

## Git branches

vi sikre os at vi altid laver nye brances så vi ikke arbejder i main

### Navngivning af branches

vi laver branches navne så det passer med det vi arbejder i.
**Format:**

**Eksempler:**

- `menuForside`
- `footerOpdatering`

Denne struktur gør det lettere for alle i gruppen at forstå, hvad der arbejdes på i de forskellige branches.

---

### Fordeling af arbejde

For at undgå at flere arbejder i de samme filer samtidigt, tildeler vi **en side til hver person i gruppen**.  
Den person har ansvar for funktioner og kode, der hører til den pågældende side.

### Kommunikation om ændringer i main

Når en **feature-branch merges ind i `main`**, kommunikerer vi ændringen i **gruppechatten**, så alle er opmærksomme på opdateringen.

Vi forsøger også så vidt muligt kun at **merge til `main`, når vi er samlet**, så vi kan undgå konflikter og fejl.

## Kode:

- Hvordan skriver i funktioner i JavaScript?(fx med function keyword eller som arrow functions)

vi har brugt begge dele i vores projekt. Vi bruger function keyword til større navngivne funktioner, mens vi bruger arrow funktioner til de kortere funktioner ind i eventlistners og .forEach()

- Beslut hvilken CSS selector i benyttes til referener i henholdsvis CSS og JavaScript(fx. id'er til JavaScript og Classes til CSS)

i vores projekt har vi ikke haft så strame regler i forhold til selektore, også fordi vi ikke har været så mange i gruppen og projektet har ikke været så stort at det har været uoverskueligt at skulle gå ind og finde selektorene for diverse id'er til javascript og classes til css.

# Funktionalitet

Vi henter først et “id” fra URL’en og bruger det til at hente data fra Supabase, som derefter vises på siden. Produkterne vises dynamisk ved hjælp af funktionen showProducts, hvor vi gennemløber data med .forEach() og opbygger HTML med template literals. Her vises bl.a. titel, pris, billede og badges.

Derudover har vi lavet dynamisk filtrering af produkter baseret på brugerens valg. I stedet for faste (hardcodede) filterknapper genereres de automatisk med funktionen buildFilterButtons. Den opretter en knap for hver unik kategori i dataen fra Supabase, hvilket gør, at filtrene automatisk tilpasser sig indholdet på siden.
