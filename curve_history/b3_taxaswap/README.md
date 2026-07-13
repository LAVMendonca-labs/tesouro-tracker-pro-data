# Histórico normalizado B3 TaxaSwap

Este diretório indexa o histórico semanal derivado das curvas `PRE` e `DPL`
entre 2015 e 2026. Os dados anuais ficam em assets imutáveis da release
[`curve-history-b3-taxaswap-v1`](https://github.com/LAVMendonca-labs/tesouro-tracker-pro-data/releases/tag/curve-history-b3-taxaswap-v1).

## Formato

Cada asset anual é um arquivo `JSONL.GZ`. Cada linha representa uma data-base
e contém:

- versão do schema e data-base;
- nome, tamanho e SHA-256 do ZIP B3 usado localmente;
- curvas `PRE` e `DPL`;
- pontos compactos nas colunas `calendarDays`, `businessDays` e
  `annualRatePct`.

O manifesto completo da release contém os hashes, tamanhos e a cobertura de
cada asset. Os ZIPs brutos não são redistribuídos.

## Política de atualização

- O backfill semanal é imutável.
- A coleta diária prospectiva será validada em shadow por 30 dias.
- Correções históricas geram uma nova release e uma nova versão de schema; os
  assets anteriores não são sobrescritos.
- O app não consome esta série enquanto o gate `appReady` estiver fechado.
