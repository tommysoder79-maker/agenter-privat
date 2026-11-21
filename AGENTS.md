# Arbeta i agenter-privat

- Det här är sfären **privat**. Varje agent här har `sfar: privat` i sitt kontrakt. Föreningens och Complexity Insights agenter hör inte hit.
- Konventionerna, schemat och validerarna finns i `tommysoder79-maker/agent-plattform`. Läs dess `docs/arkitektur.md` innan du bygger eller ändrar en agent.
- **Datagrinden:** ingen information från Tommys arbete och inget säkerhetsskyddsklassificerat förs in här, inte heller i testfall eller loggar.
- En agent har en mapp `agents/<id>/` med `kontrakt.yaml`, `granskning.md` och `evals/`, och en rad i `agentregister.yaml`. Skapa kontraktet med skillen `agent-kontrakt`; skriv inte risknivån för hand utan låt `scripts/risk.py` räkna den.
- Nivå 3 (opålitlig indata, känslig data och ändring utan godkännande i samma session) godtas inte. Dela upp flödet.
- En ny agent börjar i läget `av` eller `skugga`. Den går till `automatiskt` först när befordran är dokumenterad i kontraktet.
- Inga hemligheter i repot. Nycklarnas namn och omfång står i kontraktet. En avvecklad agent står kvar i registret med `nycklar_aterkallade: true`.
- Ändringar görs i en gren och som pull request. Tommy slår ihop.

Validera lokalt, med agent-plattform utcheckad bredvid:

```
python ../agent-plattform/scripts/validera_kontrakt.py --register agentregister.yaml \
  --kallregister ../agent-plattform/kallregister/kallor.yaml --kontrollera-sokvagar
```
