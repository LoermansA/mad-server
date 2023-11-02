# Inleiding

Dit document beschrijft de minimale stappen die nodig zijn om het back-end deel woor de course "Mobile Application Development" draaiend te krijgen.

## Algemene aantekeningen voor de student

De backend kan te allen tijden opnieuw gegenereerd worden op basis van de `application.jdl` en de `model.jdl`. Onderstaande gaat ervan uit dat jhipster is geïnstalleerd ([JHipster installatie](https://www.jhipster.tech/installation/)). In dit voorbeeld wordt gebruik gemaakt van een lokaal (projectdomein) installatie en wordt `npx` gebruikt om de generator aan te roepen. De student kan zelf bepalen hoe hij/zij JHipster geïnstalleerd wil hebben.

Installeer jhipster (in dit voorbeeld lokaal). Navigeer naar je lege projectmap en typ:

    `npm install generator/generator-jhipster`

LET OP! In versie 8.0.0-rc.1 zit een bug die foutieve schermen genereert. Gebruik (indien nog geen nieuwe release is geweest) de `main` versie:

    `npm install jhipster/generator-jhipster#main`

- Genereer vervolgens de applicatie zelf:

```bash
npx jhipster jdl application.jdl
```

- Daarna genereerd je het model en alle verwante (al gegenereerde) objecten.

```bash
npx jhipster jdl model.jdl
```

- Vervang de gegenereerde seed data met de data uit de zip. Copieer de .csv bestanden uit de zip naar `src/main/resources/config/liquibase/fake-data/`

Nu kan je de applicatie starten:

```
./mvnw
```

Om met een https verbinding te werken kan je de applicatie achter een ngrok tunnel laten draaien. Bovenstaand commando start de server in development mode, luisterend op poort 8080. [Installeer ngrok](https://ngrok.com/docs/getting-started/) en start de tunnel:

```bash
ngrok http 8080
```