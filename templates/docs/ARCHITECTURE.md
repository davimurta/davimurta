# Arquitetura — {{Nome do projeto}}

## Contexto

<!-- O sistema, quem usa e com quais sistemas externos conversa. -->
{{Descrição em 3 a 5 linhas.}}

```mermaid
flowchart LR
  actor(["{{Ator principal}}"]) --> system["{{Nome do projeto}}"]
  system --> ext["{{Serviço externo}}"]
```

## Containers e componentes

<!-- As peças que rodam separadas (app, API, banco, filas) e os módulos principais de cada uma. -->
```mermaid
flowchart TB
  subgraph client ["{{Cliente}}"]
    ui["{{Telas}}"] --> state["{{Estado / dados}}"]
  end
  subgraph server ["{{API}}"]
    routes["{{Rotas}}"] --> services["{{Regras de negócio}}"] --> repo["{{Acesso a dados}}"]
  end
  state -->|"{{HTTP / JSON}}"| routes
  repo --> db[("{{Banco}}")]
```

| Componente | Responsabilidade |
| --- | --- |
| {{Componente}} | {{O que faz e o que não faz}} |

## Fluxo de dados

<!-- Um fluxo crítico, passo a passo. -->
```mermaid
sequenceDiagram
  participant U as {{Usuário}}
  participant C as {{Cliente}}
  participant A as {{API}}
  participant D as {{Banco}}
  U->>C: {{ação}}
  C->>A: {{requisição}}
  A->>D: {{consulta / transação}}
  D-->>A: {{resultado}}
  A-->>C: {{resposta}}
```

## Decisões principais

<!-- Resumo de uma linha por decisão, com link para o ADR. -->
| Decisão | ADR |
| --- | --- |
| {{Decisão}} | [0001](./adr/0001-{{slug}}.md) |
