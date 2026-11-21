# agents/

En mapp per agent, med samma namn som agentens id:

```
agents/<id>/
├── kontrakt.yaml     agentkontraktet (schema i agent-plattform)
├── granskning.md     säkerhetsgranskningen
├── evals/            facit och injektionsfall
└── ...               eventuell kod
```

Skapa kontraktet med skillen `agent-kontrakt` och lägg till agenten i `agentregister.yaml`. Inga hemligheter här; nycklarnas namn och omfång står i kontraktet, deras värden i Claude eller i GitHubs hemligheter.
