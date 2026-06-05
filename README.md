# AWS Monitoring Lab

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![Zabbix](https://img.shields.io/badge/Zabbix-Monitoring-red)
![Grafana](https://img.shields.io/badge/Grafana-Observability-F46800?logo=grafana&logoColor=white)
![Status](https://img.shields.io/badge/status-learning%20lab-blue)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

Laboratorio de monitoramento local com Zabbix e Grafana, criado para estudar observabilidade e acompanhar a saude de instancias AWS de estudo.

O objetivo e montar um ambiente pratico com Docker Compose, documentar o processo e criar uma base para evoluir o monitoramento de infraestrutura em nuvem.

## Objetivo do laboratorio

- Subir Zabbix Server localmente
- Subir interface web do Zabbix
- Subir banco PostgreSQL para o Zabbix
- Subir Grafana
- Preparar integracao futura com instancias AWS
- Documentar passos de uso, credenciais locais e boas praticas

## Servicos incluidos

- PostgreSQL para Zabbix
- Zabbix Server
- Zabbix Web com Nginx
- Grafana

## Estrutura

```txt
aws-monitoring-lab/
├── docker-compose.yml
├── .env.example
├── .gitignore
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

Verifique os containers:

```bash
docker compose ps
```

Acesse:

```txt
Zabbix: http://localhost:8080
Grafana: http://localhost:3000
```

Credenciais padrao de laboratorio:

```txt
Zabbix: Admin / zabbix
Grafana: admin / admin
```

Pare o ambiente:

```bash
docker compose down
```

Remova volumes locais quando quiser reiniciar do zero:

```bash
docker compose down -v
```

## Boas praticas

- Nao usar senhas padrao em producao.
- Nao expor esse ambiente diretamente na internet.
- Usar security groups restritos em instancias AWS.
- Monitorar apenas instancias de estudo ou autorizadas.
- Documentar hosts, templates e dashboards criados.

## Roadmap

- [x] Criar ambiente local com Docker Compose
- [x] Adicionar Zabbix e Grafana
- [x] Criar documentacao inicial
- [ ] Adicionar agente Zabbix em instancia AWS de estudo
- [ ] Criar dashboard no Grafana
- [ ] Documentar metricas principais
- [ ] Adicionar alertas basicos

## Autor

Desenvolvido por Marcelo Gomes.
