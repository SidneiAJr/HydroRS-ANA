# HydroRS-ANA | Dados Históricos | Rio dos Sinos | São Leopoldo | 2018-2025

![Licença](https://img.shields.io/badge/licença-pública-green)
![Dados](https://img.shields.io/badge/dados-ANA-blue)
![Rio](https://img.shields.io/badge/rio-Sinos-cyan)

## Sobre o projeto

Nasceu em 2024 a partir de 194 mil linhas de dados brutos da ANA (Agência Nacional de Águas), tratados e organizados por dia para facilitar o uso por qualquer pessoa ou sistema.

Os dados cobrem a estação 87382000 em São Leopoldo - RS, com leituras a cada 15 minutos consolidadas em resumos diários.

## Aviso importante sobre qualidade dos dados

Os dados podem conter lacunas e valores nulos nos seguintes casos:

- Falha ou manutenção no sensor de nível
- Queda de energia na estação
- Problemas de transmissão de dados
- Períodos sem coleta pela ANA

Nesses casos, os campos pico, minimo, media e vazao_media aparecem como null. O campo chuva_total pode ainda ter valor mesmo com os demais nulos.

## Estrutura dos dados

Cada arquivo JSON contém um array com resumos diários com os seguintes campos:

| Campo | Descrição | Unidade |
|---|---|---|
| dia | Data da leitura | UTC |
| pico | Nível máximo do dia | metros |
| minimo | Nível mínimo do dia | metros |
| media | Nível médio do dia | metros |
| chuva_total | Chuva acumulada no dia | mm |
| vazao_media | Vazão média do dia | m³/s |

## Evento histórico registrado
📍 Maio de 2024 — Enchente histórica do RS
- Pico máximo registrado: 8.11 metros
- Vazão: 1876 m³/s
- Maior evento nos dados disponíveis

## Arquivos disponíveis

| Ano | Dias com dados | Observação |
|---|---|---|
| 2018 | 63 | Sensor instalado em agosto |
| 2019 | 352 | — |
| 2020 | 302 | Falhas em outubro |
| 2021 | 335 | — |
| 2022 | 121 | Ano com muitas falhas |
| 2023 | 246 | — |
| 2024 | 336 | — |
| 2025 | 152 | Ano em curso |

## Como usar

Copie o arquivo do ano que precisa e use direto no seu projeto.

**JavaScript/Node**
```js
const dados = require('./2024.json')

// Maior pico do ano
const maiorPico = Math.max(...dados.map(d => parseFloat(d.pico) || 0))
console.log(maiorPico) // 8.11
```

**Python**
```python
import json

with open('2024.json') as f:
    dados = json.load(f)

pico = max(float(d['pico']) for d in dados if d['pico'])
print(pico)  # 8.11
```

## Como contribuir
Encontrou erro nos dados? Abre uma issue!

## Fonte

- Estação: 87382000 — São Leopoldo, RS
- Fonte original: ANA — Agência Nacional de Águas
- Uso permitido: dados públicos, sem fins lucrativos

