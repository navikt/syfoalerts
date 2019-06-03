# syfoalerts

Lager alerts for team barken sine syfo-apper

For mer informasjon om hvordan alarmene fungere se:
`https://github.com/nais/doc/tree/master/content/alerts`

### For NAV ansatte
Vi er tilgjenngelig på slack kanalen #barken

## Utvikling:
En kan bruke `https://prometheus.nais.preprod.local/graph` som hjelp til å teste queries. Bruk `test/syfoalert_test.yaml` til å teste alerteren i dev. Varsel dukker da opp i `syfo-alerts-dev` på Slack

### Deploy test:
Deploy alerten din til riktig cluster i preprod:
`kubectl apply -f test/syfoalert_test.yaml`

Om alerten allerede finnes må den fjernes først:
`kubectl delete alert syfoalerts-test`

### Deploy prod:
Bruk byggjobb:
`https://jenkins-digisyfo.adeo.no/job/syfoalerts/`
