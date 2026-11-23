# Jellyfin (Reboot Cine)

Stack Docker Swarm do Jellyfin (`lscr.io/linuxserver/jellyfin`).

## Deploy

```sh
docker stack deploy -c media-stack.yml media
```

Requer a rede externa `proxy_net`. Web UI na porta 8096.

## Conteúdo versionado

- `media-stack.yml` — definição do serviço
- `config/*.xml` — configuração do servidor (encoding, rede, live TV, sistema)
- `config/data/root/default/` — definição das bibliotecas (Filmes, Séries, Desenhos, Filmes de Desenho, Coleções)
- `config/data/plugins/configurations/` — configuração dos plugins

## Não versionado (secrets / dados)

- `config/data/data/` — `jellyfin.db` (usuários, senhas, API keys), `device.txt`
- `config/data/metadata`, `config/cache`, `config/log`, `transcodes`
- Mídia: `movies/`, `tv/`, `desenhos/`, `downloads/`

## Layout das bibliotecas

| Biblioteca         | Caminho no container |
|--------------------|----------------------|
| Filmes             | `/movies`            |
| Séries             | `/tv`                |
| Desenhos           | `/desenhos/series`   |
| Filmes de Desenho  | `/desenhos/filmes`   |



## Pra iniciantes

```
docker compose up -d
```