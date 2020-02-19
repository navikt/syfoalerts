[![Build status](https://github.com/navikt/syfoalerts/workflows/Deploy%20to%20dev%20and%20prod/badge.svg)](https://github.com/navikt/syfoalerts/workflows/Deploy%20to%20dev%20and%20prod/badge.svg)

# syfoalerts

Lager alerts for team barken sine syfo-apper

For mer informasjon om hvordan alarmene fungere se:
`https://github.com/nais/doc/tree/master/content/alerts`

## Utvikling:
En kan bruke `https://prometheus.nais.preprod.local/graph` som hjelp til å teste queries.

### Deploy prod:
Alle kode som er i master går til prod-fss
Dette kan evt gjøres manuelt med følgende kommando:
`kubectl apply --context prod-fss --namespace default -f sykmeldingalerts.yaml`

### For NAV ansatte
Vi er tilgjenngelig på slack kanalen #team-sykmelding