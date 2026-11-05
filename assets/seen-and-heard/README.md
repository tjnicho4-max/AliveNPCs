# Seen and Heard — catálogo de percepção

Este diretório contém os dados da feature **Seen and Heard**. Os arquivos são JSON estrito (sem comentários)
para que o carregador possa rejeitar o catálogo inteiro de forma previsível quando a estrutura for inválida.

## Arquivos

- `event-types.json`: tipos de fatos que os sensores podem registrar, regras por testemunha e frases.
- `meters.json`: medidores que transformam memórias em contexto emocional. Os quatro medidores atuais são
  `confront`, `humor`, `tenderness` e `love`.

O contrato e as regras de validação estão em
`WorldAwareness/Catalog/SeenAndHeardCatalog.schema.json` e
`WorldAwareness/Catalog/SeenAndHeardCatalogManifest.json`.

## Caminhos portáveis

O manifesto usa caminhos relativos com `/`:

```text
assets/seen-and-heard/event-types.json
assets/seen-and-heard/meters.json
```

O separador não deve ser trocado por `\\` em configurações ou código. O carregador deve resolver esses caminhos
relativos à raiz do mod usando a API de caminho do sistema operacional; nenhum caminho absoluto ou caminho de
usuário é permitido no catálogo.

## Regras de validação

O carregamento deve exigir `Format: 1`, ids em `lower_snake_case`, pelo menos um tipo e uma frase por tipo.
`Grade` não pode ser negativo, `HalfLifeDays` deve ser positivo, `MinCertainty` deve ficar entre 1 e 5,
`HeardFloor` entre 0 e 1, e todo medidor referenciado por um evento deve existir em `meters.json`. `RangeTiles`
aceita `-1` apenas para significar o mapa inteiro. Campos desconhecidos são erro, não devem ser silenciosamente
ignorados.

O catálogo descreve significado e texto; ele não cria sensores. Um sensor só deve registrar fatos observáveis
(participantes, local, payload e horário). A decisão de quem testemunhou, a certeza, a memória, o prompt e a
eventual reação são responsabilidades do runtime de `WorldAwareness`.

