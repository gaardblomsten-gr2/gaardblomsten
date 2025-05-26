# Teknisk dokumentation for Tema 10 eksamen gruppeprojekt, gruppe 2

Når man er flere der bidrager til en kodebase, lærer man hurtigt, at ens sædvanlige måder at gøre tingene på ikke nødvendigvis er logisk for alle.

Skriv derfor jeres fælles retningslinjer for punkterne herunder(tilføj gerne flere selv), sådan som det giver bedst mening for jer som gruppe. Dokumentationen sikre, at jeres fælles kodebase forbliver overskuelig, er let at arbejde med og til at forstå for alle, og at I undgå konflikter, og har nemmere ved at hjælpe hinanden undervejs.

## Projektstruktur:

Beslut, hvordan I vil organisere jeres projekt – struktur for mapper og filer.

- Hvordan organiserer I billeder, fonte og andre ressourcer?
  Vi opretter og navngiver mapper efter indholdet. Fx. “img”-mappe, som indeholder vores billeder. Stylemappen kalder vi “style”, som indeholder layout.css og style.css under src-mappen.

- Hvor placerer I boilerplate?(fx CSS- og JavaScript-filer, der bruges på tværs af projektet)
  Vores generelle layout kan findes i vores fil “Layout.astro" under src. Derudover har vi style i hver enkel page og hver enkelt komponent. Det samme gælder vores Javascript, som også er placeret inde i selve pagen eller komponenten.

## Navngivning:

Beslut hvordan i vil navngive filer og mapper for at sikre en ensartet struktur og undgå forvirring.

- Hvordan navngiver I filnavne? (fx små bogstaver, ingen mellemrum, brug af - eller _)
  Vi navngiver med små bogstaver og benytter navngivning fra vores layoutdiagram. Vi bruger underscore (_) som erstatning for mellemrum, men benytter bindestreg (-) til at understrge at noget høre sammen.
- Hvordan sikre I at det er til at forstå hvilke HTML-, CSS- og JavaScript-filer der høre sammen?
  Vi har taget en fælles beslutning om at vi koder i Astro, så der styles i gældende filer, og der vil derfor ikke blive brug for at oprettet CSS-filer til HTML-filer.

## Git branches:

- Hvordan navngiver I branches, så alle kan forstår hvem der arbejder i branchen og på hvad? (fx feature-lotte-formular)
  Vi navngiver branches på følgende måde: navn_header, fx cathrine_header.

## Arbejdsflow:

- Hvordan fordeler I arbejdet, så I undgår at flere arbejder i de samme filer samtidigt?
  I alt har vi 4 pages der skal kodes. I starten af kodningsprocessen fordeler vi hvilke sider vi hver især skal kode, og fordeler komponenter mellem os. Den fjerde page, som er workshop, hvor vi arbejder med API via Supabase, udvikler vi sammen, så alle er med indover hvad der sker.
- Hvordan sikrer I, at commit-beskeder er beskrivende?
  Vi navngiver commit-beskeder på følgende måde:
  add/fix/delete/, fx add_images
- Hvordan kommunikerer i om ændringer i main branchen når feature merges?
  Vi sørger for at vi sidder fysisk sammen, når der merges og trykker pull fra main en ad gangen, så vi er sikre på alles kode bliver opdateret korrekt.

## Kode:

- Skal filer have korte forklaringer som kommentarer?
  Vi har forsøgt at sørge for, at alt ny kode, som kan være svært at huske i hovedet, er kommenteret, så alle i gruppen nemt kan læse hvad der bliver gjort i koden.

# Funktionalitet

Dette afsnit skal forklare hvad I konkret har arbejde med, for at udvikle websitet. Tænk over hvilke interaktioner brugeren kan foretage på sitet? Eller hvordan websitet håndterer og præsenterer data? Eksempler på funktionalitet, der kan beskrives:

- Hentning af produkter fra API.
- Filtrering af produkter baseret på brugerens valg.
- Dynamisk visning af produkter i HTML.

Brug korte beskrivelser, som i eksemplerne herover.

- Hentning af workshop fra API, Supabase.
- Ændring af dato og tid, ved hjælp af formatDate og formatTimeRange.
- Ændring af stort startbogstav ved hjælp af capitalizeFirstLetter.
- Arrow function kode.

# API endpoints

Dette afsnit skal liste de endpoints fra API'et i har benyttet:
https://supabase.com/dashboard/project/zzemvifmqicszywpsymv/editor/17250

# Dokumentation af Funktion

Dette afsnit skal beskrive en funktion I selv har udviklet. Det kunne eksempelvis være en funktion der generere en liste over fx. produkter:

Nedenunder ses en funktion vi selv har udviklet, for vores workshop side, hvor vi har flere events og til hvert af dem en knap, der kan trykkes på, så man kan læse mere og sektionen foldes ud.

<script>
  document.addEventListener("DOMContentLoaded", () => {
    // betyder: når sidens indhold er loadet, så starter koden
    const toggleBoxes = document.querySelectorAll(".laes-mere");
    // betyder: 'querySelectorAll' betyder den vælger alle med classen '.laes-mere', ikke kun den første

toggleBoxes.forEach((box) => {
      const label = box.querySelector("label");
      const content = box.querySelector(".content");
      // betyder: inde i boxen finder vi 'label' og 'content'

content.classList.add("usynlig"); // denne linje sørger for at indholdet er skjult ved sideindlæsning fra starten

label.addEventListener("click", () => {
        // betyder: når man klikker på label altså "læs mere/læs mindre"
        content.classList.toggle("usynlig");
        // betyder: fjerner eller tilføjer klassen "usynlig" så teksten vises eller ej

// opdater teksten på label fra læs mere til læs mindre
        label.textContent = content.classList.contains("usynlig")
          ? "Læs mere"
          : "Læs mindre";
        // betyder: dette gør at teksten ændrer sig fra læs mere og læs mindre
      });
    });
  });
</script>
