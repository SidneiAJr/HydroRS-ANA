# HydroRS-ANA | Dados Históricos | Rio dos Sinos | São Leopoldo | 2018-2025

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

Copie e cole o JSON diretamente

## Fonte

- Estação: 87382000 — São Leopoldo, RS
- Fonte original: ANA — Agência Nacional de Águas
- Uso permitido: dados públicos, sem fins lucrativos

## Projeto relacionado

API pública com queries por mês, média anual e maiores picos — HydroRS API, em breve.
