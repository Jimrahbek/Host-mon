# Teknisk dokumentation for Tema 9 gruppeprojekt

Dette projekt er lavet som en del af tema 9. Vi har lavet en hjemmeside,
der fokusere på at vise informationer om festivallen Høst Møn

## Links

- GitHub repository: [https://github.com/Jimrahbek/Host-mon.git]
- GitHub Pages: [host-g12.netlify.app]
- Figma: [https://www.figma.com/design/NfIPM8JyvaJCm1jx5XiCIL/T9-H%C3%B8st-M%C3%B8nt?node-id=382-293&p=f&m=dev]

## Projektstruktur

```text
/
├── public/
    └──billeder/
├── src/
│   └── pages/
        └── arkiv.astro
        └── festivalOversigt.astro
│       └── index.astro
        └── købsoversigt.astro
        └── kunstner.astro
        └── kunstnerliste.astro
        └── måltid.astro
        └── omHøstMøn.astro
└── .env
└── .gitignore
└── astro.config.mjs
└── package-lock.json
└── package.json
└── README.md
└── tsconfig.json

```

Astro søger efter `.astro`- eller `.md`-filer i `src/pages/`-mappen. Hver side vises som en rute baseret på dens filnavn.

Der er ikke noget særligt ved `src/components/`, men det er der, vi gerne placerer alle Astro komponenter.

Alle statiske aktiver, som f.eks. billeder, kan placeres i `public/`-mappen.

## Navngivning:

For at sikre en ensartet struktur og for at undgå forviring vil vi følge disse regler

- **Små bogstaver** - Alle mapper og filer navngives med små bogstaver
- **Ingen mellemrum** - Vi undgår mellemrum i filnavne, da det kan skabe problemer i kodning.
- **Store bogstaver** - vi bruger store bogstaver til at adskille ord som f.eks. festivalOversigt.

## Git branches:

Vi aftaller hvem arbejder på hvilke sider og pusher kun ting ind i main når vi sidder sammen. Branches bliver navngivet efter hvad der bliver lavet i dem for at skabe et bedre overskud.

## Arbejdsflow:

For at arbejde effektivt i gruppen og undgå konflikter i koden følger vi nogle fælles regler for vores arbejdsproces.

**Fordeling af arbejde**

Vi fordeler arbejdet ved at give hvert gruppemedlem ansvar for bestemte sider eller funktioner på hjemmesiden. På den måde arbejder vi som regel i forskellige filer og undgår, at flere redigerer i de samme filer på samme tid. Hvis to personer skal arbejde på samme funktion, aftaler vi det først i gruppen.

**Commit-beskeder**

For at sikre tydelige commit-beskeder skriver vi korte og præcise beskrivelser af, hvad der er blevet ændret. En commit-besked skal fx forklare hvilken fil eller funktion der er blevet ændret, og hvorfor.

**Kommunikation om ændringer i main**

Når en feature branch bliver merged til **main**, informerer vi resten af gruppen via vores fælles kommunikationskanal som enten er Messenger, Teams eller når vi mødes på skolen. På den måde ved alle, at der er kommet nye ændringer, og de kan opdatere deres lokale version af projektet, før de fortsætter arbejdet.

## Kode:

**Håndtering af data**

En vigtig del af vores kode er arbejdet med data. Vi har lavet vores egen database i supabase. Denne database har vi derefter hentede data fra som bruges til musiker siderne. Dette gør det simpelt at lave mange ensartet sider uden at skulle skrive den samme kode igen og igen.

**Css selectors**

Vi har valgt at bruge classes som selectors både i HTML og JavaScript. Det giver en fleksibel løsning, hvor flere elementer kan dele samme styling og funktionalitet.

**Kommentarer i koden**

Kommentarer i koden er brugt der, hvor det passer bedst for eksempel ved fetch-kald, funktioner og mere komplekse dele af CSS som layout eller responsive regler. Vi har valgt at ikke kommentere helt åbenlyse koder, så koden stadig fremstår ren og overskuelig, men samtidig nem at forstå for andre.

Her er et eksempel på hvordan kommentarer i koden hjælper med at skabe overblik ved at forklarer kort hvad koden handler om.

## Commands

Alle kommandoer køres fra fra en terminal:

| Command         | Action                                        |
| :-------------- | :-------------------------------------------- |
| `npm install`   | Installerer afhængigheder                     |
| `npm run dev`   | Starter lokal udviklerserver `localhost:4321` |
| `npm run build` | Byg dit produktionssted til`./dist/`          |

### api

for at få vores data har vi hentet det fra vores egen database. Dette er gjort via denne kode

```
{data.map((artister) => <Artister artister={artister} />)}
```
