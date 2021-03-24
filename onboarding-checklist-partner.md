# Hvordan kan du som Vipps Partner veilede dine kunder til å ta i bruk Vipps På Nett

**Hvert brukersted må ha en avtale direkte med VIPPS AS.**

### 1 - Om brukerstedet har ikke Vipps på Nett-avtale:

* Kunde/Partner går inn her https://vipps.no/signup/vippspanett/ og velger Integrasjon via leverandør
* Velger [Partner] som partner i nedtrekksmenyen med tilhørende pris
* Fyller ut skjema
* Sender avtalen på side 3 til signering fra person med signaturrett i selskapet. Signaturkontroll blir gjort mot opplysninger i Brønnøysundregistrene.
  * *Dersom flere personer i selskapet har signaturrett i fellesskap (f.eks. styreleder og ett styremedlem i fellesskap), er det personen høyest opp i hierarkiet som må signere. Det er ikke mulig at flere signerer avtalen*
* Søknaden om Vipps på Nett går nå til kontroll/gjennomgang (KYC og AML) hos brukerstedsservice.

**Det kan skje at søknader stopper opp, så det kan være greit å ha kontroll på hva som eventuelt kan forårsake dette:**

* Avtalen er signert av feil person i selskapet
* Salgsvilkår er ikke tilgjengelig på nettsiden eller er mangelfull. Vi anbefaler å bruke Forbrukertilsynets standard salgsbetingelser for netthandel:
https://www.forbrukertilsynet.no/lov-og-rett/veiledninger-og-retningslinjer/standard-salgsbetingelser-for-forbrukerkjop-av-varer-over-internett
* Organisasjonsnummeret ligger ikke godt nok synlig på nettsiden. Dette bør f.eks. ligge nederst på forsiden
* Merk at dersom søknaden har stoppet opp og vår bestillingsavdeling mangler informasjon, vil de sende mail til avtalens kontaktperson. Det er viktig at Partners kunder er oppmerksomme på at de kan få mail fra Vipps

Søknaden godkjennes når alt er på plass, og salgsenhet legges opp

* Gitt at Partner bruker supermerchant-nøkler, blir Merchant Serial Number (MSN) for salgsstedet sendt på epost til Partner (fra partnerbestilling@vipps.no).
  * Uten bruk av supermerchant-nøkler: API-nøkler sendes enten via callback (krever integrasjon av Signup API), alternativt hentes nøkler ut av kunden sin administrator fra https://portal.vipps.no.
* Partner fullfører integrasjonen for kunden

### 2-	Om Brukerstedet har en Vipps på nett avtale:
* Kunde trenger ikke søke om ny Vipps på Nett avtale
* Kunde / Partner gir beskjed til partnerbestilling@vipps.no om at et nytt salgssted skal opprettes på kunde [org.nr]. Salgsenheten tagges på Partner som partner. Partnerbestilling oppretter salgsenheten og sender MSN til Partner (evt. API nøkler)

**Hvordan sette opp nytt salgssted under en eksisterende avtale:**

* Kunde/Partner gir beskjed til partnerbestilling@vipps.no om at et nytt salgssted skal opprettes på kunde [org.nr.]. Partnerbestilling oppretter salgsenheten og sender MSN til Partner (eventuelt API-nøkler).
* Dersom kunde ønsker et nytt salgssted som er ulikt det eksisterende (f.eks. annen nettside, en annen bransje e.l), gir kunde/Partner beskjed til deres partneransvarlig i Vipps. Dette er ikke noe dere må ta hensyn til i første omgang, men dersom slike caser dukker opp vil de bli behandlet enkeltvis. Kunde må forøvrig ikke signere noen ny avtale.

### Spørsmål Vipps trenger svar på når et brukersted ønsker nytt salgssted som er ulikt det eksisterende:
* Tar dere imot betalinger på forhånd og går det mer enn 5 dager fra bestilling til levering? Hvis ja, hvor stor andel av deres totalomsetning betales på forhånd og mange dager det vanligvis fra bestilling til levering.
* Selger dere gavekort og forventer dere at mer enn 10 % av deres omsetning knyttet til gavekort? Hvis ja, hvor stor andel av deres totalomsetning er knyttet til salg av gavekort og hvor lenge er gavekortene deres gyldig.
* Tilbyr dere abonnementsløsninger og betaler kunden for abonnementsperioden på forhånd? Hvis ja, hvor lenge varer en gjennomsnittlig abonnementsperiode?
