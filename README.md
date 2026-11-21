# agenter-privat

Tommys privata agenter: kontrakt, säkerhetsgranskningar, evals och eventuell kod. Konventionerna och verktygen finns i [agent-plattform](https://github.com/tommysoder79-maker/agent-plattform).

```
agentregister.yaml    alla agenter i sfären, med status
agents/<id>/          en mapp per agent
```

Inga agenter är registrerade ännu. Den första blir Yahoo-rensningen, i två delar (se exemplen i `agent-plattform/schema/exempel/`).

## Läsnyckel för CI

CI validerar registret och kontrakten med skripten i `agent-plattform`. Eftersom det repot är privat behöver CI en läsnyckel:

1. GitHub → Settings → Developer settings → Fine-grained personal access tokens → Generate new token.
2. Repository access: bara `tommysoder79-maker/agent-plattform`. Permissions: Contents, Read-only. Sätt ett utgångsdatum.
3. I det här repot: Settings → Secrets and variables → Actions → New repository secret, med namnet `AGENT_PLATTFORM_LASA`.

Utan nyckeln går CI igenom med en varning, men validerar ingenting.
