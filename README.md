[![Build status](https://github.com/navikt/syfoalerts/workflows/Deploy%20to%20dev%20and%20prod/badge.svg)](https://github.com/navikt/syfoalerts/workflows/Deploy%20to%20dev%20and%20prod/badge.svg)

# syfoalerts

Lager alerts for team barken sine syfo-apper

For mer informasjon om hvordan alarmene fungere se:
`https://github.com/nais/doc/tree/master/content/alerts`

## Utvikling:
En kan bruke `https://prometheus.nais.preprod.local/graph` som hjelp til å teste queries.

## Varsler slack
Varslene dukker opp i slack kanlene som er definert opp i yaml filene
pr nå er disse:
Prod: #syfo-alerts-prod
Dev: #syfo-alerts-dev

## Deploy til dev:
Alle kode som ikkje er i master går til dev-fss
Dette kan evt gjøres manuelt med følgende kommando:
`kubectl apply --context dev-fss --namespace default -f sykmeldingalerts.yaml`

### Deploy prod:
Alle kode som er i master går til prod-fss og prod-sbs
Dette kan evt gjøres manuelt med følgende kommandoer:
`kubectl apply --context prod-fss --namespace default -f sykmeldingalerts.yaml`
`kubectl apply --context prod-sbs --namespace default -f sykmeldingalerts-sbs.yaml`

### For NAV ansatte
Vi er tilgjenngelig på slack kanalen #team-sykmelding