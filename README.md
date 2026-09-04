# AWS Monitoring Lab

[![CI](https://github.com/M4rc3low/aws-monitoring-lab/actions/workflows/ci.yml/badge.svg)](https://github.com/M4rc3low/aws-monitoring-lab/actions/workflows/ci.yml)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![Zabbix](https://img.shields.io/badge/Zabbix-Monitoring-red)
![Grafana](https://img.shields.io/badge/Grafana-Observability-F46800?logo=grafana&logoColor=white)
![Status](https://img.shields.io/badge/status-learning%20lab-blue)

Laboratório local de **monitoramento e observabilidade com Zabbix e Grafana**, criado para estudar a montagem de uma stack reproduzível com Docker Compose e preparar uma futura integração com infraestrutura AWS de estudo.

## Estado atual

O ambiente já inclui:

- PostgreSQL para persistência do Zabbix
- Zabbix Server
- Zabbix Web com Nginx
- Grafana
- Configuração via `.env`
- Documentação específica em `docs/`
- Pipeline de CI que valida o arquivo `docker-compose.yml`

> A integração com instâncias AWS ainda faz parte do roadmap. O repositório atual demonstra a stack de observabilidade local e a preparação para esse próximo passo.

## Estrutura

```text
aws-monitoring-lab/
├── docker-compose.yml
├── .env.example
├── .gitignore
├── .github/workflows/ci.yml
├── docs/
│   ├── ZABBIX.md
│   ├── GRAFANA.md
│   └── AWS-INSTANCES.md
└── README.md
```

## Como executar localmente

Copie o arquivo de ambiente:

```bash
cp .env.example .env
```

Suba os containers:

```bash
docker compose up -d
```

Confira o estado dos serviços:

```bash
docker compose ps
```

Acesse localmente:

```text
Zabbix: http://localhost:8080
Grafana: http://localhost:3000
```

As credenciais padrão de laboratório podem ser utilizadas apenas no ambiente local inicial. Antes de qualquer exposição em rede ou uso compartilhado, altere as senhas.

Para encerrar:

```bash
docker compose down
```

Para remover também os volumes e reiniciar o laboratório do zero:

```bash
docker compose down -v
```

## Validação

O GitHub Actions executa:

```bash
docker compose config
```

Isso valida a sintaxe e a composição final dos serviços a cada push ou pull request para `main`.

Você também pode executar a mesma verificação localmente antes de subir os containers:

```bash
docker compose config
```

## Boas práticas

- Não usar senhas padrão fora do laboratório local.
- Não expor Zabbix, Grafana ou PostgreSQL diretamente na internet.
- Não versionar `.env` com credenciais reais.
- Em AWS, usar security groups restritos e monitorar apenas recursos autorizados.
- Documentar hosts, templates, dashboards, métricas e alertas adicionados ao laboratório.

## Roadmap

- [x] Criar ambiente local com Docker Compose
- [x] Adicionar Zabbix, PostgreSQL e Grafana
- [x] Criar documentação inicial
- [x] Adicionar validação automática do Docker Compose
- [ ] Adicionar agente Zabbix em instância AWS de estudo
- [ ] Criar dashboard próprio no Grafana
- [ ] Documentar métricas principais
- [ ] Adicionar alertas básicos
- [ ] Documentar arquitetura final da integração AWS

## Valor profissional

Este laboratório demonstra prática com **containers, composição de serviços, monitoramento, observabilidade e CI**, mantendo clara a diferença entre o que já está implementado localmente e o que ainda será integrado à AWS.

## Autor

Desenvolvido por Marcelo Gomes.
