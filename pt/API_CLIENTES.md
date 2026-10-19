---
title: "RTV API — Guia para clientes"
description: "A API permite consultar a versão mais recente disponível de cada conjunto de dados RTV. Substitua `{processId}` pelo identificador de processo atribuído à sua integração."
lang: pt
translation_path: "API_CLIENTES.html"
---

# RTV API — Guia para clientes

A API permite consultar a versão mais recente disponível de cada conjunto de dados
RTV. Substitua `{processId}` pelo identificador de processo atribuído à sua
integração.

## Autenticação

Todas as consultas exigem o API token fornecido para o seu cliente. Envie o token
no cabeçalho `Authorization`, com o prefixo `Bearer`:

```http
Authorization: Bearer TU_API_TOKEN
```

O token permite consultar os processos do seu cliente. Não o inclua na URL.

## Consulta

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

Por padrão, a atualização mais recente é retornada. Para solicitar a versão
gerada para uma data específica, adicione o parâmetro opcional `from`:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

### Parâmetro opcional

| Parâmetro | Formato | Comportamento |
|---|---|---|
| `from` | Data `AAAA-MM-DD` | Seleciona a atualização mais recente disponível gerada para essa data exata. Se omitido, retorna a atualização mais recente disponível do processo. |

## Recursos disponíveis

Cada recurso tem uma página com o formato da resposta e a descrição dos
dados expostos.

| Recurso e documentação | Conteúdo |
|---|---|
| [`/latest/teams`](recursos/teams.md) | Equipes esportivas disponíveis para o processo. |
| [`/latest/tournaments`](recursos/tournaments.md) | Torneios e competições esportivas disponíveis. |
| [`/latest/stadiums`](recursos/stadiums.md) | Estádios e locais esportivos disponíveis. |
| [`/latest/awards`](recursos/awards.md) | Catálogo de prêmios disponível. |
| [`/latest/related-program-types`](recursos/related-program-types.md) | Tipos usados para relacionar programas entre si. |
| [`/latest/channels`](recursos/channels.md) | Sinais ou canais incluídos no processo. |
| [`/latest/categories`](recursos/categories.md) | Categorias usadas para classificar o conteúdo. |
| [`/latest/genres`](recursos/genres.md) | Gêneros usados para classificar o conteúdo. |
| [`/latest/subgenres`](recursos/subgenres.md) | Subgêneros usados para classificar o conteúdo. |
| [`/latest/genre-subgenres`](recursos/genre-subgenres.md) | Associações válidas entre gêneros e subgêneros. |
| [`/latest/category-genres`](recursos/category-genres.md) | Associações válidas entre categorias e gêneros. |
| [`/latest/clients`](recursos/clients.md) | Clientes habilitados no feed. |
| [`/latest/client-channels`](recursos/client-channels.md) | Canais associados a cada cliente. |
| [`/latest/credits`](recursos/credits.md) | Pessoas e créditos artísticos referenciados pelo conteúdo. |
| [`/latest/programs`](recursos/programs.md) | Programas e seus metadados editoriais. |
| [`/latest/episodes`](recursos/episodes.md) | Episódios ou capítulos associados aos programas. |
| [`/latest/seasons`](recursos/seasons.md) | Temporadas associadas aos programas. |
| [`/latest/schedule`](recursos/schedule.md) | Grade de programação ordenada por canal e data de início. |
| [`/latest/countries`](recursos/countries.md) | Países referenciados pelos demais recursos. |
| [`/latest/channel-categories`](recursos/channel-categories.md) | Categorias usadas para classificar sinais. |
| [`/latest/vod`](recursos/vod.md) | Disponibilidade de conteúdos sob demanda. |

O prefixo completo de cada endpoint é:

```text
/api/v1/rtv/processes/{processId}
```

Por exemplo, o endpoint completo de programação é:

```http
GET /api/v1/rtv/processes/123/latest/schedule
```

## Resposta

As respostas bem-sucedidas usam `application/json` e são compactadas com
GZIP. A maioria dos clientes HTTP faz a descompactação automaticamente.

Cabeçalhos relevantes:

- `Content-Encoding: gzip`
- `ETag`: identificador da versão do recurso.
- `X-Generation-Id`: identificador interno da atualização fornecida.

Exemplo com curl:

```bash
curl --compressed \
  -H "Authorization: Bearer TU_API_TOKEN" \
  "https://api.ejemplo.com/api/v1/rtv/processes/123/latest/programs"
```

Substitua `TU_API_TOKEN` pelo token recebido, `123` pelo identificador do seu
processo e `https://api.ejemplo.com` pela URL base informada para a sua integração.
`--compressed` permite receber e descompactar a resposta GZIP. Para consultar uma
data específica, adicione `?from=2026-08-03` ao final da URL.

## Entrega de imagens

A entrega de imagens pode ser adaptada a cada integração. É possível manter o
acesso por URL ou combinar o envio para um destino do cliente por FTP, SFTP ou
armazenamento compatível com S3. Os formatos e as imagens incluídas são definidos
ao configurar o processo.

Conforme a modalidade acordada, o campo `url` de cada imagem ou logo pode conter
uma URL pública, um caminho relativo, um nome de arquivo ou um identificador.
Em todos os casos, o tipo continua sendo texto.

## Opções por integração

A integração pode incluir atributos opcionais, como `poster`, títulos e sinopses
em idiomas adicionais, imagens de créditos ou dados adicionais de programação.
São habilitados ao configurar o processo e descritos nas considerações de cada
recurso.

## Status HTTP

- `200 OK`: recurso encontrado.
- `400 Bad Request`: processo, data ou recurso inválido.
- `401 Unauthorized`: o token está ausente, expirou, foi revogado ou é inválido.
- `403 Forbidden`: o token não permite acesso ao processo solicitado.
- `404 Not Found`: ainda não existe uma atualização para a consulta.
- `500 Internal Server Error`: erro inesperado do serviço.
