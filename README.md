# Coração em Alerta: Classificação de Doença Arterial Coronariana com IA

Projeto da disciplina de Inteligência Artificial (7º CC) — Faculdade de Computação e
Informática, Universidade Presbiteriana Mackenzie. Parte 2 (N1) — Artigo Parcial.

**Repositório:** https://github.com/Tiago300803/projeto-ia-coracao-em-alerta

## Integrante

| Nome | RA | Turma |
|---|---|---|
| Tiago Caspirro Cardoso | 10390562 | 7N |

## Sobre o projeto

Estudo acadêmico de apoio à triagem que aplica aprendizagem de máquina supervisionada para
classificar a **presença de doença arterial coronariana** (DAC) em pacientes adultos, a partir
de dados clínicos transversais. Não se trata de previsão de risco futuro: o dataset utilizado
não tem acompanhamento longitudinal, então o modelo classifica a condição presente no momento
da coleta, não estima prognóstico.

O projeto está alinhado ao ODS 3 (Saúde e Bem-Estar) da Agenda 2030.

## Dataset

[UCI Heart Disease (subconjunto Cleveland)](https://archive.ics.uci.edu/dataset/45/heart+disease),
303 pacientes, 13 variáveis clínicas preditoras + 1 rótulo. Licença CC BY 4.0. Descrição
completa em [`dataset/README.md`](dataset/README.md).

## Metodologia (resumo)

1. Levantamento de requisitos de dados e análise exploratória (EDA), incluindo variáveis
   numéricas e categóricas.
2. Preparação dos dados: tratamento de valores ausentes, codificação categórica, padronização.
3. Divisão treino/teste estratificada (80/20) e validação cruzada (k=5).
4. Comparação de um baseline (Regressão Logística) com Random Forest e XGBoost.
5. Avaliação com métricas voltadas à triagem em saúde (sensibilidade, especificidade,
   F1-score, ROC-AUC), priorizando a redução de falsos negativos.
6. Explicabilidade do melhor modelo com SHAP.
7. Verificação preliminar de consistência de desempenho entre subgrupos por sexo.

Detalhes completos, código e resultados em [`codigo/analise_heart_disease.ipynb`](codigo/analise_heart_disease.ipynb).

## Status do projeto

- [x] **N1 — Primeiro Bimestre**: proposta refinada, dataset escolhido e documentado, análise
      exploratória, preparação dos dados, protocolo experimental completo (baseline +
      comparação de modelos), artigo parcial.
- [ ] **N2 — Segundo Bimestre**: ajuste de hiperparâmetros, calibração do limiar de decisão,
      aprofundamento da avaliação de equidade entre subgrupos, conclusão, artigo final e vídeo
      de apresentação.

## Estrutura do repositório

```
├── README.md                                              # este arquivo
├── artigo/
│   ├── projetoDeIA_parte2_artigoParcial_CoracaoEmAlerta.docx
│   └── projetoDeIA_parte2_artigoParcial_CoracaoEmAlerta.pdf
├── rubrica/
│   └── projetoDeIA_parte2_rubrica_preenchida.docx
├── codigo/
│   ├── analise_heart_disease.ipynb                        # notebook com toda a análise
│   └── requirements.txt                                   # dependências (versões fixadas)
├── dataset/
│   ├── README.md                                          # descrição do dataset
│   ├── processed.cleveland.data
│   └── heart-disease.names
└── figuras/                                                # gráficos gerados pelo notebook
```

## Aspectos éticos

Dataset público, secundário e anonimizado — a tendência é que dispense submissão a Comitê de
Ética em Pesquisa (CEP), mantida a atribuição da fonte exigida pela licença. Discussão
completa (LGPD, viés de amostragem, risco de uso como diagnóstico automatizado, transparência
via SHAP, e consistência de desempenho entre subgrupos por sexo) na Seção 4.1 do artigo.
