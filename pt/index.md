---
title: "Início"
description: "A RTV API permite consultar a atualização mais recente disponível dos dados de programação e conteúdos RTV. As respostas são fornecidas em formato JSON e compactadas com GZIP."
permalink: /pt/
lang: pt
translation_path: ""
---

# Documentação da RTV API

A RTV API permite consultar a atualização mais recente disponível dos dados de
programação e conteúdos RTV. As respostas são fornecidas em formato JSON e
compactadas com GZIP.

## Início rápido

Todos os recursos são consultados com o mesmo formato de endpoint:

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

Todas as consultas exigem o API token do cliente no cabeçalho
`Authorization: Bearer TU_API_TOKEN`. O [guia para clientes](API_CLIENTES.md)
inclui um exemplo com cURL.

Substitua `{processId}` pelo identificador atribuído à sua integração e
`{resource}` pelo conjunto de dados necessário. Por exemplo:

```http
GET /api/v1/rtv/processes/123/latest/programs
```

Também é possível solicitar a versão gerada para uma data específica com o
parâmetro opcional `from`, no formato `AAAA-MM-DD`:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

O [guia para clientes](API_CLIENTES.md) contém os detalhes de consulta,
resposta, cabeçalhos e status HTTP.

## Recursos

### Conteúdos e programação

| Recurso | Descrição |
|---|---|
| [Programas](recursos/programs.md) | Programas e metadados editoriais. |
| [Episódios](recursos/episodes.md) | Episódios associados aos programas. |
| [Temporadas](recursos/seasons.md) | Temporadas associadas aos programas. |
| [Programação](recursos/schedule.md) | Grade por canal e data de início. |
| [Vídeo sob demanda](recursos/vod.md) | Disponibilidade de conteúdos sob demanda. |
| [Créditos](recursos/credits.md) | Pessoas e créditos artísticos. |
| [Prêmios](recursos/awards.md) | Catálogo de prêmios. |
| [Tipos de relação](recursos/related-program-types.md) | Relações disponíveis entre programas. |

### Classificação

| Recurso | Descrição |
|---|---|
| [Categorias](recursos/categories.md) | Categorias de conteúdo. |
| [Gêneros](recursos/genres.md) | Gêneros de conteúdo. |
| [Subgêneros](recursos/subgenres.md) | Subgêneros de conteúdo. |
| [Categorias e gêneros](recursos/category-genres.md) | Associações válidas entre categorias e gêneros. |
| [Gêneros e subgêneros](recursos/genre-subgenres.md) | Associações válidas entre gêneros e subgêneros. |
| [Países](recursos/countries.md) | Países referenciados por outros recursos. |

### Canais e clientes

| Recurso | Descrição |
|---|---|
| [Canais](recursos/channels.md) | Sinais incluídos no processo. |
| [Categorias de canais](recursos/channel-categories.md) | Classificação dos sinais. |
| [Clientes](recursos/clients.md) | Clientes habilitados no feed. |
| [Canais por cliente](recursos/client-channels.md) | Canais associados a cada cliente. |

### Esportes

| Recurso | Descrição |
|---|---|
| [Equipes](recursos/teams.md) | Equipes esportivas disponíveis. |
| [Torneios](recursos/tournaments.md) | Torneios e competições esportivas. |
| [Estádios](recursos/stadiums.md) | Estádios e locais esportivos. |
