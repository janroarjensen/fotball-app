# Lagleder – mobil kampapp (Firebase)

Dette er en mobiloptimalisert HTML-prototype for lagleder/trener i barnefotball.

## Filer
- `lagleder_mobile_firebase.html` – hovedappen (single-file HTML)
- `firebase-rtdb-rules.json` – eksempel på Realtime Database-regler

## Viktige funksjoner
- Firebase Authentication (e-post/passord)
- Firebase Realtime Database
- Lagoppsett: laginfo og spillere
- Kampstyring: start/pause/2. omgang/slutt
- Hendelser: mål, mål imot, bytte, notater, assist, redning, stor sjanse
- Sesongstatistikk: minutter, kamper, mål, assist og bidragsscore
- Lokal AI-lignende kamprapport basert på kampdata
- CSV-eksport og utskrift

## Datamodell (enkelt forslag)
- `/users/{uid}`
  - `name`
  - `email`
  - `phone`
  - `teamId`
- `/teams/{teamId}/info`
- `/teams/{teamId}/players/{playerId}`
- `/teams/{teamId}/matches/{matchId}`

## Oppsett
1. Opprett Firebase-prosjekt.
2. Aktiver Authentication > Email/Password.
3. Opprett Realtime Database.
4. Legg inn reglene fra `firebase-rtdb-rules.json`.
5. Åpne HTML-filen og lim inn Firebase-config under **Innstillinger**.
6. Registrer trener/lagleder.
7. Legg inn `/users/{uid}/teamId` manuelt, eller sett dette automatisk via adminverktøy senere.
8. Legg inn lag/spillere i appen.

## Viktig om «AI-generert rapport»
I denne front-end-prototypen lages rapporten lokalt i klienten. Det gir en automatisk oppsummering i «AI-stil», men ikke ekte generativ AI.

Hvis du vil ha ekte AI senere bør dette gjøres via en sikker backend, f.eks:
- Firebase Cloud Functions
- Azure Functions
- Egen API-løsning

Da kan appen sende kampdata til backend og få tilbake en ekte tekstgenerert rapport uten å eksponere hemmelige nøkler i HTML/JS.
