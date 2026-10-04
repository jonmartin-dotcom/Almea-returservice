# Almea – Returservice

Enkel returportal for kunder av Almea, bygget på Next.js. Kunden slår opp
ordrenummeret sitt, velger hvilke varer som skal returneres, fyller ut
kontaktinfo, og får en returetikett generert automatisk via Webshipper.
Returen registreres samtidig i Ongoing WMS slik at lageret ser den komme.

## Oppsett

1. `npm install`
2. Kopier `.env.example` til `.env.local` og fyll ut verdiene (se under)
3. `npm run dev`

## Miljøvariabler

Se `.env.example` for full liste. Viktigst:

- `ONGOING_GOODS_OWNER_ID=89` (Almea sin vareeier-ID i Ongoing)
- `ONGOING_USERNAME` / `ONGOING_PASSWORD` – API-bruker for "Goods Owner
  Returns REST API" (må skrus på i Ongoing-admin for goodsOwnerId 89)
- `WEBSHIPPER_ACCESS_TOKEN` / `WEBSHIPPER_CARRIER_ID` / `WEBSHIPPER_SERVICE_CODE`
- `WAREHOUSE_RETURN_*` – adressen varene skal returneres til (samme lager som
  for øvrige vareeiere)

## Driftsnotat

Denne løsningen er en egen kopi av løsningen bygget for Vitae Vital (som i
sin tur er en kopi av Nesco-løsningen), tilpasset Almea. Se prosjektet
"Returløsning - Ongoing kunder" i Claude for felles arkitekturbeslutninger,
kjente fallgruver, og en oversikt over alle vareeiere.

## Deploy

Deploy via Vercel. Husk å sette "Framework Preset" til "Next.js" manuelt
hvis det ikke blir satt automatisk.
